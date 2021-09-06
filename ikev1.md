# Topology
![GRE](https://user-images.githubusercontent.com/62337797/132097000-9a7c7a38-d332-4aff-8852-c32d463df00d.png)
![GRE-2](https://user-images.githubusercontent.com/62337797/132097002-184eccd2-00e3-4cdf-bca4-8f5979f7c3f2.png)
## R1
Cоздание политики первой фазы IPSEC
> crypto isakmp policy 1 # ее приоритет

> authentication pre-share # метод аутентификации 

> hash md5 # какой использовать hash

> gruop 2 # группа Diffie-Hellman

> encryption 3des # симетричное шифрование

Создание ключа аутентификации
> crypto isakmp key CISCO123 address 212.12.12.2

Выбор набора алгоритмов для второй фазы
> crypto ipsec transform-set GRE esp-3des esp-md5-hmac 

> mode tunnel # режим работы IPSEC

Создание профиля IPSEC
> crypto ipsec profile GRE-IPSEC # называем профиль

> set transform-set GRE # добавляем набор алгоритмов

Применение профиля на интерфейсе
> interface tunnel 1

> tunnel protection ipsec profile GRE-IPSEC

## R2
Cоздание политики первой фазы IPSEC
> crypto isakmp policy 1 # ее приоритет

> authentication pre-share # метод аутентификации 

> hash md5 # какой использовать hash

> gruop 2 # группа Diffie-Hellman

> encryption 3des # симетричное шифрование

Создание ключа аутентификации
> crypto isakmp key CISCO123 address 212.12.12.1

Выбор набора алгоритмов для второй фазы
> crypto ipsec transform-set GRE esp-3des esp-md5-hmac 

> mode tunnel # режим работы IPSEC

Создание профиля IPSEC
> crypto ipsec profile GRE-IPSEC # называем профиль

> set transform-set GRE # добавляем набор алгоритмов

Применение профиля на интерфейсе
> interface tunnel 1

> tunnel protection ipsec profile GRE-IPSEC

# Troubleshoot
> show crypto isakmp sa # если есть, тосоединение установлено
