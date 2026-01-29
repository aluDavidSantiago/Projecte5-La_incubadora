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

## Notas importantes:
*   El servidor FTP/SFTP se comunicará **solo** por la red Host-Only, evitando exposición innecesaria.
*   Mantén las máquinas actualizadas antes de avanzar.

***

# FASE 2: Verificación de la conectividad entre servidor y cliente

## Introducción

En esta fase comprobamos que Ubuntu Server y Windows 11 pueden comunicarse a través de la red Host-Only configurada en las máquinas virtuales. Esta verificación es necesaria antes de instalar el servicio FTP/SFTP.

## Objetivo

*   Identificar la IP del servidor Ubuntu.
*   Comprobar conectividad desde Windows mediante ping.
*   Validar que la red Host-Only funciona correctamente.

***

## PASO 1 — Comprobar interfaces de red en Ubuntu Server

### Comando ejecutado

    ip a

### Explicación del comando

*   **ip**: herramienta moderna para gestionar la red en Linux.
*   **a** (addr): muestra todas las interfaces de red y sus direcciones IP.  
    Sirve para identificar la IP asignada al adaptador Host-Only del servidor (en tu imagen es **192.168.56.101**).

***

## PASO 2 — Verificar conectividad desde Windows 11 hacia Ubuntu Server

### Comando ejecutado (PowerShell)

    ping 192.168.56.101

### Explicación del comando

*   **ping**: herramienta para comprobar si un equipo responde en red.
*   **192.168.56.101**: IP del servidor Ubuntu obtenida en el paso anterior.  
    Permite verificar que ambas máquinas se encuentran en la misma red Host-Only y pueden comunicarse.

***

## Notas importantes

*   Si el ping falla, revisar que ambos adaptadores Host-Only están activados en las dos VM.
*   El adaptador NAT no interviene en esta prueba, solo se usa para acceso a internet.
*   Esta comprobación es obligatoria antes de instalar FTP, ya que el cliente debe alcanzar al servidor.

***

¿Confirmas que está correcto? Si sí, pasamos a la siguiente fase.
