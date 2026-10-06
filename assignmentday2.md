Implement the network design
==============ACCENTURE
config t
vlan 20
name ACCENTURE.COM
Interface vlan 20
 desc ACCENTURE.COM
 no shut
 ip add 10.0.0.129 255.255.255.128

ip dhcp excluded-add 10.0.0.129 10.0.0.139
ip dhcp pool ACCENTURE.COM
 network 10.0.0.128 255.255.255.128
 default-router 10.0.0.129
 domain-name ACCENTURE.COM
int e1/0
 no shut
 switchport mode access
 switchport access vlan 20
@S1
conf t
int e1/0
no shut
ip add dhcp
do bp

=================CHEVRON
config t
vlan 21
name CHEVRON.COM
Interface vlan 21
 desc CHEVRON.COM
 no shut
 ip add 10.0.8.1 255.255.248.0

ip dhcp excluded-add 10.0.8.1 10.0.8.100
ip dhcp pool CHEVRON.COM
 network 10.0.8.0 255.255.248.0
 default-router 10.0.8.1
 domain-name CHEVRON.COM
@A1
conf t
int e0/0
 no shut
 switchport mode access
 switchport access vlan 21
 do sh vlan brief


@P1
conf t
int e0/0
no shut
ip add dhcp
do bp
do sh ip domain

===============SHELL
config t
vlan 22
name SHELL.COM
Interface vlan 22
 desc SHELL.COM
 no shut
 ip add 10.0.16.1 255.255.240.0

ip dhcp excluded-add 10.0.16.1 10.0.16.100
ip dhcp pool SHELL.COM
 network 10.0.16.0 255.255.240.0
 default-router 10.0.16.1
 domain-name SHELL.COM
 do sh run | sec dhcp



@A2
conf t
int e1/0
 no shut
 switchport mode access
 switchport access vlan 22
 do sh vlan brief


@P2
conf t
int e1/0
no shut
ip add dhcp
do bp
do sh ip domain


===============FUELSAVE
config t
vlan 23
name FUELSAVE.COM
Interface vlan 23
 desc FUELSAVE.COM
 no shut
 ip add 10.0.2.1 255.255.254.0

ip dhcp excluded-add 10.0.2.1 10.0.2.100
ip dhcp pool FUELSAVE.COM
 network 10.0.2.0 255.255.254.0
 default-router 10.0.2.1
 domain-name FUELSAVE.COM
 do sh run | sec dhcp

@C2

int e1/0
 no shut
 switchport mode access
 switchport access vlan 23
 do sh vlan brief


@S2
conf t
int e1/0
no shut
ip add dhcp
do bp
do sh ip domain



=================


DHCP RstHayup

@C1:
Config t
vlan 31
name DICT.GOV.PH
Interface vlan 31
 desc DICT.GOV.PH
 no shut
 ip add 10.0.0.65 255.255.255.192
ip dhcp excluded-add 10.0.0.65 10.0.0.74
ip dhcp pool DICT.GOV.PH
 network 10.0.0.64 255.255.255.192
 default-router 10.0.0.65
 domain-name DICT.GOV.PH
Int e1/0
 no shut
 switchport mode access
 switchport access vlan 31
@S1
config t
int e1/0
no shut
ip add dhcp
do bp
******** DPWH.GOV.PH******
@C1:
Config t
vlan 32
name DPWH.GOV.PH
Interface vlan 32
 desc DPWH.GOV.PH
 no shut
 ip add 10.0.32.1 255.255.224.0
ip dhcp excluded-add 10.0.32.1 10.0.32.100
ip dhcp pool DPWH.GOV.PH
 network 10.0.32.0 255.255.224.0
 default-router 10.0.32.1
 domain-name DPWH.GOV.PH
@a1:
CONFIG T
Int e0/0
 no shut
 switchport mode access
 switchport access vlan 32
 DO SH VLAN BRIEF
@P1: 30S
config t
int e0/0
no shut
ip add dhcp
do bp
do sh ip domain

******** FOR DEPED.GOV.PH******
@C1:
Config t
vlan 33
name DEPED.GOV.PH
Interface vlan 33
 desc DEPED.GOV.PH
 no shut
 ip add 10.0.128.1 255.255.224.0
ip dhcp excluded-add 10.0.128.1 10.0.128.100
ip dhcp pool DEPED.GOV.PH
 network 10.0.128.0 255.255.224.0
 default-router 10.0.128.1
 domain-name DEPED.GOV.PH
 do sh run | sec dhcp
@a2:
CONFIG T
Int e1/0
 no shut
 switchport mode access
 switchport access vlan 33
 DO SH VLAN BRIEF
@P2: 30S
config t
int e1/0
no shut
ip add dhcp
do bp
do sh ip domain

******** PNP.GOV.PH******
@C1:
Config t
vlan 34
name PNP.GOV.PH
Interface vlan 34
 desc PNP.GOV.PH
 no shut
 ip add 10.0.64.1 255.255.255.192
ip dhcp excluded-add 10.0.64.1 10.0.2.100
ip dhcp pool PNP.GOV.PH
 network 10.0.64.0 255.255.255.192
 default-router 10.0.64.1
 domain-name PNP.GOV.PH
 do sh run | sec dhcp
@C2:
CONFIG T
Int e1/0
 no shut
 switchport mode access
 switchport access vlan 34
 DO SH VLAN BRIEF
@S2: 30S
config t
int e1/0
no shut
ip add dhcp
do bp
do sh ip domain

convert: 4500 is 13b
s: /32 - 13 = /19
i:   3rd,32i
DPWH.GOV.PH:  10.0.32.0/19
1ST: 10.0.32.1
BC: 10.0.63.255
NOTURS:     10.0.64.0/?















