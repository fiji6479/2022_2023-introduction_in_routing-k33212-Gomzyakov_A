# Настройки устройств для первой части: #

### Роутер (RO1.NY) (ssh admin@172.40.44.2) ###
/interface bridge
add name=Lo
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/routing bgp instance
set default client-to-client-reflection=no router-id=10.0.10.1
/routing ospf instance
set [ find default=yes ] router-id=10.0.10.1
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=10.0.10.1 interface=Lo network=10.0.10.1
add address=172.40.1.1/30 interface=ether3 network=172.40.1.0
add address=192.168.20.1/30 interface=ether2 network=192.168.22.0
/ip dhcp-client
add disabled=no interface=ether1
/ip route vrf
add export-route-targets=65530:666 import-route-targets=65530:666 interfaces=ether2 \
    route-distinguisher=65530:666 routing-mark=VRF_DEVOPS
/mpls ldp
set enabled=yes
/mpls ldp interface
add interface=ether3
/routing bgp instance vrf
add redistribute-connected=yes routing-mark=VRF_DEVOPS
/routing bgp network
add network=172.40.0.0/16
/routing bgp peer
add address-families=ip,l2vpn,l2vpn-cisco,vpnv4 name=peer1 remote-address=10.0.11.1 remote-as=\
    65530 update-source=Lo
/routing ospf network
add area=backbone
/system identity
set name=RO1.NY


### Роутер (RO1.LND) (ssh admin@172.40.44.3) ###
/interface bridge
add name=Lo
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/routing bgp instance
set default router-id=10.0.11.1
/routing ospf instance
set [ find default=yes ] router-id=10.0.11.1
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=10.0.11.1 interface=Lo network=10.0.11.1
add address=172.40.1.2/30 interface=ether2 network=172.40.1.0
add address=172.40.2.1/30 interface=ether3 network=172.40.2.0
add address=172.40.3.1/30 interface=ether4 network=172.40.3.0
/ip dhcp-client
add disabled=no interface=ether1
add disabled=no interface=ether2
/mpls ldp
set enabled=yes
/mpls ldp interface
add interface=ether2
add interface=ether3
add interface=ether4
/routing bgp network
add network=172.40.0.0/16
/routing bgp peer
add address-families=ip,l2vpn,l2vpn-cisco,vpnv4 name=peer1 remote-address=10.0.12.1 remote-as=\
    65530 route-reflect=yes update-source=Lo
add address-families=ip,l2vpn,l2vpn-cisco,vpnv4 name=peer2 remote-address=10.0.10.1 remote-as=\
    65530 update-source=Lo
add address-families=ip,l2vpn,l2vpn-cisco,vpnv4 name=peer3 remote-address=10.0.14.1 remote-as=\
    65530 route-reflect=yes update-source=Lo
/routing ospf network
add area=backbone
/system identity
set name=RO1.LND

### Роутер (RO1.LBN) (ssh admin@172.40.44.4) ###

/interface bridge
add name=Lo
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/routing bgp instance
set default router-id=10.0.12.1
/routing ospf instance
set [ find default=yes ] router-id=10.0.12.1
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=10.0.12.1 interface=Lo network=10.0.12.1
add address=172.40.3.2/30 interface=ether2 network=172.40.3.0
add address=172.40.4.2/30 interface=ether3 network=172.40.4.0
add address=172.40.6.1/30 interface=ether4 network=172.40.6.0
/ip dhcp-client
add disabled=no interface=ether1
/mpls ldp
set enabled=yes
/mpls ldp interface
add interface=ether2
add interface=ether4
add interface=ether3
/routing bgp network
add network=172.40.0.0/16
/routing bgp peer
add address-families=ip,l2vpn,l2vpn-cisco,vpnv4 name=peer1 remote-address=10.0.11.1 remote-as=\
    65530 route-reflect=yes update-source=Lo
add address-families=ip,l2vpn,l2vpn-cisco,vpnv4 name=peer2 remote-address=10.0.13.1 remote-as=\
    65530 update-source=Lo
add address-families=ip,l2vpn,l2vpn-cisco,vpnv4 name=peer3 remote-address=10.0.14.1 remote-as=\
    65530 route-reflect=yes update-source=Lo
/routing ospf network
add area=backbone
/system identity
set name=RO1.LBN

### Роутер (RO1.HKI) (ssh admin@172.40.44.5) ###

/interface bridge
add name=Lo
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/routing bgp instance
set default router-id=10.0.14.1
/routing ospf instance
set [ find default=yes ] router-id=10.0.14.1
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=10.0.14.1 interface=Lo network=10.0.14.1
add address=172.40.2.2/30 interface=ether2 network=172.40.2.0
add address=172.40.5.1/30 interface=ether3 network=172.40.5.0            
add address=172.40.4.1/30 interface=ether4 network=172.40.4.0
/ip dhcp-client
add disabled=no interface=ether1
/mpls ldp
set enabled=yes
/mpls ldp interface
add interface=ether2
add interface=ether3
add interface=ether4
/routing bgp network
add network=172.40.0.0/16
/routing bgp peer
add address-families=ip,l2vpn,l2vpn-cisco,vpnv4 name=peer1 remote-address=10.0.11.1 remote-as=\
    65530 route-reflect=yes update-source=Lo
add address-families=ip,l2vpn,l2vpn-cisco,vpnv4 name=peer2 remote-address=10.0.12.1 remote-as=\
    65530 route-reflect=yes update-source=Lo
add address-families=ip,l2vpn,l2vpn-cisco,vpnv4 name=peer3 remote-address=10.0.15.1 remote-as=\
    65530 update-source=Lo
/routing ospf network
add area=backbone
/system identity
set name=RO1.HKI

### Роутер (RO1.SVL) (ssh admin@172.40.44.6) ###

/interface bridge
add name=Lo
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/routing bgp instance
set default client-to-client-reflection=no router-id=10.0.13.1
/routing ospf instance
set [ find default=yes ] router-id=10.0.13.1
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=10.0.13.1 interface=Lo network=10.0.13.1
add address=172.40.6.2/30 interface=ether2 network=172.40.6.0
add address=192.168.30.1/30 interface=ether3 network=192.168.30.0
/ip dhcp-client
add disabled=no interface=ether1
/ip route vrf
add export-route-targets=65530:666 import-route-targets=65530:666 interfaces=ether3 \
    route-distinguisher=65530:666 routing-mark=VRF_DEVOPS
/mpls ldp
set enabled=yes
/mpls ldp interface
add interface=ether2
/routing bgp instance vrf
add redistribute-connected=yes routing-mark=VRF_DEVOPS
/routing bgp network
add network=172.40.0.0/16
/routing bgp peer
add address-families=ip,l2vpn,l2vpn-cisco,vpnv4 name=peer1 remote-address=10.0.12.1 remote-as=\
    65530 update-source=Lo
/routing ospf network
add area=backbone
/system identity
set name=RO1.SVL

### Роутер (RO1.SPB) (ssh admin@172.40.44.7) ###

/interface bridge
add name=Lo
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/routing bgp instance
set default client-to-client-reflection=no router-id=10.0.15.1
/routing ospf instance
set [ find default=yes ] router-id=10.0.15.1
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=10.0.15.1 interface=Lo network=10.0.15.1
add address=172.40.5.2/30 interface=ether2 network=172.40.5.0
add address=192.168.10.1/30 interface=ether3 network=192.168.10.0
/ip dhcp-client
add disabled=no interface=ether1
/ip route vrf
add export-route-targets=65530:666 import-route-targets=65530:666 interfaces=ether3 route-distinguisher=65530:666 routing-mark=VRF_DEVOPS
/mpls ldp
set enabled=yes
/mpls ldp interface
add interface=ether2
/routing bgp instance vrf
add redistribute-connected=yes routing-mark=VRF_DEVOPS
/routing bgp network
add network=172.40.0.0/16
/routing bgp peer
add address-families=ip,l2vpn,l2vpn-cisco,vpnv4 name=peer1 remote-address=10.0.14.1 remote-as=65530 update-source=Lo
/routing ospf network
add area=backbone
/system identity
set name=RO1.SPB

# Настройки устройств для второй части: #

### Роутер (RO1.NY) (ssh admin@172.40.44.2) ###
interface bridge
add name=Lo
add name=VPLS
/interface vpls
add disabled=no l2mtu=1500 mac-address=02:94:C1:74:C4:F4 name=VPLS1 remote-peer=10.0.15.1 vpls-id=15:0
add disabled=no l2mtu=1500 mac-address=02:63:CB:A8:53:08 name=VPLS3 remote-peer=10.0.13.1 vpls-id=15:0
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/routing bgp instance
set default client-to-client-reflection=no router-id=10.0.10.1
/routing ospf instance
set [ find default=yes ] router-id=10.0.10.1
/interface bridge port
add bridge=VPLS interface=VPLS1
add bridge=VPLS interface=VPLS3
add bridge=VPLS interface=ether2
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=10.0.10.1 interface=Lo network=10.0.10.1
add address=172.40.1.1/30 interface=ether3 network=172.40.1.0
/ip dhcp-client
add disabled=no interface=ether1
/mpls ldp
set enabled=yes
/mpls ldp interface
add interface=ether3
/routing bgp network
add network=172.40.0.0/16
/routing bgp peer
add address-families=ip,l2vpn,l2vpn-cisco,vpnv4 name=peer1 remote-address=10.0.11.1 remote-as=65530 update-source=Lo
/routing ospf network
add area=backbone
/system identity
set name=RO1.NY
### Роутер (RO1.SVL) (ssh admin@172.40.44.6) ###
/interface bridge
add name=Lo
add name=VPLS
/interface vpls
add disabled=no l2mtu=1500 mac-address=02:B6:4B:57:21:6F name=VPLS2 remote-peer=10.0.15.1 vpls-id=15:0
add disabled=no l2mtu=1500 mac-address=02:09:81:DE:76:B4 name=VPLS3 remote-peer=10.0.10.1 vpls-id=15:0
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/routing bgp instance
set default client-to-client-reflection=no router-id=10.0.13.1
/routing ospf instance
set [ find default=yes ] router-id=10.0.13.1
/interface bridge port
add bridge=VPLS interface=VPLS2
add bridge=VPLS interface=VPLS3
add bridge=VPLS interface=ether3
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=10.0.13.1 interface=Lo network=10.0.13.1
add address=172.40.6.2/30 interface=ether2 network=172.40.6.0
/ip dhcp-client
add disabled=no interface=ether1
/mpls ldp
set enabled=yes
/mpls ldp interface
add interface=ether2
/routing bgp network
add network=172.40.0.0/16
/routing bgp peer
add address-families=ip,l2vpn,l2vpn-cisco,vpnv4 name=peer1 remote-address=10.0.12.1 remote-as=65530 update-source=Lo
/routing ospf network
add area=backbone
/system identity
set name=RO1.SVL
### Роутер (RO1.SPB) (ssh admin@172.40.44.7) ###
/interface bridge
add name=Lo
add name=VPLS
/interface vpls
add disabled=no l2mtu=1500 mac-address=02:8E:0D:7C:E0:AF name=VPLS1 remote-peer=10.0.10.1 vpls-id=15:0
add disabled=no l2mtu=1500 mac-address=02:04:BE:B1:00:DC name=VPLS2 remote-peer=10.0.13.1 vpls-id=15:0
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/routing bgp instance
set default client-to-client-reflection=no router-id=10.0.15.1
/routing ospf instance
set [ find default=yes ] router-id=10.0.15.1
/interface bridge port
add bridge=VPLS interface=VPLS1
add bridge=VPLS interface=VPLS2
add bridge=VPLS interface=ether3
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=172.40.5.2/30 interface=ether2 network=172.40.5.0
/ip dhcp-client
add disabled=no interface=ether1
/mpls ldp
set enabled=yes
/mpls ldp interface
add interface=ether2
/routing bgp network
add network=172.40.0.0/16
/routing bgp peer
add address-families=ip,l2vpn,l2vpn-cisco,vpnv4 name=peer1 remote-address=10.0.14.1 remote-as=65530 update-source=Lo
/routing ospf network
add area=backbone
/system identity
set name=RO1.SPB

### PC (PC1) (ssh admin@172.40.44.8) ###
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=172.40.40.1/24 interface=ether2 network=172.40.40.0
/ip dhcp-client
add disabled=no interface=ether1
/system identity
set name=PC1
### PC (PC2) (ssh admin@172.40.44.9) ###
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=172.40.40.2/24 interface=ether2 network=172.40.40.0
/ip dhcp-client
add disabled=no interface=ether1
/system identity
set name=PC2
### PC (PC3) (ssh admin@172.40.44.10) ###
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=172.40.40.3/24 interface=ether2 network=172.40.40.0
/ip dhcp-client
add disabled=no interface=ether1
/system identity
set name=PC3
