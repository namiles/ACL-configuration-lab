# ACL Configuration Lab -- Work in Progress
This repository contains device configurations for my ACL configuration CCNA lab, which can be found here. More free CCNA labs are available at https://nicksnetworklab.com.   

## Standard ACLs

### R1
```

```

### R2
```

```
### R3
```

```

### ACL Placement


## Extended ACLs
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
```
access-list 150 permit tcp any 10.1.1.0 0.0.0.255 established
access-list 150 permit tcp any 172.16.1.0 0.0.0.255 eq www
access-list 150 permit tcp any 172.16.1.0 0.0.0.255 eq 443
access-list 150 permit udp host 173.20.1.1 eq domain 10.1.1.0 0.0.0.255
access-list 150 deny ip 173.20.1.0 0.0.0.255 10.1.1.0 0.0.0.255
```

### ACL Placement
"extended_local_ACL" should be applied inbound on R1's GigabitEthernet0/1 interface.   
ACL "150" should be applied inbounc on R1's GigabitEthernet0/0 interface.
