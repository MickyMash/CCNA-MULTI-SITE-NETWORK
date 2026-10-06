# BRANCH ACCESS-SWITCHES





dhcp sn + arp ins



ip dhcp sn

int r f0/1-2

ip dhcp sn tr

ip arp ins tr



no ip dhcp sn info o



## 1.NSO SWITCH



EN

conf t

int r f0/1-24

sw mod acc

sw acc vl 10



IP DHCP SN

INT R F0/1-2

IP DHCP SN TR

IP ARP INS TR



IP DHCP SN VL 10

IP ARP INS VL 10



NO IP DHCP SN INFO OP



int r f0/3-24

sw po

sw po mac s

sw po max 1

sw po vio sh



span po

span bpdug en



## 2\. HL-SWITCH



EN

conf t

HOS HL-SW

int r f0/1-24

sw mod acc

sw acc vl 20



IP DHCP SN

INT R F0/1-2

IP DHCP SN TR

IP ARP INS TR



IP DHCP SN VL 20

IP ARP INS VL 20



NO IP DHCP SN INFO OP



int r f0/3-24

sw po

sw po mac s

sw po max 1

sw po vio sh



span po

span bpdug en





## 3\. MARKETING-SWITCH



EN

conf t

HOS MARKETING-SW

int r f0/1-24

sw mod acc

sw acc vl 30



IP DHCP SN

INT R F0/1-2

IP DHCP SN TR

IP ARP INS TR



IP DHCP SN VL 30

IP ARP INS VL 30



NO IP DHCP SN INFO OP



int r f0/3-24

sw po

sw po mac s

sw po max 1

sw po vio sh



span po

span bpdug en







## 4\. FINANCE-SWITCH



EN

conf t

HOS FINANCE-SW

int r f0/1-24

sw mod acc

sw acc vl 40



IP DHCP SN

INT R F0/1-2

IP DHCP SN TR

IP ARP INS TR



IP DHCP SN VL 40

IP ARP INS VL 40



NO IP DHCP SN INFO OP





int r f0/3-24

sw po

sw po mac s

sw po max 1

sw po vio sh



span po

span bpdug en





## 5.HR-SWITCH



EN

conf t

HOS HR-SW

int r f0/1-24

sw mod acc

sw acc vl 50



IP DHCP SN

INT R F0/1-2

IP DHCP SN TR

IP ARP INS TR



IP DHCP SN VL 50

IP ARP INS VL 50



NO IP DHCP SN INFO OP



int r f0/3-24

sw po

sw po mac s

sw po max 1

sw po vio sh



span po

span bpdug en







## 6.BRANCH-GWA-SWITCH



EN

conf t

int r f0/1-24

sw mod acc

sw acc vl 99



EN

conf t

HOS HR-SW

int r f0/1-24

sw mod acc

sw acc vl 99



IP DHCP SN

INT R F0/1-2

IP DHCP SN TR

IP ARP INS TR



IP DHCP SN VL 99

IP ARP INS VL 99



NO IP DHCP SN INFO OP





int r f0/3-24

sw po

sw po mac s

sw po max 1

sw po vio sh



span po

span bpdug en

