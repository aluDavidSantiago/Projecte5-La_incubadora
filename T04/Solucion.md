
***

# **T04: Instalación de Windows Server 2025 (VirtualBox)**

## **1. Configuración inicial de la Máquina Virtual**

### **1.1. Creación de la VM**

**Parámetros recomendados:**

*   **Nombre de la VM:** WS2025-Instalación
*   **RAM:** 8 GB
*   **CPU:** 2 procesadores
*   **Disco 1 (Sistema):** 32 GB
*   **Disco 2 (Datos):** 10 GB
*   **Red:**
    *   Adaptador 1: NAT
    *   Adaptador 2: Host-only

***

### **1.2. Procedimiento paso a paso (VirtualBox)**

1.  Abre **VirtualBox** y pulsa **New**.

2.  Introduce los datos iniciales:
    *   **Nombre:** WS2025-Instalación
    

3.  Configura:
    *   **Memoria:** 8192 MB
    *   **Procesadores:** 2

4.  En *Hard disk*, selecciona:
    *   **Create a virtual hard disk now** → 32 GB

5.  Después de crear la VM, abre **Settings**:
    *   **Storage → Controller SATA → Add Hard Disk → 10 GB**
    *   **Network → Adapter 1: NAT**
    *   **Network → Adapter 2: Host-only**

***

## **2. Instalación de Windows Server 2025 (Modo GUI)**

### **2.1. Arranque e inicio de la instalación**

1.  En VirtualBox, abre **Settings → Storage → Controller IDE → Choose Disk File**.
2.  Selecciona el ISO de Windows Server 2025.
3.  Inicia la máquina virtual.
4.  En la pantalla inicial, elige:
    *   **Language:** English (United States)
    *   **Time and currency format:** Spanish (Spain)
    *   **Keyboard:** Spanish
5.  Haz clic en **Install now**.

***

### **2.2. Selección de edición y método de instalación**

1.  En la lista de versiones, selecciona:

    **Windows Server 2025 Standard (Desktop Experience)**  
    *(modo con interfaz gráfica)*

2.  Acepta la licencia.

3.  Selecciona **Custom Installation**.

4.  Elige el disco de **32 GB** como disco del sistema.

***

### **2.3. Primera configuración**

1.  Espera a que finalice la instalación.
2.  Introduce una contraseña para el usuario **Administrator**.
3.  Inicia sesión.

***

## **3. Configuración del Sistema**

### **3.1. Cambiar el nombre del equipo**

1.  Abre **Server Manager**.
2.  Ve a **Local Server**.
3.  En *Computer Name*, selecciona **Change**.
4.  En este caso escribe:

<!---->

    DC10

*(Sustituye “xx” por tu número de lista.)*

5.  Reinicia la máquina.

***

## **4. Configuración de Red**

### **4.1. Comprobar adaptadores de red**

1.  Abre:

    **Control Panel → Network and Sharing Center → Change adapter settings**

2.  Deben aparecer:

*   **Ethernet 1:** NAT
*   **Ethernet 2:** Host-only


***

## **5. Actualización del Servidor**

### **5.1. Ejecutar Windows Update**

1.  Abre **Settings → Windows Update**.
2.  Haz clic en **Check for updates**.
3.  Instala todas las actualizaciones disponibles.
4.  Reinicia si se solicita.

***

### **5.2. Pausar actualizaciones**

1.  En **Windows Update**, selecciona **Pause updates**.
2.  Elige el máximo tiempo permitido.

***

## **6. Comparación con los requisitos oficiales de Microsoft**

| **Componente** | **Requisito mínimo**     | **Configuración VM**   | **Comentario**                |
| -------------- | ------------------------ | ---------------------- | ----------------------------- |
| CPU            | 1.4 GHz 64‑bit           | 2 CPU                  | Correcto (superior al mínimo) |
| RAM            | 2 GB (Core) – 4 GB (GUI) | 8 GB                   | Muy adecuado                  |
| Disco          | 32 GB                    | 32 GB SO + 10 GB datos | Aceptable                     |
| Red            | Adaptador Ethernet       | NAT + Host‑only        | Cumple y añade redundancia    |

### **Conclusión**

La configuración de la VM supera los requisitos mínimos de Microsoft y es totalmente adecuada para prácticas y entornos de laboratorio.


