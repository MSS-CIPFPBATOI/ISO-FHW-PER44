# Memoria de Montaje - Entorno de Pruebas (Tasca 0)

## 1. Introducción

El objetivo de esta tasca ha sido la preparación y configuración de un entorno de pruebas individualizado utilizando el hipervisor VirtualBox. Este entorno simula la arquitectura de red y los servicios que componen el proyecto grupal, permitiendo validar configuraciones antes de su despliegue definitivo.

## 2. Preparación del Host (Anfitrión)

Para asegurar el correcto funcionamiento de la virtualización, se han verificado los siguientes requisitos en el equipo físico:

- **Virtualización (VT-x/AMD-V):** Activada en la BIOS/UEFI.
  
- **Hipervisor:** Instalación de VirtualBox.

- **Recursos:** Verificación de disponibilidad de RAM (16GB) y almacenamiento SSD (1TB) para soportar la ejecución simultánea de los nodos de Proxmox y otros servicios.

## 3. Procedimiento de Montaje

El proceso de configuración se ha realizado siguiendo estos pasos:

1. **Directorio de trabajo:** Se han configurado las rutas de las máquinas virtuales en el disco principal para optimizar la velocidad de acceso a disco (I/O).

2. **Redes virtuales:** 
    - Se ha configurado un `NAT` para permitir el acceso a internet de las máquinas virtuales.
    - Se han definido las tarjetas de red internas (`intranet44`) necesarias para aislar el tráfico del clúster de Proxmox.

3. **Creación de Máquinas:** Creación de las estructuras de las máquinas virtuales (Nodos, NAS, Clientes, Firewall) aplicando los perfiles de hardware definidos en la documentación técnica del proyecto.

## 4. Problemas Encontrados y Soluciones

| Problema | Causa | Solución |
| :--- | :--- | :--- |
| **Error de aceleración HW** | VT-x/AMD-V desactivado en BIOS. | Acceder a BIOS y habilitar la virtualización. |
| **Permisos de acceso** | Problemas de lectura/escritura en rutas. | Configurar permisos de usuario para el grupo `vboxusers`. |

## 5. Conclusión
El entorno de pruebas individual está plenamente operativo, cumpliendo con los requisitos de capacidad y conectividad necesarios para el desarrollo de las tascas posteriores del proyecto ASIX ThinkLab.
