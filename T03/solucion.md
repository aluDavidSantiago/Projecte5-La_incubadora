# INTRODUCCIÓN BREVE

En este proyecto configuraremos un entorno de laboratorio compuesto por **Ubuntu Server** como servidor FTP/SFTP y **Windows 11** como cliente. Antes de comenzar con la teoría o las configuraciones, es imprescindible definir las **máquinas virtuales**, sus **recursos mínimos** y la **configuración de red** que permitirá la comunicación entre ambos sistemas.

***

# PASO 0: Preparación de las Máquinas Virtuales

A continuación se detallan los requisitos mínimos y la configuración base de red necesaria para garantizar que el laboratorio funcione correctamente.

## Objetivo del Paso 0

*   Crear dos máquinas virtuales funcionales.
*   Asignar recursos mínimos para Ubuntu Server y Windows 11.
*   Configurar los adaptadores de red en **NAT + Adaptador solo-anfitrión** para permitir:
    *   Acceso a internet.
    *   Comunicación directa entre servidor y cliente.

***

## 1. Máquina Virtual: Ubuntu Server (Servidor FTP/SFTP)

### Requisitos mínimos recomendados

*   **CPU:** 1–2 núcleos
*   **RAM:** 2 GB
*   **Almacenamiento:** 20 GB
*   **SO:** Ubuntu Server LTS (22.04 o 24.04 recomendado)
*   **Red:**
    *   **Adaptador 1:** NAT
    *   **Adaptador 2:** Adaptador solo-anfitrión (Host-Only)

### Explicación de la red

*   **NAT:** permite que Ubuntu Server tenga acceso a internet (actualizaciones, paquetes).
*   **Host-Only:** crea una red privada interna entre el servidor y el cliente Windows 11.

***

## 2. Máquina Virtual: Windows 11 (Cliente FTP/SFTP)

### Requisitos mínimos recomendados

*   **CPU:** 2 núcleos
*   **RAM:** 4 GB
*   **Almacenamiento:** 64 GB
*   **SO:** Windows 11 Pro o Home
*   **Red:**
    *   **Adaptador 1:** NAT
    *   **Adaptador 2:** Adaptador solo-anfitrión (Host-Only)

### Explicación de la red

*   Igual que en Ubuntu:
    *   NAT para acceso a internet.
    *   Host-Only para comunicación directa con el servidor FTP/SFTP.

***

## Notas importantes del Paso 0
*   El servidor FTP/SFTP se comunicará **solo** por la red Host-Only, evitando exposición innecesaria.
*   Mantén las máquinas actualizadas antes de avanzar.

***

