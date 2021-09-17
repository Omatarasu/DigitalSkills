# Topology
![GRE-2](https://user-images.githubusercontent.com/62337797/132096652-79d09d4f-ffa6-4092-9afd-b57e4b25515e.png)

## R1
Создаем процесс BGP

    router bgp 101

Объявляем сети

    network 192.168.1.0 mask 255.255.255.0
    network 172.16.1.0 mask 255.255.255.252

Устанавливаем соседство
    
    neighbor 172.16.1.2 remote-as 102

## R2
Создаем процесс BGP
    
    router bgp 102

Объявляем сети
    
    network 192.168.2.0 mask 255.255.255.0
    network 172.16.1.0 mask 255.255.255.252

Устанавливаем соседство

    neighbor 172.16.1.1 remote-as 101
