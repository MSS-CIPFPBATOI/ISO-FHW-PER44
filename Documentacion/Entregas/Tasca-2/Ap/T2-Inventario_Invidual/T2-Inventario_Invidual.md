# INVENTARIO INDIVIDUAL

## EQUIPO DE CASA (HOST)

### EQUIPO

---

| Componente | Especificación |
| ---- | ---- |
| **CPU** | Intel Core i5-11400F (11th Gen) @ 2.60GHz |
|   **GPU**   |   GeForce RXT 5060 8GB     |
| **RAM** | 16 GB |
| **Almacenamiento** | 1000 GB M.2 |
| **EFI** | Activada |
| **Red** | Subred: 192.168.44.0/24 |

---

---

### PERIFERICOS

---

| PERIFERICO | CANTIDAD | ENLACE PROVEEDOR |
|------------|----------|------------------|
|   RATONES  |     1    |n/a               |
|  TECLADOS  |     1    |n/a               |
| MONITORES  |     2    |n/a               |

---

---

<br>

## SERVIDORES 

### NODOS PROXMOX

Se ha planificado un clúster de **3 nodos Proxmox** para proporcionar alta disponibilidad y redundancia. Los nodos `Proxmox1`, `Proxmox2` y `Proxmox3` seguirán la misma configuración base para garantizar la homogeneidad del clúster.

|  Nodo    | CPU (vCPU) | RAM | Disco | Justificación (Respecto Proxmox) |
| -------- | ---------- | --- | ----- | -------------------------------- |
| Proxmox1 |     1      | 4GB |  vdi  | Nodo principal. Encargado de la gestión de la hipervisoría y recursos del clúster inicial. |
| Proxmox2 |     1      | 4GB |  vdi  | Nodo secundario. Necesario para redundancia y migración de máquinas virtuales en caso de fallo del nodo 1. |
| Proxmox3 |     1      | 4GB |  vdi  | Nodo terciario. Completa el clúster para asegurar el quórum y estabilidad de servicios críticos. |

---

---

### TRUENAS

| SISTEMA | CPU (vCPU) | RAM | Disco | Justificación |
| :--- | :--- | :--- | :--- | :--- |
| TrueNAS44 | 1 | 4GB | vdi | Servidor NAS para almacenamiento centralizado y gestión de datos. |

---

---

<br>

## CLIENTES

| Cliente | CPU (vCPU) | RAM | Disco | Justificación |
| :--- | :--- | :--- | :--- | :--- |
| Win11Cli44 | 2 | 4GB | vdi | Cliente Windows 11 para pruebas de entorno de usuario. |
| DualCli44 | 2 | 4GB | vdi | Cliente Dual para pruebas de interoperabilidad de sistemas. |

---

---

<br>

## COMUNICACIONES

| SISTEMA | CPU (vCPU) | RAM | Disco | Justificación |
| :--- | :--- | :--- | :--- | :--- |
| OPNsense44 | 1 | 2GB | vdi | Firewall perimetral y gestión de seguridad de red. |
| MikroTik44 | 1 | 1GB | vdi | Router principal para gestión de rutas y servicios de red. |
| SvrDeb44 | 1 | 2GB | vdi | Servidor de servicios de infraestructura y enrutamiento secundario. |

---

---

