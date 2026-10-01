# HQ ACCESS-SWITCHES





dhcp sn + arp ins



ip dhcp sn

int r f0/1-2

ip dhcp sn tr

ip arp ins tr



no ip dhcp sn info o



1.MLOC SWITCH



EN

conf t

int r f0/1-24

sw mod acc

sw acc vl 10



2\. MER-SWITCH



EN

conf t

int r f0/1-24

sw mod acc

sw acc vl 20



3\. MRM-SWITCH



EN

conf t

int r f0/1-24

sw mod acc

sw acc vl 30



4\. IT-SWITCH



EN

conf t

int r f0/1-24

sw mod acc

sw acc vl 40



5.CS-SWITCH



EN

conf t

int r f0/1-24

sw mod acc

sw acc vl 50



6.MANAGEMENT-SWITCH



EN

conf t

int r f0/1-24

sw mod acc

sw acc vl 99



