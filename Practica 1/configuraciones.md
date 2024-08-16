# Configuraciones switches

# SW0_G4 (servidor vtp y raiz stp)

```
enable
configure terminal
hostname SW0_G4
end
write

! modo troncal

configure terminal
interface range fastEthernet 0/1-3
switchport mode trunk
switchport nonegotiate
end
write

! Revisar modo troncal: show interfaces trunk
! creacion de VLANs

configure terminal
vlan 14
name Primaria14
vlan 24
name Basicos24
vlan 34
name Diversificado34
end
write

! Revisar creacion de VLANs: show vlan brief
! Modo servidor

configure terminal
vtp version 2
vtp mode server
vtp domain g4
vtp password redes2grupo4
end
write

! Revisar vtp creado: show vtp status
! Spanning tree protocol - PVST

configure terminal
spanning-tree mode rapid-pvst
spanning-tree vlan 14,24,34 root primary
end
write

! Revisar STP: show spanning-tree ó show spanning-tree summary
```


# SW11_G4 

```
enable
configure terminal
hostname SW11_G4
end
write

! Modo troncal

configure terminal
interface range fastEthernet 0/1-3
switchport mode trunk
switchport nonegotiate
end
write

! Revisar modo troncal: show interfaces trunk
! Modo cliente

configure terminal
vtp mode client
vtp domain g4
vtp password redes2grupo4
end
write

! Revisar vtp creado: show vtp status
! Spanning tree protocol - PVST

configure terminal
spanning-tree mode rapid-pvst
spanning-tree vlan 14,24,34 root secondary
end
write

! Revisar STP: show spanning-tree ó show spanning-tree summary
```

# SW1_G4

```
enable
configure terminal
hostname SW1_G4
end
write

! Modo troncal

configure terminal
interface range fastEthernet 0/1-3
switchport mode trunk
switchport nonegotiate
end
write

! Revisar modo troncal: show interfaces trunk
! Modo cliente

configure terminal
vtp mode client
vtp domain g4
vtp password redes2grupo4
end
write

! Revisar vtp creado: show vtp status
! Spanning tree protocol - PVST

configure terminal
spanning-tree mode rapid-pvst
end
write

! Revisar STP: show spanning-tree ó show spanning-tree summary
```


# SW2_G4

```
enable
configure terminal
hostname SW2_G4
end
write

! Modo troncal

configure terminal
interface range fastEthernet 0/1-3
switchport mode trunk
switchport nonegotiate
end
write

! Revisar modo troncal: show interfaces trunk
! Modo cliente

configure terminal
vtp mode client
vtp domain g4
vtp password redes2grupo4
end
write

! Revisar vtp creado: show vtp status
! Spanning tree protocol - PVST

configure terminal
spanning-tree mode rapid-pvst
end
write

! Revisar STP: show spanning-tree ó show spanning-tree summary
```

# SW3_G4

```
enable
configure terminal
hostname SW3_G4
end
write

! Modo troncal

configure terminal
interface range fastEthernet 0/1-4
switchport mode trunk
switchport nonegotiate
end
write

! Revisar modo troncal: show interfaces trunk
! Modo cliente

configure terminal
vtp mode client
vtp domain g4
vtp password redes2grupo4
end
write

! Revisar vtp creado: show vtp status
! Spanning tree protocol - PVST

configure terminal
spanning-tree mode rapid-pvst
end
write

! Revisar STP: show spanning-tree ó show spanning-tree summary
```

# SW4_G4

```
enable
configure terminal
hostname SW4_G4
end
write

! Modo troncal

configure terminal
interface range fastEthernet 0/1-9
switchport mode trunk
switchport nonegotiate
end
write

! Revisar modo troncal: show interfaces trunk
! Modo cliente

configure terminal
vtp mode client
vtp domain g4
vtp password redes2grupo4
end
write

! Revisar vtp creado: show vtp status
! Spanning tree protocol - PVST

configure terminal
spanning-tree mode rapid-pvst
end
write

! Revisar STP: show spanning-tree ó show spanning-tree summary
```

# SW5_G4

```
enable
configure terminal
hostname SW5_G4
end
write

! Modo troncal

configure terminal
interface range fastEthernet 0/1-4
switchport mode trunk
switchport nonegotiate
end
write

! Revisar modo troncal: show interfaces trunk
! Modo cliente

configure terminal
vtp mode client
vtp domain g4
vtp password redes2grupo4
end
write

! Revisar vtp creado: show vtp status
! Spanning tree protocol - PVST

configure terminal
spanning-tree mode rapid-pvst
end
write

! Revisar STP: show spanning-tree ó show spanning-tree summary
```

# SW6_G4

```
enable
configure terminal
hostname SW6_G4
end
write

! Modo troncal

configure terminal
interface range fastEthernet 0/1-3
switchport mode trunk
switchport nonegotiate
end
write

! Revisar modo troncal: show interfaces trunk
! Modo cliente

configure terminal
vtp mode client
vtp domain g4
vtp password redes2grupo4
end
write

! Revisar vtp creado: show vtp status
! Modo acceso

configure terminal
interface fastEthernet 0/3
switchport mode access
switchport access vlan 14
switchport port-security
switchport port-security maximum 1
switchport port-security mac-address sticky
end
write

! Verificar vlan: show vlan brief
! Spanning tree protocol - PVST

configure terminal
spanning-tree mode rapid-pvst
end
write

! Revisar STP: show spanning-tree ó show spanning-tree summary
```

# SW7_G4

```
enable
configure terminal
hostname SW7_G4
end
write

! Modo troncal

configure terminal
interface range fastEthernet 0/1-3
switchport mode trunk
switchport nonegotiate
end
write

! Revisar modo troncal: show interfaces trunk
! Modo cliente

configure terminal
vtp mode client
vtp domain g4
vtp password redes2grupo4
end
write

! Revisar vtp creado: show vtp status
! Modo acceso

configure terminal
interface fastEthernet 0/3
switchport mode access
switchport access vlan 14
switchport port-security
switchport port-security maximum 1
switchport port-security mac-address sticky
end
write

! Verificar vlan: show vlan brief
! Spanning tree protocol - PVST

configure terminal
spanning-tree mode rapid-pvst
end
write

! Revisar STP: show spanning-tree ó show spanning-tree summary
```


# SW8_G4

```
enable
configure terminal
hostname SW8_G4
end
write

! Modo troncal

configure terminal
interface range fastEthernet 0/1-2
switchport mode trunk
switchport nonegotiate
end
write

! Revisar modo troncal: show interfaces trunk
! Modo cliente

configure terminal
vtp mode client
vtp domain g4
vtp password redes2grupo4
end
write

! Revisar vtp creado: show vtp status
! Modo acceso

configure terminal
interface fastEthernet 0/2
switchport mode access
switchport access vlan 24
switchport port-security
switchport port-security maximum 1
switchport port-security mac-address sticky
end
write

! Verificar vlan: show vlan brief
! Spanning tree protocol - PVST

configure terminal
spanning-tree mode rapid-pvst
end
write

! Revisar STP: show spanning-tree ó show spanning-tree summary
```

# SW9_G4

```
enable
configure terminal
hostname SW9_G4
end
write

! Modo troncal

configure terminal
interface range fastEthernet 0/1-3
switchport mode trunk
switchport nonegotiate
end
write

! Revisar modo troncal: show interfaces trunk
! Modo cliente

configure terminal
vtp mode client
vtp domain g4
vtp password redes2grupo4
end
write

! Revisar vtp creado: show vtp status
! Modo acceso

configure terminal
interface fastEthernet 0/3
switchport mode access
switchport access vlan 34
switchport port-security
switchport port-security maximum 1
switchport port-security mac-address sticky
end
write

! Verificar vlan: show vlan brief
! Spanning tree protocol - PVST

configure terminal
spanning-tree mode rapid-pvst
end
write

! Revisar STP: show spanning-tree ó show spanning-tree summary
```

# SW10_G4

```
enable
configure terminal
hostname SW10_G4
end
write

! Modo troncal

configure terminal
interface range fastEthernet 0/1-3
switchport mode trunk
switchport nonegotiate
end
write

! Revisar modo troncal: show interfaces trunk
! Modo cliente

configure terminal
vtp mode client
vtp domain g4
vtp password redes2grupo4
end
write

! Revisar vtp creado: show vtp status
! Modo acceso

configure terminal
interface fastEthernet 0/3
switchport mode access
switchport access vlan 34
switchport port-security
switchport port-security maximum 1
switchport port-security mac-address sticky
end
write

! Verificar vlan: show vlan brief
! Spanning tree protocol - PVST

configure terminal
spanning-tree mode rapid-pvst
end
write

! Revisar STP: show spanning-tree ó show spanning-tree summary
```

# SW12_G4

```
enable
configure terminal
hostname SW12_G4
end
write

! Modo troncal

configure terminal
interface range fastEthernet 0/1-3
switchport mode trunk
switchport nonegotiate
end
write

! Revisar modo troncal: show interfaces trunk
! Modo cliente

configure terminal
vtp mode client
vtp domain g4
vtp password redes2grupo4
end
write

! Revisar vtp creado: show vtp status
! Spanning tree protocol - PVST

configure terminal
spanning-tree mode rapid-pvst
end
write

! Revisar STP: show spanning-tree ó show spanning-tree summary
```

# SW13_G4

```
enable
configure terminal
hostname SW13_G4
end
write

! Modo troncal

configure terminal
interface range fastEthernet 0/1-3
switchport mode trunk
switchport nonegotiate
end
write

! Revisar modo troncal: show interfaces trunk
! Modo cliente

configure terminal
vtp mode client
vtp domain g4
vtp password redes2grupo4
end
write

! Revisar vtp creado: show vtp status
! Spanning tree protocol - PVST

configure terminal
spanning-tree mode rapid-pvst
end
write

! Revisar STP: show spanning-tree ó show spanning-tree summary
```

# SW14_G4

```
enable
configure terminal
hostname SW14_G4
end
write

! Modo troncal

configure terminal
interface range fastEthernet 0/1-4
switchport mode trunk
switchport nonegotiate
end
write

! Revisar modo troncal: show interfaces trunk
! Modo cliente

configure terminal
vtp mode client
vtp domain g4
vtp password redes2grupo4
end
write

! Revisar vtp creado: show vtp status
! Spanning tree protocol - PVST

configure terminal
spanning-tree mode rapid-pvst
end
write

! Revisar STP: show spanning-tree ó show spanning-tree summary
```

# SW15_G4

```
enable
configure terminal
hostname SW15_G4
end
write

!  Modo troncal

configure terminal
interface range fastEthernet 0/1-9
switchport mode trunk
switchport nonegotiate
end
write

! Revisar modo troncal: show interfaces trunk
! Modo cliente

configure terminal
vtp mode client
vtp domain g4
vtp password redes2grupo4
end
write

! Revisar vtp creado: show vtp status
! Spanning tree protocol - PVST

configure terminal
spanning-tree mode rapid-pvst
end
write

! Revisar STP: show spanning-tree ó show spanning-tree summary
```

# SW16_G4

```
enable
configure terminal
hostname SW16_G4
end
write

! Modo troncal

configure terminal
interface range fastEthernet 0/1-4
switchport mode trunk
switchport nonegotiate
end
write

! Revisar modo troncal: show interfaces trunk
! Modo cliente

configure terminal
vtp mode client
vtp domain g4
vtp password redes2grupo4
end
write

! Revisar vtp creado: show vtp status
! Spanning tree protocol - PVST

configure terminal
spanning-tree mode rapid-pvst
end
write

! Revisar STP: show spanning-tree ó show spanning-tree summary
```

# SW17_G4

```
enable
configure terminal
hostname SW17_G4
end
write
! Modo troncal

configure terminal
interface range fastEthernet 0/1-3
switchport mode trunk
switchport nonegotiate
end
write

! Revisar modo troncal: show interfaces trunk
! Modo cliente

configure terminal
vtp mode client
vtp domain g4
vtp password redes2grupo4
end
write

! Revisar vtp creado: show vtp status
! Modo acceso

configure terminal
interface fastEthernet 0/3
switchport mode access
switchport access vlan 14
switchport port-security
switchport port-security maximum 1
switchport port-security mac-address sticky
end
write

! Verificar vlan: show vlan brief
! Spanning tree protocol - PVST

configure terminal
spanning-tree mode rapid-pvst
end
write

! Revisar STP: show spanning-tree ó show spanning-tree summary
```

# SW18_G4

```
enable
configure terminal
hostname SW18_G4
end
write

! Modo troncal

configure terminal
interface range fastEthernet 0/1-3
switchport mode trunk
switchport nonegotiate
end
write

! Revisar modo troncal: show interfaces trunk
! Modo cliente

configure terminal
vtp mode client
vtp domain g4
vtp password redes2grupo4
end
write

! Revisar vtp creado: show vtp status
! Modo acceso

configure terminal
interface fastEthernet 0/3
switchport mode access
switchport access vlan 14
switchport port-security
switchport port-security maximum 1
switchport port-security mac-address sticky
end
write

! Verificar vlan: show vlan brief
! Spanning tree protocol - PVST

configure terminal
spanning-tree mode rapid-pvst
end
write

! Revisar STP: show spanning-tree ó show spanning-tree summary
```

# SW19_G4

```
enable
configure terminal
hostname SW19_G4
end
write

! Modo troncal

configure terminal
interface range fastEthernet 0/1-2
switchport mode trunk
switchport nonegotiate
end
write

! Revisar modo troncal: show interfaces trunk
! Modo cliente

configure terminal
vtp mode client
vtp domain g4
vtp password redes2grupo4
end
write

! Revisar vtp creado: show vtp status
! Modo acceso

configure terminal
interface fastEthernet 0/2
switchport mode access
switchport access vlan 34
switchport port-security
switchport port-security maximum 1
switchport port-security mac-address sticky
end
write

! Verificar vlan: show vlan brief
! Spanning tree protocol - PVST

configure terminal
spanning-tree mode rapid-pvst
end
write

! Revisar STP: show spanning-tree ó show spanning-tree summary
```

# SW20_G4

```
enable
configure terminal
hostname SW20_G4
end
write

! Modo troncal

configure terminal
interface range fastEthernet 0/1-3
switchport mode trunk
switchport nonegotiate
end
write

! Revisar modo troncal: show interfaces trunk
! Modo cliente

configure terminal
vtp mode client
vtp domain g4
vtp password redes2grupo4
end
write

! Revisar vtp creado: show vtp status
! Modo acceso

configure terminal
interface fastEthernet 0/3
switchport mode access
switchport access vlan 24
switchport port-security
switchport port-security maximum 1
switchport port-security mac-address sticky
end
write

! Verificar vlan: show vlan brief
! Spanning tree protocol - PVST

configure terminal
spanning-tree mode rapid-pvst
end
write

! Revisar STP: show spanning-tree ó show spanning-tree summary
```

# SW21_G4

```
enable
configure terminal
hostname SW21_G4
end
write

! Modo troncal

configure terminal
interface range fastEthernet 0/1-3
switchport mode trunk
switchport nonegotiate
end
write

! Revisar modo troncal: show interfaces trunk
! Modo cliente

configure terminal
vtp mode client
vtp domain g4
vtp password redes2grupo4
end
write

! Revisar vtp creado: show vtp status
! Modo acceso

configure terminal
interface fastEthernet 0/3
switchport mode access
switchport access vlan 24
switchport port-security
switchport port-security maximum 1
switchport port-security mac-address sticky
end
write

! Verificar vlan: show vlan brief
! Spanning tree protocol - PVST

configure terminal
spanning-tree mode rapid-pvst
end
write

! Revisar STP: show spanning-tree ó show spanning-tree summary
```