# Preparation
create VM or WEBAPPS # preferably in avilability set or avilability group
# LoadBalancer 
> Work in 3 modes: 5 hash (default), protocol (udp/tcp) + source ip, sorce ip. 

1. Need configure backend pool (vm or apps)
2. Need configure Health Probe (test backend)
3. Need configure Load Balancer Rules (can change mode)
  
