# Topology
![nat](https://user-images.githubusercontent.com/62337797/132469540-ad0e9e0d-8165-4563-8c61-0485f797062b.png)

## R1
Выбираем внутеренний и вненшний интерфейс
    
    interface g0/0
    ip nat outside
    interface g0/1
    ip nat inside

Выбираем, что будем транслировать

    access-list 100 permit 10.0.0.0 0.0.0.255 

Включаем трансляцию (PAT)
    
    ip nat inside source list 100 interface g0/0 overload

Включаем Static NAT для веб сервера 

    ip nat inside source static tcp 10.0.0.10 80 11.0.0.1 80

