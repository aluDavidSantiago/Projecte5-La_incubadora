
# **T06: Configuració del domini**

## **Breu descripció**

### **Introducció**

Un cop tenim el domini creat, el següent pas és **desplegar i organitzar els objectes del directori actiu**: usuaris, grups i equips.  
També es treballarà amb **Unitats Organitzatives (OU)** per estructurar aquests objectes de manera lògica i administrable.

***

## **Procediment pràctic**

### **1. Crear una estructura d’unitats organitzatives**

Defineix i crea una estructura d’OU que sigui:

*   coherent amb una empresa real,
*   escalable,
*   fàcil d’administrar.

Cal **justificar** la decisió presa.

Exemple d’estructura típica:

    TransLogic
    │
    ├── Usuaris
    │   ├── Gestio
    │   ├── Magatzem
    │   └── Gerencia
    │
    ├── Equips
    │   └── PC1
    │
    └── Grups

***

### **2. Definir l'estructura de grups**

Crear els següents grups:

*   **gestio**
*   **magatzem**
*   **gerencia**
*   **personal**  
    *(Aquest últim ha d’incloure com a membres la resta de grups)*

Relació:

    personal
    ├── gestio
    ├── magatzem
    └── gerencia

***

### **3. Crear plantilles d'usuari per a cada grup**

Crear un usuari plantilla per:

*   **Gestio**
*   **Magatzem**
*   **Gerencia**

Cada plantilla ha de tenir:

*   Pertença automàtica al grup corresponent
*   Configuració de **carpeta personal (home folder)**

***

### **4. Crear usuaris de prova**

A partir de les plantilles, crear **un usuari de prova per cada grup**.

Exemples:

*   usuari\_gestio\_test
*   usuari\_magatzem\_test
*   usuari\_gerencia\_test

***

### **5. Aprovisionar un equip (PC1)**

Dins de l’OU **equips**, afegir l’objecte d’equip:

    PC1

***

### **6. Crear una màquina virtual Windows 11**

*   **4 GB de RAM**
*   Disc suficient per instal·lació (mínim 64 GB recomanat)
*   Xarxa configurada en **NAT**

Un cop instal·lat Windows 11:

1.  Assignar un nom coherent (PC1 si no existeix)
2.  Agregar l’equip al domini:

<!---->

    translogicXX.test

(XX és el vostre número de llista)

***

### **7. Comprovacions finals**

Iniciar sessió al client Windows 11 amb:

*   usuari de prova de **Gestio**
*   usuari de prova de **Magatzem**
*   usuari de prova de **Gerencia**

Verificar:

*   Pertença al domini
*   Accés correcte al perfil
*   Creació de la carpeta personal
*   Polítiques aplicades (si n’hi ha)

***

## **Materials i links de suport**

*   **UD6.AA3 Desplegament – Moodle 0224 SOX**

