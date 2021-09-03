#gre 
int tunnel 1
 tunnel source 10.10.10.1
 tunnel destinatio 10.10.10.2
 ip add 172.16.10.1
 tunnel mode gre ip


#bgp
router brp 101
 neighbor 212.12.12.1 remote-as 102
 network 192.168.1.1
