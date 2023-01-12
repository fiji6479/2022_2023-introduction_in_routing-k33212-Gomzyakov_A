# Настройки устройств : #

### Роутер (RO1.NY) (ssh admin@172.30.33.2) ###
/interface bridge
add name=EoMPLS
add name=lo0
/interface vpls
add cisco-style=yes cisco-style-id=666 disabled=no l2mtu=1500 mac-address=02:68:F1:3C:34:E3 name=EoMPLS_vpls remote-peer=4.4.4.4
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/routing ospf instance
set [ find default=yes ] router-id=1.1.1.1
/interface bridge port
add bridge=EoMPLS interface=ether2
add bridge=EoMPLS interface=EoMPLS_vpls
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=10.0.1.1/30 interface=ether3 network=10.0.1.0
add address=10.0.2.1/30 interface=ether4 network=10.0.2.0
add address=1.1.1.1 interface=lo0 network=1.1.1.1
/ip dhcp-client
add disabled=no interface=ether1
/mpls ldp
set enabled=yes transport-address=1.1.1.1
/mpls ldp interface
add interface=ether3
add interface=ether4
/routing ospf network
add area=backbone
/system identity
set name=RO1.NY

### Роутер (RO1.LND) (ssh admin@172.30.33.3) ###
/interface bridge
add name=lo0
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/routing ospf instance
set [ find default=yes ] router-id=2.2.2.2
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=2.2.2.2 interface=lo0 network=2.2.2.2
add address=10.0.1.2/30 interface=ether2 network=10.0.1.0
add address=10.0.3.1/30 interface=ether3 network=10.0.3.0
/ip dhcp-client
add disabled=no interface=ether1
/mpls ldp
set enabled=yes transport-address=2.2.2.2
/mpls ldp interface
add interface=ether2
add interface=ether3
/routing ospf network
add area=backbone
/system identity
set name=RO1.LND

### Роутер (RO1.HKI) (ssh admin@172.30.33.4) ###
/interface bridge
add name=lo0
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/routing ospf instance
set [ find default=yes ] router-id=3.3.3.3
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=3.3.3.3 interface=lo0 network=3.3.3.3
add address=10.0.3.2/30 interface=ether2 network=10.0.3.0
add address=10.0.4.1/30 interface=ether3 network=10.0.4.0
add address=10.0.5.1/30 interface=ether4 network=10.0.5.0
/ip dhcp-client
add disabled=no interface=ether1
/mpls ldp
set enabled=yes transport-address=3.3.3.3
/mpls ldp interface
add interface=ether2
add interface=ether3
add interface=ether4
/routing ospf network
add area=backbone
/system identity
set name=RO1.HKI

### Роутер (RO1.LBN) (ssh admin@172.30.33.5) ###
/interface bridge
add name=lo0
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/routing ospf instance
set [ find default=yes ] router-id=6.6.6.6
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=6.6.6.6 interface=lo0 network=6.6.6.6
add address=10.0.2.2/30 interface=ether2 network=10.0.2.0
add address=10.0.4.2/30 interface=ether3 network=10.0.4.0
add address=10.0.7.2/30 interface=ether4 network=10.0.7.0
/ip dhcp-client
add disabled=no interface=ether1
/mpls ldp
set enabled=yes transport-address=6.6.6.6
/mpls ldp interface
add interface=ether2
add interface=ether3
add interface=ether4
/routing ospf network
add area=backbone
/system identity
set name=RO1.LBN

### Роутер (RO1.MSK)ssh admin@172.30.33.6) ### 
/interface bridge
add name=lo0
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/routing ospf instance
set [ find default=yes ] router-id=5.5.5.5
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=5.5.5.5 interface=lo0 network=5.5.5.5
add address=10.0.6.2/30 interface=ether3 network=10.0.6.0
add address=10.0.7.1/30 interface=ether2 network=10.0.7.0
/ip dhcp-client
add disabled=no interface=ether1
/mpls ldp
set enabled=yes transport-address=5.5.5.5
/mpls ldp interface
add interface=ether2
add interface=ether3
/routing ospf network
add area=backbone
/system identity
set name=RO1.MSK

### Роутер (RO1.SPB)ssh admin@172.30.33.7) ### 
/interface bridge
add name=EoMPLS
add name=lo0
/interface vpls
add cisco-style=yes cisco-style-id=666 disabled=no l2mtu=1500 mac-address=02:2B:4C:56:23:41 name=EoMPLS_vpls remote-peer=1.1.1.1
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/routing ospf instance
set [ find default=yes ] router-id=4.4.4.4
/interface bridge port
add bridge=EoMPLS interface=ether4
add bridge=EoMPLS interface=EoMPLS_vpls
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=4.4.4.4 interface=lo0 network=4.4.4.4
add address=10.0.5.2/30 interface=ether2 network=10.0.5.0
add address=10.0.6.1/30 interface=ether3 network=10.0.6.0
/ip dhcp-client
add disabled=no interface=ether1
/mpls ldp
set enabled=yes transport-address=4.4.4.4
/mpls ldp interface
add interface=ether2
add interface=ether3
add interface=ether4
/routing ospf network
add area=backbone
/system identity
set name=RO1.SPB

### Сервер (SGI_Prism)ssh admin@172.30.33.8) ### 
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=192.168.10.1/24 interface=ether2 network=192.168.10.0
/ip dhcp-client
add disabled=no interface=ether1
/system identity
set name=SGI_Prism

### Компьютер (PC1) (ssh admin@172.30.33.9) ### 
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=192.168.10.2/24 interface=ether2 network=192.168.10.0
/ip dhcp-client
add disabled=no interface=ether1
/system identity
set name=PC1
