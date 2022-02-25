# ACL Configuration Lab
This repository contains device configurations for my ACL configuration CCNA lab, which can be found here. More free CCNA labs are available at https://nicksnetworklab.com.   

### R1
```
ip access-list extended extended_local_ACL
  permit icmp host 10.1.1.1 host 172.16.1.3
  permit tcp host 10.1.1.1 host 172.16.1.3 eq 80
  permit tcp host 10.1.1.1 host 172.16.1.3 eq 443
  permit icmp host 10.1.1.2 host 172.16.1.4
  permit tcp host 10.1.1.2 host 172.16.1.4 eq 80
  permit tcp host 10.1.1.2 host 172.16.1.4 eq 443
  deny ip 10.1.1.0 0.0.0.255 172.16.1.0 0.0.0.255
  permit ip 10.1.1.0 0.0.0.255 any
```
