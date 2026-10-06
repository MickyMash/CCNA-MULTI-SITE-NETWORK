# BRANCH-MULTILAYER-SWITCH2



int g1/0/1

no sw

ip add 172.16.40.2 255.255.255.0

ip ospf 10 area 0

no sh

do wr



vl 10

nam NURSES-SO

vl 20

nam HL

vl 30

nam MARKETING

VL 40

nam FINANCE

VL 50

nam HUMAN-RESOURCE

vl 99

nam MANAGEMENT



EN

CONF T

LINE CON 0

PASS cisco

logg sy

enable secret class

service password-encryption



ip routing



spanning-tree mode rapid-pvst

span vl 10,20,30 root sec

span vl 40,50,99 root pri



int vl 10

ip add 172.31.10.2 255.255.255.0

ip helper-add 172.16.60.11

IP OSPF 10 ARE 0

standby 10 ip 172.31.10.10







int vl 20

ip add 172.31.20.2 255.255.255.0

ip helper-add 172.16.60.11

IP OSPF 10 ARE 0

standby 20 ip 172.31.20.10



int vl 30

ip helper-add 172.16.60.11

ip helper-add 172.16.50.18

IP OSPF 10 ARE 0



standby 30 ip 172.31.30.10



int vl 40

ip helper-add 172.16.60.11

ip helper-add 172.16.50.18

IP OSPF 10 ARE 0



standby 40 ip 172.31.40.10

standby 40 prio 150

standby 40 pre





int vl 50

ip add 172.31.50.1 255.255.255.0

ip helper-add 172.16.60.11

standby 50 ip 172.31.50.10

IP OSPF 10 ARE 0

standby 50 prio 150

standby 50 pre







int vl 99



ip add 172.31.99.1 255.255.255.0

ip helper-add 172.16.60.11

standby 9 ip 172.31.99.10

IP OSPF 10 ARE 0

IP OSPF 10 ARE 0

standby 9 prio 150

standby 9 pre









int g1/0/2

sw mod acc

sw acc vl 10

int g1/0/3

sw mod acc

sw acc vl 20

int g1/0/4

sw mod acc

sw acc vl 30

int g1/0/5

sw mod acc

sw acc vl 40

int g1/0/6

sw mod acc

sw acc vl 50

int g1/0/7

sw mod acc

sw acc vl 99





LACP

int r g1/0/8-9

channel-group 1 mode pass



int po1

sw mod tr

sw tr nat vl 99

sw tr all vl all

do wr





dhcp sn + Arp inspection



ip dhcp sn

ip dhcp sn vl 10,20,30,40,50,99

ip arp ins vl 10,20,30,40,50,99

int r g1/0/2-7

ip dhcp sn tr

ip arp ins tr

no ip dhcp sn info o













