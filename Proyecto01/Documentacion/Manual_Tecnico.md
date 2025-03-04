<h1 align="center">📌 PROYECTO 01</h1>

<div align="center"> <strong>🖧 Redes de Computadoras 1</strong>  </div>
<div align="center"> 🏛 Universidad de San Carlos de Guatemala  </div>
<div align="center"> 📆 Primer Semestre - 2025  </div>

### MANUAL TÉCNICO

**Topología de la Red:** 

La red está organizada con los siguientes switches:
  - Servidor VTP (Root Bridge STP)
  - Switches Clientes y Transparentes

<p align="center">
  <img src="./img/topologia.png" alt="topologia" width="550px">
</p>

**Resumen de Direcciones IP y VLAN**

Tabla de direccionamiento:

<table>
  <thead>
    <tr>
      <th>VLAN ID</th>
      <th>Nombre</th>
      <th>Red</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1X</td>
      <td>Ventas</td>
      <td>192.168.1X.0/24</td>
    </tr>
    <tr>
      <td>2X</td>
      <td>Soporte</td>
      <td>192.168.2X.0/24</td>
    </tr>
    <tr>
      <td>3X</td>
      <td>Gerencia</td>
      <td>192.168.3X.0/24</td>
    </tr>
    <tr>
      <td>4X</td>
      <td>Seguridad</td>
      <td>192.168.4X.0/24</td>
    </tr>
  </tbody>
</table>

Cada PC ha sido asignada a una VLAN específica y cuenta con una dirección IP en la subred correspondiente con máscara 255.255.255.0.

**Configuración de los Switches**
- Configuración del Switch Servidor
```bash
    enable
    configure terminal
    vtp domain G#_technet
    vtp password secure2025
    vtp mode server
    spanning-tree mode pvst
```

**Configuración de las VLANs**
- Las VLANs se crean en el switch Servidor y se propagan automáticamente a los clientes.
```bash
enable
configure terminal
vlan 1X
 name Ventas
vlan 2X
 name Soporte
vlan 3X
 name Gerencia
vlan 4X
 name Seguridad
exit
```

**Configuración de Trunking**
- Los enlaces entre switches deben configurarse como trunks para permitir la propagación de VLANs.
```bash
enable
configure terminal
interface range GigabitEthernet0/1 - 2
 switchport mode trunk
 switchport trunk encapsulation dot1q
```

**Configuración de Etherchannel**
```bash
interface port-channel 1
 switchport mode trunk
 switchport trunk encapsulation dot1q
 channel-group 1 mode active  # (LACP para infraestructura, PAGP para desarrollo)
```

**Verificación de Configuración**
- Verificar VTP en los Switches
```bash
show vtp status
```
- Verificar VLANs en cada Switch
```bash
show vlan brief
```
- Verificar Trunking en los Switches
```bash
show interfaces trunk
```

### **Configuración**
#### **VTP en cada switch**

**Servidor:**
<p align="center">
  <img src="./img/vtp_servidor.png" alt="VTP en Servidor" width="350px">
</p>

**Transparente:**
<p align="center">
  <img src="./img/vtp_transparente.png" alt="VTP en Transparente" width="350px">
</p>

**Cliente01:**
<p align="center">
  <img src="./img/vtp_cliente01.png" alt="VTP en Cliente01" width="350px">
</p>

**Cliente02:**
<p align="center">
  <img src="./img/vtp_cliente02.png" alt="VTP en Cliente02" width="350px">
</p>

#### **Capturas de VLANs en cada switch**

**Servidor:**
<p align="center">
  <img src="./img/vlan_servidor.png" alt="VLANs en Servidor" width="350px">
</p>

**Transparente:**
<p align="center">
  <img src="./img/vlan_trasparente.png" alt="VLANs en Transparente" width="350px">
</p>

**Cliente01:**
<p align="center">
  <img src="./img/vlan_cliente01.png" alt="VLANs en Cliente01" width="350px">
</p>

**Cliente02:**
<p align="center">
  <img src="./img/vlan_cliente02.png" alt="VLANs en Cliente02" width="350px">
</p>

#### **Pruebas de Conectividad (Ping)**
 - Ping en VLAN (Ventas)
<p align="center">
  <img src="./img/ping_vlan_ventas.png" alt="Ping ventas" width="450px">
</p>

 - Ping en VLAN (Soporte)
<p align="center">
  <img src="./img/ping_vlan_soporte.png" alt="Ping soporte" width="450px">
</p>

 - Ping en VLAN (Gerencia)
<p align="center">
  <img src="./img/ping_vlan_gerencia.png" alt="Ping gerencia" width="450px">
</p>

 - Ping en VLAN (Seguridad)
<p align="center">
  <img src="./img/ping_vlan_seguridad.png" alt="Ping seguridad" width="450px">
</p>
