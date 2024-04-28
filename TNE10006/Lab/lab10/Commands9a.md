Part 1: Step 1 -> 4
### S3
```
en
!
conf t
!
no ip domain-lookup
!
banner motd + Hey, no cwossie without pewmisswon
+
!
line console 0
 logging synchronous
 exit
!
interface range g1/0/1 - 24
 shutdown
!
interface range g1/1/1 - 4
 shutdown
!
interface g1/0/7
 no shutdown
 ex
!
hostname S3
!
vlan 10
 name Staff
 ex
!
vlan 99
 name Management
 ex
!
interface vlan 10
 no shutdown
 desc Staff VLAN
 ex
!
interface vlan 99
 no shutdown
 desc Management VLAN
 ip address 192.168.99.13 255.255.255.0
 ex
!
interface g1/0/7
 switchport mode access
 switchport access vlan 10
 ex
!
end
```

### S4
```
en
!
conf t
!
no ip domain-lookup
!
banner motd + Hey, no cwossie without pewmisswon
+
!
line console 0
 logging synchronous
 exit
!
interface range g1/0/1 - 24
 shutdown
!
interface range g1/1/1 - 4
 shutdown
!
interface g1/0/24
 no shutdown
 ex
!
hostname S4
!
vlan 10
 name Staff
 ex
!
vlan 99
 name Management
 ex
!
interface vlan 10
 no shutdown
 desc Staff VLAN
 ex
!
interface vlan 99
 no shutdown
 desc Management VLAN
 ip address 192.168.99.14 255.255.255.0
 ex
!
interface g1/0/24
 switchport mode access
 switchport access vlan 10
 ex
!
end
```

### S1
```
en
!
conf t
!
no ip domain-lookup
!
banner motd + Hey, no cwossie without pewmisswon
+
!
line console 0
 logging synchronous
 exit
!
interface range f0/1 - 24
 shutdown
!
interface range g0/1 - 2
 shutdown
!
interface f0/18
 no shutdown
 ex
!
hostname S1
!
vlan 10
 name Staff
!
vlan 99
 name Management
!
interface vlan 10
 no shutdown
 desc Staff VLAN
 ex
!
interface vlan 99
 no shutdown
 desc Management VLAN
 ip address 192.168.99.11 255.255.255.0
 ex
!
interface f0/18
 switchport mode access
 switchport access vlan 10
 ex
!
end
```