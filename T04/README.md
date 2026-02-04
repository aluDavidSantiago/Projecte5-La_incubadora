
# T04: Instal·lació Windows Server 2025

## **Breu descripció**

### **Introducció al cas**

Després del nostre assessorament, **TransLògic S.A.** ens encarrega el desplegament dels seus **Windows Server 2025**.  
Per aquest motiu, haurem de desplegar diverses màquines virtuals i, amb l’objectiu de ser eficients i seguir bones pràctiques, realitzarem una **instal·lació de prova** que servirà tant per aprendre els procediments com per elaborar una **guia d’instal·lació**, que ha de proporcionar documentació base per a la posterior implantació als sistemes del client.

## **Procediment**

*   Crear una màquina virtual amb:
    *   **8 GB de RAM**
    *   **2 processadors**
    *   **Dos discos:**
        *   Disc principal de **32 GB** (on s’instal·larà el SO)
        *   Disc secundari de **10 GB**
    *   **Dues interfícies de xarxa**:
        *   una en **xarxa NAT (no NAT)**
        *   la segona en **host-only**

*   Instal·lar **Windows Server 2025** en mode **GUI**, amb:
    *   **Idioma US**
    *   **Configuració i teclat en espanyol**

*   Canviar el nom de l’equip a **DCxx** (xx és el número de llista).

*   Actualitzar la màquina virtual i, un cop fet, **pausar les actualitzacions** el màxim de temps possible.

***

## **Contingut de la guia**

### **Comparació de requisits**

Compara la configuració de la màquina virtual definida a l’apartat anterior amb els requisits indicats per Microsoft.  
**Són coherents?**

### **Documentació**

Documenta els diversos procediments de la instal·lació amb:

*   Captures de pantalla
*   Observacions  
    El format a utilitzar ha de ser **Markdown**.

***

## **Materials i links de suport**

*   **UD.6. AA2. Instal·lació Windows Server 2025** – Moodle (0224 Sistemes Operatius en Xarxa)
*   **Requisitos de hardware para Windows Server – Microsoft Learn:**  
    <https://learn.microsoft.com/es-es/windows-server/get-started/hardware-requirements?tabs=cpu&pivots=windows-server-2025>

***

Si vols, també puc convertir-ho en una plantilla completa per a una guia final amb seccions, o preparar l’esquelet de la documentació amb espais per capturas, notes i procediments.
