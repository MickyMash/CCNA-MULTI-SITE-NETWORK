# Branch Router Show Running-config



BRANCH-RTR#sh run

Building configuration...



Current configuration : 1890 bytes

!

version 15.1

service timestamps log datetime msec

no service timestamps debug datetime msec

no service password-encryption

!

hostname BRANCH-RTR

!

!

!

!

ip dhcp excluded-address 172.16.60.1 172.16.60.10

!

ip dhcp pool Branch-Pool

&#x20;network 172.16.60.0 255.255.255.0

&#x20;default-router 172.16.60.1

&#x20;dns-server 172.16.50.17

&#x20;domain-name wr

clock timezone EAT 3

!

!

!

!

no ip cef

no ipv6 cef

!

!

!

!

license udi pid CISCO2911/K9 sn FTX1524W13L-

!

!

!

!

!

!

!

!

!

!

!

!

!

spanning-tree mode pvst

!

!

!

!

!

!

interface GigabitEthernet0/0

&#x20;ip address 172.16.40.1 255.255.255.0

&#x20;ip ospf 10 area 0

&#x20;ip nat inside

&#x20;duplex auto

&#x20;speed auto

!

interface GigabitEthernet0/1

&#x20;ip address 172.16.30.1 255.255.255.0

&#x20;ip ospf 10 area 0

&#x20;ip nat inside

&#x20;duplex auto

&#x20;speed auto

!

interface GigabitEthernet0/2

&#x20;ip address 172.16.60.1 255.255.255.0

&#x20;ip nat inside

&#x20;duplex auto

&#x20;speed auto

!

interface Serial0/2/0

&#x20;ip address 10.10.10.2 255.255.255.252

&#x20;ip ospf 10 area 0

!

interface Serial0/2/1

&#x20;ip address 40.40.40.1 255.255.255.252

&#x20;ip ospf 10 area 0

&#x20;ip nat outside

&#x20;clock rate 2000000

!

interface Serial0/3/0

&#x20;ip address 60.60.60.2 255.255.255.252

&#x20;ip ospf 10 area 0

&#x20;ip nat outside

!

interface Serial0/3/1

&#x20;no ip address

&#x20;clock rate 2000000

!

interface Vlan1

&#x20;no ip address

&#x20;shutdown

!

router ospf 10

&#x20;router-id 2.2.2.2

&#x20;log-adjacency-changes

!

ip nat inside source list 20 interface Serial0/2/1 overload

ip classless

ip route 172.16.0.0 255.255.0.0 10.10.10.1 

ip route 0.0.0.0 0.0.0.0 40.40.40.2 

ip route 0.0.0.0 0.0.0.0 60.60.60.1 50

ip route 172.31.0.0 255.255.0.0 172.16.30.2 

ip route 172.31.0.0 255.255.0.0 172.16.40.2 50

!

ip flow-export version 9

!

!

access-list 20 permit 172.31.0.0 0.0.255.255

!

!

!

!

!

logging trap debugging

logging 172.16.60.11

line con 0

!

line aux 0

!

line vty 0 4

&#x20;login

!

!

ntp authentication-key 1 md5 0802455D0A16544541 7

ntp trusted-key 1

ntp server 172.16.60.11

!

end

