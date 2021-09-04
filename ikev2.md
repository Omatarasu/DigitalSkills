# Topology
![GRE](https://user-images.githubusercontent.com/62337797/132098193-d3d0314f-2ebf-4c68-869f-a01dc007a2ba.png)
![GRE-2](https://user-images.githubusercontent.com/62337797/132098194-b75c5ffa-0172-49d4-ad63-0afb18c9dc52.png)
## R1
Создание связки ключей
> crypto ikev2 keyring GRE-KEY # называем связку ключей

> peer R2 # логическое название ключа

> address 212.12.12.2 # для кого ключ

> pre-shared-key CISCO123

Настройка профиля первой фазы 
> crypto ikev2 profile GRE-IKE # называем профиль IKE

> keyring local GRE-KEY # выбор связки ключей 

> authentication local pre-share

> authentication remote pre-share

> match address local 212.12.12.1 

> match identity remote address 212.12.12.2

Настройка профиля второй фазы

> crypto ipsec profile GRE-IPSEC # называем профиль

> set ikev2-profile GRE-IKE # соединяем с профилем первой фазы

Применение на интерфейсе

> interface tunnel 1

> tunnel protection ipsec profile GRE-IPSEC

## R2
Создание связки ключей
> crypto ikev2 keyring GRE-KEY # называем связку ключей

> peer R1 # логическое название ключа

> address 212.12.12.1 # для кого ключ

> pre-shared-key CISCO123

Настройка профиля первой фазы 
> crypto ikev2 profile GRE-IKE # называем профиль IKE

> keyring local GRE-KEY # выбор связки ключей 

> authentication local pre-share

> authentication remote pre-share

> match address local 212.12.12.2

> match identity remote address 212.12.12.1

Настройка профиля второй фазы

> crypto ipsec profile GRE-IPSEC # называем профиль

> set ikev2-profile GRE-IKE # соединяем с профилем первой фазы

Применение на интерфейсе

> interface tunnel 1

> tunnel protection ipsec profile GRE-IPSEC


