
# **T05: Instal·lació del domini**

## **Breu descripció**

### **Introducció**

Com a continuació de la tasca anterior, cal desplegar el **Directori Actiu** sobre la màquina virtual amb l’objectiu de practicar per al futur desplegament al client.  
A més, aquest procediment servirà com a **prova de concepte (PoC)** per mostrar als responsables de *TransLògic S.A.* i ajustar les configuracions a les necessitats reals del client.

***

## **Procediment a documentar**

### **1. Instal·lar els rols necessaris**

Instal·la els rols del servidor relacionats amb:

*   **Active Directory Domain Services (AD DS)**
*   Altres rols o característiques que el procediment requereixi

***

### **2. Crear un domini nou en un bosc nou**

*   Crear un domini amb el nom:

<!---->

    translogicXX.test

*(On **XX** és el vostre número de llista.)*

*   Això implica desplegar:
    *   Un **bosc nou (new forest)**
    *   Un **domini nou**
    *   Sense dependències amb infraestructures prèvies

***

### **3. Establir el nivell funcional del bosc**

*   Configura el **Forest Functional Level (FFL)** i el **Domain Functional Level (DFL)** a:

<!---->

    Windows Server 2025

***

### **4. Promocionar el servidor a controlador de domini (DC)**

El procés ha d’incloure:

*   Configuració del rol AD DS
*   Elecció del nom del domini
*   Definició del mode del bosc
*   Establiment de la contrasenya del *Directory Services Restore Mode (DSRM)*

📌 **Important:** Cal documentar la **pantalla resum** que apareix abans de finalitzar la promoció.

***

### **5. Generar i guardar l’script PowerShell**

Windows Server genera automàticament un script PowerShell que permet replicar el desplegament.  
Cal:

*   Guardar l’script `.ps1` al servidor
*   Afegir-lo al vostre repositori del projecte

***

### **6. Copiar l’script al repositori**

Podeu transferir l’arxiu `.ps1` mitjançant qualsevol d’aquests mètodes:

*   **USB**
*   Enviant-lo per **Internet** (correu, Drive, FileTransfer, etc.)
*   Copiant-lo via **scp**  
    *(Cal instal·lar el servei OpenSSH a Windows Server per poder utilitzar-lo.)*

***

## **Materials i links de suport**

*   **Guia UD6.AA3 Instal·lació DC – Moodle SOX**

