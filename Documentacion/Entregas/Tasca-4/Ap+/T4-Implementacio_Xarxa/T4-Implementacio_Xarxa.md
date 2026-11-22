# Documentación T4 - Implementación de Red (Ap+)

## Introducción
Este documento detalla la implementación física y lógica del entorno de red individual para el proyecto ASIX ThinkLab, siguiendo el diseño en VirtualBox y utilizando la subred `192.168.44.0/24`.

## Esquema de Direccionamiento IP
Se ha establecido el siguiente rango de IPs para organizar los distintos roles del sistema:

| Rango de IP | Rol |
| :--- | :--- |
| `192.168.44.1 - 10` | Enrutadores y dispositivos de comunicación |
| `192.168.44.100 - 150` | Clientes |
| `192.168.44.160 - 170` | Nodos Proxmox |
| `192.168.44.180 - 200` | Servidores |

---

## Análisis de Máquinas

### Comunicaciones (Enrutadores)

| Máquina | Rol | Imagen |
| :--- | :--- | :--- |
| **OPNsense** | Firewall perimetral y gestión de seguridad. | ![OPNsense](Recursos/OpenSense.png) |
| **MikroTik** | Router principal de la red para gestión de rutas. | ![MikroTik](Recursos/MikroTik.png) |
| **DebianSvr** | Servidor de infraestructura y enrutamiento secundario. | ![DebianSvr](Recursos/DebianSvr.png) |

### Clientes

| Máquina | Rol | Imagen |
| :--- | :--- | :--- |
| **Windows 11** | Cliente para pruebas de entorno de usuario. | ![Win11](Recursos/Windows11.png) |
| **Dual Boot** | Cliente para pruebas de interoperabilidad. | ![DualBoot](Recursos/DualBoot.png) |

### Proxmox (Nodos)

| Máquina | Rol | Imagen |
| :--- | :--- | :--- |
| **Proxmox 1** | Nodo principal de hipervisoría. | ![Prox1](Recursos/Prox1N44.png) |
| **Proxmox 2** | Nodo secundario para redundancia. | ![Prox2](Recursos/Prox2N44.png) |
| **Proxmox 3** | Nodo terciario para estabilidad del clúster. | ![Prox3](Recursos/Prox3N44.png) |

### Servidores

| Máquina | Rol | Imagen |
| :--- | :--- | :--- |
| **TrueNAS** | Almacenamiento centralizado (NAS). | ![TrueNAS](Recursos/TrueNAS.png) |
| **Win Server** | Active Directory. | ![WinServer](Recursos/WinServer25.png) |
