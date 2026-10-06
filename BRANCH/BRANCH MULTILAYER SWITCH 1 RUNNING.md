# BRANCH MULTILAYER SWITCH 1 RUNNING CONFIG





Branch-Multilayer-sw1#sh run

Building configuration...



Current configuration : 4000 bytes

!

version 16.3.2

service timestamps log datetime msec

no service timestamps debug datetime msec

service password-encryption

!

hostname Branch-Multilayer-sw1

!

!

no profinet

enable secret 5 $1$mERr$9cTjUIEqNGurQiFU.ZeCi1

!

!

!

clock timezone EAT 4

!

!

!

!

no ip cef

ip routing

!

no ipv6 cef

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

ip arp inspection vlan 10,20,30,40,50,99

!

ip dhcp snooping vlan 10,20,30,40,50,99

no ip dhcp snooping information option

ip dhcp snooping

!

!

!

spanning-tree mode rapid-pvst

spanning-tree vlan 10,20,30 priority 24576

spanning-tree vlan 40,50,99 priority 28672

!

!

!

!

!

!

interface Port-channel1

&#x20;switchport trunk native vlan 99

&#x20;switchport mode trunk

!

interface GigabitEthernet1/0/1

&#x20;no switchport

&#x20;ip address 172.16.30.2 255.255.255.0

&#x20;ip ospf 10 area 0

&#x20;duplex auto

&#x20;speed auto

!

interface GigabitEthernet1/0/2

&#x20;ip dhcp snooping trust

&#x20;switchport access vlan 10

&#x20;switchport mode access

&#x20;ip arp inspection trust

!

interface GigabitEthernet1/0/3

&#x20;ip dhcp snooping trust

&#x20;switchport access vlan 20

&#x20;switchport mode access

&#x20;ip arp inspection trust

!

interface GigabitEthernet1/0/4

&#x20;ip dhcp snooping trust

&#x20;switchport access vlan 30

&#x20;switchport mode access

&#x20;ip arp inspection trust

!

interface GigabitEthernet1/0/5

&#x20;ip dhcp snooping trust

&#x20;switchport access vlan 40

&#x20;switchport mode access

&#x20;ip arp inspection trust

!

interface GigabitEthernet1/0/6

&#x20;ip dhcp snooping trust

&#x20;switchport access vlan 50

&#x20;switchport mode access

&#x20;ip arp inspection trust

!

interface GigabitEthernet1/0/7

&#x20;ip dhcp snooping trust

&#x20;switchport access vlan 99

&#x20;switchport mode access

&#x20;ip arp inspection trust

!

interface GigabitEthernet1/0/8

&#x20;switchport trunk native vlan 99

&#x20;switchport mode trunk

&#x20;channel-group 1 mode active

!

interface GigabitEthernet1/0/9

&#x20;switchport trunk native vlan 99

&#x20;switchport mode trunk

&#x20;channel-group 1 mode active

!

interface GigabitEthernet1/0/10

!

interface GigabitEthernet1/0/11

!

interface GigabitEthernet1/0/12

!

interface GigabitEthernet1/0/13

!

interface GigabitEthernet1/0/14

!

interface GigabitEthernet1/0/15

!

interface GigabitEthernet1/0/16

!

interface GigabitEthernet1/0/17

!

interface GigabitEthernet1/0/18

!

interface GigabitEthernet1/0/19

!

interface GigabitEthernet1/0/20

!

interface GigabitEthernet1/0/21

!

interface GigabitEthernet1/0/22

!

interface GigabitEthernet1/0/23

!

interface GigabitEthernet1/0/24

!

interface GigabitEthernet1/1/1

!

interface GigabitEthernet1/1/2

!

interface GigabitEthernet1/1/3

!

interface GigabitEthernet1/1/4

!

interface Vlan1

&#x20;no ip address

&#x20;shutdown

!

interface Vlan10

&#x20;mac-address 0001.96c6.2901

&#x20;ip address 172.31.10.1 255.255.255.0

&#x20;ip helper-address 172.16.60.11

&#x20;ip ospf 10 area 0

&#x20;standby 10 ip 172.31.10.10

&#x20;standby 10 priority 150

&#x20;standby 10 preempt

!

interface Vlan20

&#x20;mac-address 0001.96c6.2902

&#x20;ip address 172.31.20.1 255.255.255.0

&#x20;ip helper-address 172.16.60.11

&#x20;ip ospf 10 area 0

&#x20;standby 20 ip 172.31.20.10

&#x20;standby 20 priority 150

&#x20;standby 20 preempt

!

interface Vlan30

&#x20;mac-address 0001.96c6.2903

&#x20;ip address 172.31.30.1 255.255.255.0

&#x20;ip helper-address 172.16.60.11

&#x20;ip ospf 10 area 0

&#x20;standby 30 ip 172.31.30.10

&#x20;standby 30 priority 150

&#x20;standby 30 preempt

!

interface Vlan40

&#x20;mac-address 0001.96c6.2904

&#x20;ip address 172.31.40.2 255.255.255.0

&#x20;ip helper-address 172.16.60.11

&#x20;ip ospf 10 area 0

&#x20;standby 40 ip 172.31.40.10

!

interface Vlan50

&#x20;mac-address 0001.96c6.2905

&#x20;ip address 172.31.50.2 255.255.255.0

&#x20;ip helper-address 172.16.60.11

&#x20;ip ospf 10 area 0

&#x20;standby 50 ip 172.31.50.10

!

interface Vlan99

&#x20;mac-address 0001.96c6.2906

&#x20;ip address 172.31.99.2 255.255.255.0

&#x20;ip helper-address 172.16.60.11

&#x20;ip ospf 10 area 0

&#x20;standby 9 ip 172.31.99.10

!

router ospf 10

&#x20;router-id 2.2.2.10

&#x20;log-adjacency-changes

!

ip classless

ip route 0.0.0.0 0.0.0.0 172.16.30.1 

!

ip flow-export version 9

!

!

!

!

!

!

!

line con 0

&#x20;password 7 0822455D0A16

&#x20;logging synchronous

!

line aux 0

!

line vty 0 4

&#x20;login

!

!

!

ntp authentication-key 1 md5 080048430017544541 7

ntp trusted-key 1

ntp server 10.10.10.10

ntp update-calendar

!

end

