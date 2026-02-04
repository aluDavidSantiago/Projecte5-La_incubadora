
# **T06: Configuración del dominio (Active Directory)**

**Alumno nº 10**  
**Dominio:** `translogic10.test`  
**Servidor:** `DC10`  
**Cliente:** `PC1` (Windows 11)

***

# **1. Breve descripción**

En esta práctica se configurará la estructura inicial del dominio creado en la tarea anterior. Se organizarán las unidades organizativas (OU), grupos, plantillas de usuario, usuarios de prueba y un equipo cliente unido al dominio.  
Todo el proceso se realiza en el entorno **Active Directory Domain Services** del dominio `translogic10.test`.

***

# **2. Introducción**

Una vez creado el dominio, el siguiente paso en su despliegue es organizar correctamente sus objetos:

*   OU (estructura lógica y administrativa)
*   Grupos de seguridad
*   Plantillas (templates) de usuario
*   Carpetas personales (home folder)
*   Usuarios de prueba
*   Equipos unidos al dominio

El objetivo es preparar un entorno organizado, limpio y escalable para TransLògic S.A, siguiendo buenas prácticas de administración.

***

# **3. Estructura de Unidades Organizativas (OU)**

> **Cubre rúbrica: 2 puntos (Estructura + justificació)**

## **3.1. Estructura propuesta**

    translogic10.test
    │
    ├── Empreses
    │   ├── Gestio
    │   ├── Magatzem
    │   ├── Gerencia
    │   └── Personal
    │
    └── Equips

Se crean:

*   OU **Empreses** → contiene los usuarios y grupos corporativos.
*   Dentro de ella:
    *   **Gestio**
    *   **Magatzem**
    *   **Gerencia**
    *   **Personal** (OU global donde se centralizan usuarios del dominio)
*   OU **Equips** → contiene equipos como `PC1`.

## **3.2. Justificación**

La estructura propuesta sigue un modelo **funcional**, adecuado para empresas con diferentes áreas de trabajo.  
La OU raíz **Empreses** permite delegar administración si fuera necesario, y cada OU específica representa un departamento con usuarios y plantillas diferenciadas.  
La OU **Equips** separa los equipos del dominio de los usuarios, mejorando la administración y la aplicación de GPO específicas.

***

# **4. Creación de grupos de seguridad**

> **Cubre rúbrica: 2 puntos (grupos gestio, magatzem, gerencia, personal)**

Desde **Active Directory Users and Computers (ADUC)**:

Crear en OU *Empreses*:

1.  Grupo **gestio** → type: Security, scope: Global
2.  Grupo **magatzem** → Security, Global
3.  Grupo **gerencia** → Security, Global
4.  Grupo **personal** → Security, Global

## **4.1. Pertinença obligatoria**

Los tres grupos principales deben ser miembros de **personal**:

*   gestio → member of: personal
*   magatzem → member of: personal
*   gerencia → member of: personal

***

# **5. Carpeta Home (Carpeta personal)**

> **Cubre rúbrica: 1 punto permisos compartidos + 2 puntos permisos NTFS**

## **5.1. Creación del recurso compartido en el 2º disco**

Ruta recomendada:

    D:\Homes

Clic derecho → **Properties → Sharing → Advanced Sharing**

*   Share name: `homes`
*   Permisos de recurso compartido (Share Permissions):
    *   Administrators → Full Control
    *   Users → Remove (no deben tener permisos globales)
    *   Everyone → Remove

## **5.2. Permisos NTFS (Security → Advanced)**

Dentro de `D:\Homes`:

Eliminar:

*   Users
*   Authenticated Users (si aparece)

Crear:

*   CREATOR OWNER → Full Control (solo subcarpetas y archivos)
*   Administrators → Full Control
*   SYSTEM → Full Control

Aplicar correctamente **“This folder only”** cuando sea necesario según la estructura.  
Este requisito es clave para obtener los **2 puntos completos** de la rúbrica.

## **5.3. Configuración de Home Folder en las plantillas**

La ruta para los usuarios será:

    \\DC10\homes\%username%

***

# **6. Plantillas de usuario**

> **Cubre rúbrica: 1 punto (totes fetes i començant amb \_) + 1 punto por cada plantilla**

Crear en la OU correspondiente:

*   `_gestio`
*   `_magatzem`
*   `_gerencia`

## Todas deben cumplir:

1.  Nombre comenzando por `_`
2.  Pertenencia automática a:
    *   su grupo propio (gestio/magatzem/gerencia)
    *   el grupo **personal**
3.  Carpeta personal configurada:
    *   En la pestaña **Profile → Home folder**:
            Connect: H:
            To: \\DC10\homes\%username%

### IMPORTANTE

Cada plantilla debe estar **en la OU correspondiente**, no todas en una misma OU.

***

# **7. Creación de usuarios de prueba**

> **Cubre rúbrica: 1 punto**

Crear un usuario en cada OU:

*   `u_gestio`
*   `u_magatzem`
*   `u_gerencia`

Cada uno debe:

*   Crearse usando la opción **Copy** desde su plantilla correspondiente.
*   Heredar:
    *   Pertenencia al grupo
    *   Carpeta personal
    *   Ruta de Home Folder

***

# **8. Preaprovisionar el equipo PC1**

> **Cubre rúbrica: 1 punto**

En OU **Equips**:

1.  Clic derecho → **New → Computer**
2.  Nombre:
        PC1
3.  Marcar:
    *   Allow this computer to join the domain
    *   Assign user: Administrator (opcional)

***

# **9. Creación y unión al dominio de la máquina Windows 11**

> **Cubre rúbrica: 2 puntos**

## **9.1. Crear VM con Windows 11**

*   4 GB RAM
*   1 CPU (o más)
*   Disco suficiente (mínimo 64 GB recomendado)
*   Red: **NAT**
*   Instalar normalmente
*   Configurar usuario local temporal

## **9.2. Unir el PC1 al dominio**

En Windows 11:

1.  Abrir **Settings → System → About → Rename this PC (advanced)**
2.  Seleccionar **Domain**
3.  Escribir:

<!---->

    translogic10.test

4.  Usar credenciales de dominio:
        Administrator
5.  Reiniciar.

> **Evidencia perfecta:**  
> Captura de Windows 11 indicando “Domain: translogic10.test”.

***

# **10. Prueba de acceso con los tres usuarios**

> **Cubre rúbrica: 2 puntos**

En `PC1`:

1.  Cerrar sesión del usuario local
2.  Probar login uno por uno:
    *   `u_gestio`
    *   `u_magatzem`
    *   `u_gerencia`
3.  Verificar en cada sesión:
    *   Inicio correcto
    *   Aparece el disco **H:** (home folder)
    *   Acceso correcto a su carpeta individual
    *   No acceso a otras carpetas


