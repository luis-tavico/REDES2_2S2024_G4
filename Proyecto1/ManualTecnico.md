# Proyecto 1 - Manual Técnico
---
UNIVERSIDAD DE SAN CARLOS DE GUATEMALA  
FACULTAD DE INGENIERÍA  
ESCUELA DE CIENCIAS Y SISTEMAS  
REDES DE COMPUTADORAS 2  
ING. ALLAN ALBERTO MORATAYA GÓMEZ  
AUX: EDUARDO IXÉN  

---

## Integrantes

| Nombre                                | Carnet    |
|:------------------------------------- |:---------:|
| [Luis Fernando Falla Guzmán](https://github.com/fernandofalla)          | 201700700 |
| [Cristofher Antonio Saquilmer Rodas](https://github.com/CristofherS)    | 201700686 |
| [Pedro Luis Pu Tavico](https://github.com/luis-tavico)                  | 202000562 |
| [Camilo Ernesto Sincal Sipac](https://github.com/CamiloSincal)          | 202000605 |

## Introducción

El presente manual técnico tiene como objetivo proporcionar las configuraciones necesarias para la implementación de la red de forma facil y segura. La correcta configuración de los switches, el uso de los protocolos de enrutamiento y la implementación de tecnologías como VTP, LACP y DHCP garantizan que la red no solo cumpla con los requisitos solicitados, sino que esté preparada para futuras expansiones. A lo largo de este documento, se explicarán las configuraciones clave necesarias para asegurar el correcto funcionamiento de la red y permitir que otros puedan replicarla.

## Objetivos

* Realizar las configuraciones de switches multicapa y capa 2: Los switches multicapa permiten realizar funciones de enrutamiento en una red, permite la interconexión de las distintas LANs ubicadas en los diferentes edificios. Se configurarán tanto switches de capa 2, que manejan el tráfico dentro de una misma LAN, como switches de capa 3, que permiten el enrutamiento entre redes y proporcionan segmentación en VLANs (Redes de Área Local Virtuales).

* Implementar los protocolos de capa 3: RIP, OSPF, EIGRP y BGP: Estos protocolos de enrutamiento serán configurados para permitir una comunicación eficaz entre las diferentes LANs de los edificios. 

* Aplicar los conocimientos de LACP: LACP (Link Aggregation Control Protocol) permitirá combinar múltiples interfaces físicas para crear un enlace lógico, mejorando la disponibilidad y el ancho de banda de la red.

* Implementar el protocolo VTP: VTP (VLAN Trunking Protocol) facilita la administración de VLANs en toda la red al propagar las configuraciones de VLAN de manera automática entre los switches. 

* Familiarizarse con el protocolo VRRP (HSRP): El uso de VRRP (Virtual Router Redundancy Protocol) o HSRP (Hot Standby Router Protocol). Estos protocolos permiten la creación de un router virtual que actúa como respaldo en caso de que el router principal falle, asegurando así que la conectividad entre los edificios no se interrumpa.

* Familiarizarse con las configuraciones de DHCP y sus conceptos: Se configurará un servidor DHCP (Dynamic Host Configuration Protocol) que asignará direcciones IP automáticamente a los dispositivos conectados a la red. Esta configuración reducirá la necesidad de asignar manualmente direcciones IP.

## Topología

![https://raw.githubusercontent.com/fernandofalla/Img/refs/heads/main/redes2/TOPO_P1.jpg](https://raw.githubusercontent.com/fernandofalla/Img/refs/heads/main/redes2/TOPO_P1.jpg)

## Asignación de direcciones IP

- **Dirección IP: 192.168.4.0, máscara de subred: 255.255.255.0**

### VLAN y Direcciones de red

| Nombre VLAN | Edificio | Dirección IP | Máscara de subred |
|---|---|---|---|
| VLAN_Naranja_Grupo_4 | Edificio 1 | 192.168.4.0 | 255.255.255.192 |
| VLAN_Verde_Grupo_4 | Edificio 1 | 192.168.64.0 | 255.255.255.192 |
| VLAN_Naranja_Grupo_4 | Edificio 2 | 192.168.128.0 | 255.255.255.192 |
| VLAN_Verde_Grupo_4 | Edificio 2 | 192.168.192.0 | 255.255.255.192 |

## Configuración VTP

### Multilayer Switch0 [Cliente]

```
enable
configure terminal
vtp mode client
vtp domain redes2G4
vtp password redes2G4
interface range Gig 1/1/1-2
switchport mode trunk
exit
```

### Multilayer Switch1 [Servidor]
```
enable
configure terminal
vtp mode server
vtp domain redes2G4
vtp password redes2G4
interface range Gig 1/1/1-2
switchport mode trunk
exit
vlan 10
name VLAN_Naranja_Grupo_4
exit
vlan 20
name VLAN_Verde_Grupo_4
exit
vlan 30
name VLAN2_Naranja_Grupo_4
exit
vlan 40
name VLAN2_Verde_Grupo_4
exit
```

### Multilayer Switch11 [Cliente]
```
enable
configure terminal
vtp mode client
vtp domain redes2G4
vtp password redes2G4
interface range Gig1/1/1-2
switchport mode trunk
exit
```

### Multilayer Switch2 [Cliente]
```
enable
configure terminal
vtp mode client
vtp domain redes2G4
vtp password redes2G4
```

### Multilayer Switch3 [Cliente]
```
enable
configure terminal
vtp mode client
vtp domain redes2G4
vtp password redes2G4
exit
```

### Multilayer Switch7 [Cliente]
```
enable
configure terminal
vtp mode client
vtp domain redes2G4
vtp password redes2G4
exit
```

### Multilayer Switch4 [Cliente]
```
enable
configure terminal
vtp mode client
vtp domain redes2G4
vtp password redes2G4
exit
```

### Multilayer Switch5 [Cliente]
```
enable
configure terminal
vtp mode client
vtp domain redes2G4
vtp password redes2G4
exit
```

### Multilayer Switch8 [Cliente]
```
enable
configure terminal
vtp mode client
vtp domain redes2G4
vtp password redes2G4
exit
```

### Multilayer Switch9 [Cliente]
```
enable
configure terminal
vtp mode client
vtp domain redes2G4
vtp password redes2G4
exit
```

### Multilayer Switch6 [Cliente]
```
enable
configure terminal
vtp mode client
vtp domain redes2G4
vtp password redes2G4
exit
```

### Multilayer Switch10 [Cliente]
```
enable
configure terminal
vtp mode client
vtp domain redes2G4
vtp password redes2G4
exit
```

### Switch0 [Cliente]
```
enable
configure terminal
vtp mode client
vtp domain redes2G4
vtp password redes2G4
exit
```

### Switch1 [Cliente]
```
enable
configure terminal
vtp mode client
vtp domain redes2G4
vtp password redes2G4
exit
```

### Switch2 [Cliente]
```
enable
configure terminal
vtp mode client
vtp domain redes2G4
vtp password redes2G4
exit
```

### Switch3 [Cliente]
```
enable
configure terminal
vtp mode client
vtp domain redes2G4
vtp password redes2G4
exit
```

## Conexiones entre Edificios

![https://raw.githubusercontent.com/fernandofalla/Img/refs/heads/main/redes2/EDIFICIOS_P1.jpg](https://raw.githubusercontent.com/fernandofalla/Img/refs/heads/main/redes2/EDIFICIOS_P1.jpg)

### DHCP

| Dispositivo | Dirección IP | Default Gateway | DHCP Services |  
|---|---|---|---|
| DHCP1 | 10.0.0.2 | 10.0.0.1 | |
| DHCP2 | 10.0.0.6 | 10.0.0.5 | |
| Server-WEB | 10.0.0.10 | 10.0.0.9 | |


## Configuración inicial 

### Multilayer Switch0
```
enable
configure terminal
interface Gig1/0/1
no switchport
ip address 10.0.0.1 255.255.255.252
no shutdown
exit
interface Gig1/0/2
no switchport
ip address 10.0.0.5 255.255.255.252
no shutdown
exit
```

### Multilayer Switch11
```
enable
configure terminal
interface Gig1/0/10
no switchport
ip address 10.0.0.9 255.255.255.252
no shutdown
exit
```

## Configuración OSPF

### Multilayer Switch0
```
enable
configure terminal
ip routing
router ospf 1
router-id 1.1.1.1
network 10.0.0.0 0.0.0.3 area 4
network 10.0.0.4 0.0.0.3 area 4
network 192.168.1.0 0.0.0.63 area 4
network 192.168.1.64 0.0.0.63 area 4
network 192.168.1.128 0.0.0.63 area 4
network 192.168.1.192 0.0.0.63 area 4
exit
interface vlan 10
ip address 192.168.4.2 255.255.255.192
ip ospf 1 area 4
no shutdown
exit
interface vlan 20
ip address 192.168.4.66 255.255.255.192
ip ospf 1 area 4
no shutdown
exit
interface vlan 30
ip address 192.168.4.130 255.255.255.192
ip ospf 1 area 4
no shutdown
exit
interface vlan 40
ip address 192.168.4.194 255.255.255.192
ip ospf 1 area 4
no shutdown
exit
```

### Multilayer Switch1
```
enable
configure terminal
interface vlan 10
ip address 192.168.4.1 255.255.255.192
ip ospf 1 area 4
no shutdown
exit
interface vlan 20
ip address 192.168.4.65 255.255.255.192
ip ospf 1 area 4
no shutdown
exit
interface vlan 30
ip address 192.168.4.129 255.255.255.192
ip ospf 1 area 4
no shutdown
exit
interface vlan 40
ip address 192.168.4.193 255.255.255.192
ip ospf 1 area 4
no shutdown
exit
ip routing
router ospf 1
router-id 2.2.2.2
network 192.168.1.0 0.0.0.63 area 4
network 192.168.1.64 0.0.0.63 area 4
network 192.168.1.128 0.0.0.63 area 4
network 192.168.1.192 0.0.0.63 area 4
exit
```

### Multilayer Switch11
```
enable
configure terminal
ip routing
router ospf 1
router-id 3.3.3.3
network 10.0.0.8 0.0.0.3 area 4
network 192.168.1.0 0.0.0.63 area 4
network 192.168.1.64 0.0.0.63 area 4
network 192.168.1.128 0.0.0.63 area 4
network 192.168.1.192 0.0.0.63 area 4
exit
interface vlan 10
ip address 192.168.4.3 255.255.255.192
ip ospf 1 area 4
no shutdown
exit
interface vlan 20
ip address 192.168.4.67 255.255.255.192
ip ospf 1 area 4
no shutdown
exit
interface vlan 30
ip address 192.168.4.131 255.255.255.192
ip ospf 1 area 4
no shutdown
exit
interface vlan 40
ip address 192.168.4.195 255.255.255.192
ip ospf 1 area 4
no shutdown
exit
```

### Multilayer Switch2
```
enable
configure terminal
interface vlan 10
ip address 192.168.4.4 255.255.255.192
ip ospf 1 area 4
no shutdown
exit
interface vlan 20
ip address 192.168.4.68 255.255.255.192
ip ospf 1 area 4
no shutdown
exit
interface vlan 30
ip address 192.168.4.132 255.255.255.192
ip ospf 1 area 4
no shutdown
exit
interface vlan 40
ip address 192.168.4.196 255.255.255.192
ip ospf 1 area 4
no shutdown
exit
ip routing
router ospf 1
router-id 4.4.4.4
network 192.168.1.0 0.0.0.63 area 4
network 192.168.1.64 0.0.0.63 area 4
network 192.168.1.128 0.0.0.63 area 4
network 192.168.1.192 0.0.0.63 area 4
exit
```

### Multilayer Switch3
```
enable
configure terminal
interface vlan 10
ip address 192.168.4.5 255.255.255.192
ip ospf 1 area 4
no shutdown
exit
interface vlan 20
ip address 192.168.4.69 255.255.255.192
ip ospf 1 area 4
no shutdown
exit
interface vlan 30
ip address 192.168.4.133 255.255.255.192
ip ospf 1 area 4
no shutdown
exit
interface vlan 40
ip address 192.168.4.197 255.255.255.192
ip ospf 1 area 4
no shutdown
exit
ip routing
router ospf 1
router-id 5.5.5.5
network 192.168.1.0 0.0.0.63 area 4
network 192.168.1.64 0.0.0.63 area 4
network 192.168.1.128 0.0.0.63 area 4
network 192.168.1.192 0.0.0.63 area 4
exit
```

### Multilayer Switch7
```
enable
configure terminal
interface vlan 10
ip address 192.168.4.6 255.255.255.192
ip ospf 1 area 4
no shutdown
exit
interface vlan 20
ip address 192.168.4.70 255.255.255.192
ip ospf 1 area 4
no shutdown
exit
interface vlan 30
ip address 192.168.4.134 255.255.255.192
ip ospf 1 area 4
no shutdown
exit
interface vlan 40
ip address 192.168.4.198 255.255.255.192
ip ospf 1 area 4
no shutdown
exit
ip routing
router ospf 1
router-id 6.6.6.6
network 192.168.1.0 0.0.0.63 area 4
network 192.168.1.64 0.0.0.63 area 4
network 192.168.1.128 0.0.0.63 area 4
network 192.168.1.192 0.0.0.63 area 4
exit
```

### Multilayer Switch4
```
enable
configure terminal
interface vlan 10
ip address 192.168.4.7 255.255.255.192
ip ospf 1 area 4
no shutdown
exit
interface vlan 20
ip address 192.168.4.71 255.255.255.192
ip ospf 1 area 4
no shutdown
exit
interface vlan 30
ip address 192.168.4.135 255.255.255.192
ip ospf 1 area 4
no shutdown
exit
interface vlan 40
ip address 192.168.4.199 255.255.255.192
ip ospf 1 area 4
no shutdown
exit
ip routing
router ospf 1
router-id 7.7.7.7
network 192.168.1.0 0.0.0.63 area 4
network 192.168.1.64 0.0.0.63 area 4
network 192.168.1.128 0.0.0.63 area 4
network 192.168.1.192 0.0.0.63 area 4
exit
```

### Multilayer Switch5
```
enable
configure terminal
interface vlan 10
ip address 192.168.4.8 255.255.255.192
ip ospf 1 area 4
no shutdown
exit
interface vlan 20
ip address 192.168.4.72 255.255.255.192
ip ospf 1 area 4
no shutdown
exit
interface vlan 30
ip address 192.168.4.136 255.255.255.192
ip ospf 1 area 4
no shutdown
exit
interface vlan 40
ip address 192.168.4.200 255.255.255.192
ip ospf 1 area 4
no shutdown
exit
ip routing
router ospf 1
router-id 8.8.8.8
network 192.168.1.0 0.0.0.63 area 4
network 192.168.1.64 0.0.0.63 area 4
network 192.168.1.128 0.0.0.63 area 4
network 192.168.1.192 0.0.0.63 area 4
exit
```

### Multilayer Switch8
```
enable
configure terminal
interface vlan 10
ip address 192.168.4.9 255.255.255.192
ip ospf 1 area 4
no shutdown
exit
interface vlan 20
ip address 192.168.4.73 255.255.255.192
ip ospf 1 area 4
no shutdown
exit
interface vlan 30
ip address 192.168.4.137 255.255.255.192
ip ospf 1 area 4
no shutdown
exit
interface vlan 40
ip address 192.168.4.201 255.255.255.192
ip ospf 1 area 4
no shutdown
exit
ip routing
router ospf 1
router-id 9.9.9.9
network 192.168.1.0 0.0.0.63 area 4
network 192.168.1.64 0.0.0.63 area 4
network 192.168.1.128 0.0.0.63 area 4
network 192.168.1.192 0.0.0.63 area 4
exit
```

### Multilayer Switch9
```
enable
configure terminal
interface vlan 10
ip address 192.168.4.10 255.255.255.192
ip ospf 1 area 4
no shutdown
exit
interface vlan 20
ip address 192.168.4.74 255.255.255.192
ip ospf 1 area 4
no shutdown
exit
interface vlan 30
ip address 192.168.4.138 255.255.255.192
ip ospf 1 area 4
no shutdown
exit
interface vlan 40
ip address 192.168.4.202 255.255.255.192
ip ospf 1 area 4
no shutdown
exit
ip routing
router ospf 1
router-id 10.10.10.10
network 192.168.1.0 0.0.0.63 area 4
network 192.168.1.64 0.0.0.63 area 4
network 192.168.1.128 0.0.0.63 area 4
network 192.168.1.192 0.0.0.63 area 4
exit
```

## Conexiones LACP

![https://raw.githubusercontent.com/fernandofalla/Img/refs/heads/main/redes2/LACP_P1.jpg](https://raw.githubusercontent.com/fernandofalla/Img/refs/heads/main/redes2/LACP_P1.jpg)

### Multilayer Switch1
```
enable
configure terminal
interface range Gig1/0/20-22
channel-protocol lacp
channel-group 1 mode active
exit
interface port-channel 1
switchport mode trunk
end
wr
```

### Multilayer Switch3
```
enable
configure terminal
interface range fastEthernet 0/20-22
channel-protocol lacp
channel-group 1 mode active
exit
interface port-channel 1
switchport trunk encapsulation dot1q
switchport mode trunk
end
wr
```

### Multilayer Switch2
```
enable
configure terminal
interface range Gig1/0/20-22
channel-protocol lacp
channel-group 1 mode active
exit
interface port-channel 1
switchport mode trunk
end
wr
```

### Multilayer Switch7
```
enable
configure terminal
interface range fastEthernet 0/20-22
channel-protocol lacp
channel-group 1 mode active
exit
interface port-channel 1
switchport trunk encapsulation dot1q
switchport mode trunk
end
wr
```

## Red Edificio 1

![https://raw.githubusercontent.com/fernandofalla/Img/refs/heads/main/redes2/EDIFICIO1_P1.jpg](https://raw.githubusercontent.com/fernandofalla/Img/refs/heads/main/redes2/EDIFICIO1_P1.jpg)

### Configuración de interfaces [Switches]

### Multilayer Switch3
```
enable
configure terminal
interface fastEthernet 0/1
switchport trunk encapsulation dot1q
switchport mode trunk
exit
interface fastEthernet 0/2
switchport trunk encapsulation dot1q
switchport mode trunk
end
wr
```

### Multilayer Switch4
```
enable
configure terminal
interface fastEthernet 0/1
switchport trunk encapsulation dot1q
switchport mode trunk
exit
end
wr
```

### Multilayer Switch5
```
enable
configure terminal
interface fastEthernet 0/1
switchport trunk encapsulation dot1q
switchport mode trunk
exit
end
wr
```

### Multilayer Switch6
```
enable
configure terminal
interface fastEthernet 0/10
switchport trunk encapsulation dot1q
switchport mode trunk
exit
interface fastEthernet 0/11
switchport trunk encapsulation dot1q
switchport mode trunk
exit
interface fastEthernet 0/15
switchport trunk encapsulation dot1q
switchport mode trunk
exit
interface fastEthernet 0/16
switchport trunk encapsulation dot1q
switchport mode trunk
end
wr
```

### Switch0
```
enable
configure terminal
interface fastEthernet 0/10
switchport mode trunk
exit
interface range fastEthernet 0/1-2
switchport mode access
switchport acces vlan 10
```

### Switch1
```
enable
configure terminal
interface fastEthernet 0/10
switchport mode trunk
exit
interface range fastEthernet 0/1-2
switchport mode access
switchport acces vlan 20
```

## Configuración HSRP

### Multilayer Switch4
```
enable
configure terminal
interface vlan 10
standby 1 ip 192.168.4.11
standby 1 priority 150
standby 1 preempt
no shutdown
exit
interface vlan 20
standby 2 ip 192.168.4.75
standby 2 priority 150
standby 2 preempt
no shutdown
end
wr
```

### Multilayer Switch5
```
enable
configure terminal
interface vlan 10
standby 1 ip 192.168.4.11
standby 1 priority 90
standby 1 preempt
no shutdown
exit
interface vlan 20
standby 2 ip 192.168.4.75
standby 2 priority 90
standby 2 preempt
no shutdown
end
```

## Configuración DHCP

### Multilayer Switch4
```
enable
configure terminal
interface vlan 10
ip helper-address 10.0.0.2
exit
interface vlan 20
ip helper-address 10.0.0.2
end
wr
```

### Multilayer Switch5
```
enable
configure terminal
interface vlan 10
ip helper-address 10.0.0.2
exit
interface vlan 20
ip helper-address 10.0.0.2
end
wr
```

## Red edificio 2

![https://raw.githubusercontent.com/fernandofalla/Img/refs/heads/main/redes2/EDIFICIO2_P1.jpg](https://raw.githubusercontent.com/fernandofalla/Img/refs/heads/main/redes2/EDIFICIO2_P1.jpg)

## Configuración de interfaces [Switches]

### Multilayer Switch7
```
enable
configure terminal
interface fastEthernet 0/1
switchport trunk encapsulation dot1q
switchport mode trunk
exit
interface fastEthernet 0/2
switchport trunk encapsulation dot1q
switchport mode trunk
end
wr
```

### Multilayer Switch8
```
enable
configure terminal
interface fastEthernet 0/2
switchport trunk encapsulation dot1q
switchport mode trunk
end
wr
```

### Multilayer Switch9
```
enable
configure terminal
interface fastEthernet 0/1
switchport trunk encapsulation dot1q
switchport mode trunk
end
wr
```

### Multilayer Switch10
```
enable
configure terminal
interface fastEthernet 0/10
switchport trunk encapsulation dot1q
switchport mode trunk
exit
interface fastEthernet 0/11
switchport trunk encapsulation dot1q
switchport mode trunk
exit
interface fastEthernet 0/15
switchport trunk encapsulation dot1q
switchport mode trunk
exit
interface fastEthernet 0/16
switchport trunk encapsulation dot1q
switchport mode trunk
end
wr
```

### Switch2
```
enable
configure terminal
interface fastEthernet 0/10
switchport mode trunk
exit
interface range fastEthernet 0/1-2
switchport mode access
switchport acces vlan 30
Switch3
enable
configure terminal
interface fastEthernet 0/10
switchport mode trunk
exit
interface range fastEthernet 0/1-2
switchport mode access
switchport acces vlan 40
```

## Configuración HSRP

### Multilayer Switch8
```
enable
configure terminal
interface vlan 30
standby 3 ip 192.168.4.139
standby 3 priority 150
standby 3 preempt
no shutdown
exit
interface vlan 40
standby 4 ip 192.168.4.203
standby 4 priority 150
standby 4 preempt
no shutdown
end
wr
```

### Multilayer Switch9
```
enable
configure terminal
interface vlan 30
standby 3 ip 192.168.4.139
standby 3 priority 90
standby 3 preempt
no shutdown
exit
interface vlan 40
standby 4 ip 192.168.4.203
standby 4 priority 90
standby 4 preempt
no shutdown
end
```

## Configuración DHCP

### Multilayer Switch8
```
enable
configure terminal
interface vlan 30
ip helper-address 10.0.0.6
exit
interface vlan 40
ip helper-address 10.0.0.6
end
wr
```

### Multilayer Switch9
```
enable
configure terminal
interface vlan 30
ip helper-address 10.0.0.6
exit
interface vlan 40
ip helper-address 10.0.0.6
end
wr
```

## Configuración De Access Lists

### Multilayer Switch4 y Multilayer Switch5
```
enable
configure terminal
access-list 100 deny icmp 192.168.4.0 0.0.0.63 192.168.4.64 0.0.0.63 echo
access-list 100 deny icmp 192.168.4.0 0.0.0.63 192.168.4.192 0.0.0.63 echo
access-list 100 permit ip any any
interface vlan 10
ip access-group 100 in
exit
access-list 101 deny icmp 192.168.4.64 0.0.0.63 192.168.4.0 0.0.0.63 echo
access-list 101 deny icmp 192.168.4.64 0.0.0.63 192.168.4.128 0.0.0.63 echo
access-list 101 permit ip any any
interface vlan 20
ip access-group 101 in
end
wr

```

### Multilayer Switch8 y Multilayer Switch9
```
enable
configure terminal
access-list 100 deny icmp 192.168.4.128 0.0.0.63 192.168.4.64 0.0.0.63 echo
access-list 100 deny icmp 192.168.4.128 0.0.0.63 192.168.4.192 0.0.0.63 echo
access-list 100 permit ip any any
interface vlan 30
ip access-group 100 in
exit
access-list 101 deny icmp 192.168.4.192 0.0.0.63 192.168.4.0 0.0.0.63 echo
access-list 101 deny icmp 192.168.4.192 0.0.0.63 192.168.4.128 0.0.0.63 echo
access-list 101 permit ip any any
interface vlan 40
ip access-group 101 in
end
wr

```
