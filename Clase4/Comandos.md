# Redes1_1S2025

## Configuraciones Básicas en Switch
```
enable
configure terminal
no ip domain-lookup
hostname [nombre]
```
### Configuración de contraseña
```
Puede ser:
1. enable secret [contraseña]
2. enable password[contraseña] 
```
>Para verificar la configuración **show running-config**
## Modo de enlace Troncal
### Configurando una sola interfaz a la vez
```
enable
configure terminal
interface  Fa0/1 (interfaz a configurar)
switchport mode trunk
switchport trunk allowed vlan all
do wr
```
### Configurando un rango de interfaces a la vez
```
enable
configure terminal
interface range Fa0/1-5 (interfaces a configurar)
switchport mode trunk
switchport trunk allowed vlan all
do wr
```
>Para verificar la configuración **show interface status**

## Creación VLAN (Virtual LAN)
```
enable
configure terminal
vlan 10
name ventas
exit
vlan 23
name finanzas
do wr
```
>Para verificar la creación **show vlan**

## Modo de enlace Acceso
```
enable
configure terminal
interface fa0/12
switchport mode access
switchport Access vlan 25
do wr
```
>Para verificar la creación **show interface status**

## Configuración VTP
### Modo Servidor (Server Mode)
```
enable
configure terminal
vtp mode server
vtp domain [nombre]
vtp password [password]
vtp version 2
do wr
```
### Modo Cliente (Client Mode)
```
enable
configure terminal
vtp mode client
vtp domain [nombre] (Debe ser el mismo que en el servidor)
vtp password [password] (Debe ser el mismo que en el servidor)
vtp version 2
do wr
```
### Modo Transparente (Transparent Mode)
```
enable
configure terminal
vtp mode transparent
vtp domain [nombre] (Debe ser el mismo que en el servidor)
vtp password [password] (Debe ser el mismo que en el servidor)
vtp version 2
do wr
```
>Para verificar la configuración **show vtp status**    
Si el switch esta en modo transparente se tendrá que crear las vlan localmente.
Para verificar la propagación de vlans **show vlan brief**


