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
      <td>13</td>
      <td>Ventas</td>
      <td>192.168.13.0/24</td>
    </tr>
    <tr>
      <td>23</td>
      <td>Soporte</td>
      <td>192.168.23.0/24</td>
    </tr>
    <tr>
      <td>33</td>
      <td>Gerencia</td>
      <td>192.168.33.0/24</td>
    </tr>
    <tr>
      <td>43</td>
      <td>Seguridad</td>
      <td>192.168.43.0/24</td>
    </tr>
  </tbody>
</table>

<table>
  <thead>
    <tr>
      <th>Vlan</th>
      <th>Dispositivo</th>
      <th>IP Asignada</th>
      <th>Switch Conectado</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>13</td>
      <td>VENTAS 1</td>
      <td>192.168.13.11</td>
      <td>SW4</td>
    </tr>
    <tr>
      <td>13</td>
      <td>VENTAS 2</td>
      <td>192.168.13.12</td>
      <td>SW8</td>
    </tr>
    <tr>
      <td>13</td>
      <td>VENTAS 3</td>
      <td>192.168.13.13</td>
      <td>SW10</td>
    </tr>
    <tr>
      <td>13</td>
      <td>VENTAS 4</td>
      <td>192.168.13.14</td>
      <td>SW7</td>
    </tr>
    <tr>
      <td>13</td>
      <td>VENTAS 5</td>
      <td>192.168.13.15</td>
      <td>SW1</td>
    </tr>
    <tr>
      <td>23</td>
      <td>SOPORTE 1</td>
      <td>192.168.23.11</td>
      <td>SW3</td>
    </tr>
    <tr>
      <td>23</td>
      <td>SOPORTE 2</td>
      <td>192.168.23.12</td>
      <td>SW9</td>
    </tr>
    <tr>
      <td>23</td>
      <td>SOPORTE 3</td>
      <td>192.168.23.13</td>
      <td>SW10</td>
    </tr>
    <tr>
      <td>23</td>
      <td>SOPORTE 4</td>
      <td>192.168.23.14</td>
      <td>SW6</td>
    </tr>
    <tr>
      <td>23</td>
      <td>SOPORTE 5</td>
      <td>192.168.23.15</td>
      <td>SW11</td>
    </tr>
    <tr>
      <td>33</td>
      <td>GERENCIA 1</td>
      <td>192.168.33.11</td>
      <td>SW4</td>
    </tr>
    <tr>
      <td>33</td>
      <td>GERENCIA 2</td>
      <td>192.168.33.12</td>
      <td>SW1</td>
    </tr>
    <tr>
      <td>33</td>
      <td>GERENCIA 3</td>
      <td>192.168.33.13</td>
      <td>SW13</td>
    </tr>
    <tr>
      <td>33</td>
      <td>GERENCIA 4</td>
      <td>192.168.33.14</td>
      <td>SW12</td>
    </tr>
    <tr>
      <td>33</td>
      <td>GERENCIA 5</td>
      <td>192.168.33.15</td>
      <td>SW10</td>
    </tr>
    <tr>
      <td>43</td>
      <td>SEGURIDAD 1</td>
      <td>192.168.43.11</td>
      <td>SW2</td>
    </tr>
    <tr>
      <td>43</td>
      <td>SEGURIDAD 2</td>
      <td>192.168.43.12</td>
      <td>SW8</td>
    </tr>
    <tr>
      <td>43</td>
      <td>SEGURIDAD 3</td>
      <td>192.168.43.13</td>
      <td>SW11</td>
    </tr>
    <tr>
      <td>43</td>
      <td>SEGURIDAD 5</td>
      <td>192.168.43.15</td>
      <td>SW6</td>
    </tr>
    <tr>
      <td>43</td>
      <td>SEGURIDAD 6</td>
      <td>192.168.43.16</td>
      <td>SW7</td>
    </tr>
    <tr>
      <td>43</td>
      <td>SEGURIDAD 7</td>
      <td>192.168.43.17</td>
      <td>SW9</td>
    </tr>
    <tr>
      <td>53</td>
      <td>RECEPCION 1</td>
      <td>192.168.53.11</td>
      <td>SW5</td>
    </tr>
    <tr>
      <td>53</td>
      <td>RECEPCION 2</td>
      <td>192.168.53.12</td>
      <td>SW5</td>
    </tr>
    <tr>
      <td>53</td>
      <td>RECEPCION 3</td>
      <td>192.168.53.13</td>
      <td>SW5</td>
    </tr>
    <tr>
      <td>53</td>
      <td>RECEPCION 4</td>
      <td>192.168.53.14</td>
      <td>SW5</td>
    </tr>
  </tbody>
</table>

Cada PC ha sido asignada a una VLAN específica y cuenta con una dirección IP en la subred correspondiente con máscara 255.255.255.0.

---
# Configuraciones de Switches

## Servidor

| Configuración | Comando |
| --- | --- |
| **Modo STP** | `spanning-tree mode rapid-pvst` |
| **Root Bridge** | `spanning-tree vlan 1-100 root primary` |
| **Modo VTP** | `vtp mode server` |
| **Versión VTP** | `vtp version 2` |
| **Dominio VTP** | `vtp domain G15_technet` |
| **Contraseña VTP** | `vtp password secure2025` |
| **Vlan 13** | `vlan 13`<br>`name Ventas` |
| **Vlan 23** | `vlan 23`<br>`name Soporte` |
| **Vlan 33** | `vlan 33`<br>`name Gerencia` |
| **Vlan 43** | `vlan 43`<br>`name Seguridad` |
| **Trunk Fa0/1-4** | `interface range Fa0/1-4`<br>`switchport trunk encapsulation dot1q`<br>`switchport mode trunk`<br>`switchport trunk allowed vlan all` |
| **Guardar Configuración** | `wr` |

---

## MSW1

| Configuración | Comando |
| --- | --- |
| **Modo VTP** | `vtp mode client` |
| **Versión VTP** | `vtp version 2` |
| **Dominio VTP** | `vtp domain G15_technet` |
| **Contraseña VTP** | `vtp password secure2025` |
| **Trunk Fa0/1-6** | `interface range Fa0/1-6`<br>`switchport trunk encapsulation dot1q`<br>`switchport mode trunk`<br>`switchport trunk allowed vlan all` |
| **Guardar Configuración** | `wr` |

---

## MSW2

| Configuración | Comando |
| --- | --- |
| **Modo VTP** | `vtp mode client` |
| **Versión VTP** | `vtp version 2` |
| **Dominio VTP** | `vtp domain G15_technet` |
| **Contraseña VTP** | `vtp password secure2025` |
| **Trunk Fa0/1-5** | `interface range Fa0/1-5`<br>`switchport trunk encapsulation dot1q`<br>`switchport mode trunk`<br>`switchport trunk allowed vlan all` |
| **Guardar Configuración** | `wr` |

---

## MSW3

| Configuración | Comando |
| --- | --- |
| **Modo VTP** | `vtp mode client` |
| **Versión VTP** | `vtp version 2` |
| **Dominio VTP** | `vtp domain G15_technet` |
| **Contraseña VTP** | `vtp password secure2025` |
| **Trunk Fa0/1-5** | `interface range Fa0/1-5`<br>`switchport trunk encapsulation dot1q`<br>`switchport mode trunk`<br>`switchport trunk allowed vlan all` |
| **Guardar Configuración** | `wr` |

---

## MSW4

| Configuración | Comando |
| --- | --- |
| **Modo VTP** | `vtp mode client` |
| **Versión VTP** | `vtp version 2` |
| **Dominio VTP** | `vtp domain G15_technet` |
| **Contraseña VTP** | `vtp password secure2025` |
| **Trunk Fa0/1-6** | `interface range Fa0/1-6`<br>`switchport trunk encapsulation dot1q`<br>`switchport mode trunk`<br>`switchport trunk allowed vlan all` |
| **Guardar Configuración** | `wr` |

---

## MSW5

| Configuración | Comando |
| --- | --- |
| **Modo VTP** | `vtp mode client` |
| **Versión VTP** | `vtp version 2` |
| **Dominio VTP** | `vtp domain G15_technet` |
| **Contraseña VTP** | `vtp password secure2025` |
| **Trunk Fa0/1-4** | `interface range Fa0/1-4`<br>`switchport trunk encapsulation dot1q`<br>`switchport mode trunk`<br>`switchport trunk allowed vlan all` |
| **Guardar Configuración** | `wr` |

---

## MSW6

| Configuración | Comando |
| --- | --- |
| **Modo VTP** | `vtp mode client` |
| **Versión VTP** | `vtp version 2` |
| **Dominio VTP** | `vtp domain G15_technet` |
| **Contraseña VTP** | `vtp password secure2025` |
| **Trunk Fa0/1-6** | `interface range Fa0/1-6`<br>`switchport trunk encapsulation dot1q`<br>`switchport mode trunk`<br>`switchport trunk allowed vlan all` |
| **Guardar Configuración** | `wr` |

---

## MSW7

| Configuración | Comando |
| --- | --- |
| **Modo VTP** | `vtp mode client` |
| **Versión VTP** | `vtp version 2` |
| **Dominio VTP** | `vtp domain G15_technet` |
| **Contraseña VTP** | `vtp password secure2025` |
| **Trunk Fa0/1-4** | `interface range Fa0/1-4`<br>`switchport trunk encapsulation dot1q`<br>`switchport mode trunk`<br>`switchport trunk allowed vlan all` |
| **Guardar Configuración** | `wr` |

---

## MSW8

| Configuración | Comando |
| --- | --- |
| **Modo VTP** | `vtp mode client` |
| **Versión VTP** | `vtp version 2` |
| **Dominio VTP** | `vtp domain G15_technet` |
| **Contraseña VTP** | `vtp password secure2025` |
| **Trunk Fa0/1-2** | `interface range Fa0/1-2`<br>`switchport trunk encapsulation dot1q`<br>`switchport mode trunk`<br>`switchport trunk allowed vlan all` |
| **Trunk con Link Aggregation** | `interface range fa0/1-3`<br>`channel-group 2 mode desirable`<br>`interface port-channel 2`<br>`switchport trunk encapsulation dot1q`<br>`switchport mode trunk`<br>`switchport trunk allowed vlan all` |
| **Guardar Configuración** | `wr` |

---

## MSW9

| Configuración | Comando |
| --- | --- |
| **Modo VTP** | `vtp mode client` |
| **Versión VTP** | `vtp version 2` |
| **Dominio VTP** | `vtp domain G15_technet` |
| **Contraseña VTP** | `vtp password secure2025` |
| **Trunk Fa0/2-6** | `interface range Fa0/2-6`<br>`switchport trunk encapsulation dot1q`<br>`switchport mode trunk`<br>`switchport trunk allowed vlan all` |
| **Trunk con Link Aggregation** | `interface range fa0/4-6`<br>`channel-group 2 mode desirable`<br>`interface port-channel 2`<br>`switchport trunk encapsulation dot1q`<br>`switchport mode trunk`<br>`switchport trunk allowed vlan all` |
| **Guardar Configuración** | `wr` |

---

## MSW10

| Configuración | Comando |
| --- | --- |
| **Modo VTP** | `vtp mode client` |
| **Versión VTP** | `vtp version 2` |
| **Dominio VTP** | `vtp domain G15_technet` |
| **Contraseña VTP** | `vtp password secure2025` |
| **Trunk Fa0/2-6** | `interface range Fa0/2-6`<br>`switchport trunk encapsulation dot1q`<br>`switchport mode trunk`<br>`switchport trunk allowed vlan all` |
| **Trunk con Link Aggregation** | `interface range fa0/4-6`<br>`channel-group 1 mode desirable`<br>`interface port-channel 1`<br>`switchport trunk encapsulation dot1q`<br>`switchport mode trunk`<br>`switchport trunk allowed vlan all` |
| **Guardar Configuración** | `wr` |

---

## SW0

| Configuración | Comando |
| --- | --- |
| **Modo VTP** | `vtp mode client` |
| **Versión VTP** | `vtp version 2` |
| **Dominio VTP** | `vtp domain G15_technet` |
| **Contraseña VTP** | `vtp password secure2025` |
| **Trunk Fa0/1-5** | `interface range Fa0/1-5`<br>`switchport mode trunk` |
| **Guardar Configuración** | `wr` |




# **Verificación de Configuración**

- **Verificar VTP en los Switches**
  ```bash
  show vtp status
  ```

- **Verificar VLANs en cada Switch**
  ```bash
  show vlan brief
  ```

- **Verificar Trunking en los Switches**
  ```bash
  show interfaces trunk
  ```

- **Verificar el Estado de Spanning Tree (STP)**
  ```bash
  show spanning-tree
  ```

- **Verificar Configuración de LACP (Link Aggregation Control Protocol)**
  ```bash
  show etherchannel summary
  ```

- **Verificar Estado de las Interfaces**
  ```bash
  show interfaces status
  ```

- **Verificar Configuración de Enlaces Trunk en Específicos Puertos**
  ```bash
  show running-config interface fa0/1
  ```

- **Verificar la Configuración de Vlan en el Switch Raíz**
  ```bash
  show running-config
  ```

- **Verificar la Configuración de VTP y Dominios**
  ```bash
  show vtp password
  ```

- **Verificar el Estado de Enlaces de Agregación (Port-Channel)**
  ```bash
  show etherchannel 1
  ```

- **Verificar Configuración de la Interfaz de Puerto**
  ```bash
  show running-config interface port-channel 1
  ```

- **Verificar la Configuración de STP en el Switch Raíz**
  ```bash
  show spanning-tree vlan 1
  ```



### **Configuración**
#### **Pruebas de Conectividad (Ping)**
 - Ping en VLAN (Ventas)
![alt text](image-3.png)

 - Ping en VLAN (Soporte)
![alt text](image-2.png)

 - Ping en VLAN (Gerencia)
![alt text](image-4.png)

 - Ping en VLAN (Seguridad)
![alt text](image-5.png)