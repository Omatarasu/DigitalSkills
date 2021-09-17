# Topology
![GRE](https://user-images.githubusercontent.com/62337797/132096064-2b3b5096-2d15-4f74-813f-70397952f63b.png)

![GRE-2](https://user-images.githubusercontent.com/62337797/132096279-d527b97e-3e45-4dc0-b138-3f834cdc5021.png)

## R1 
Создание туннеля
    
    interface Tunnel 1 

Задаем ему IP address
    
    ip address 172.16.1.1 255.255.255.252 

Включаем GRE
    
    tunnel mode gre ip

Откуда
    
    tunnel source 212.12.12.1

Куда
    
    tunnel destination 212.12.12.2


## R2
Создание туннеля
    
    interface Tunnel 1 

Задаем ему IP address
    
    ip address 172.16.1.2 255.255.255.252 

Включаем GRE
    
    tunnel mode gre ip

Откуда
    
    tunnel source 212.12.12.2

Куда
    
    tunnel destination 212.12.12.1


