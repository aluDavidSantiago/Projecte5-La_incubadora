Guía de la práctica 1: Verificación del funcionamiento del antimalware mediante el archivo EICAR
1. Introducción
En esta práctica se verifica el funcionamiento del antivirus del sistema operativo utilizando el archivo de prueba EICAR.
EICAR no es un malware real, sino un fichero estándar diseñado para comprobar que las soluciones antivirus responden correctamente ante amenazas sin poner en riesgo el sistema.
El objetivo es observar cómo actúan las diferentes capas de protección del navegador, del sistema operativo y del propio antivirus ante la descarga, extracción y manipulación del archivo EICAR en distintos formatos.
2. Advertencias previas y consideraciones

Este ejercicio se debe realizar únicamente en una máquina virtual o entorno de pruebas.
No debe utilizarse malware real para esta actividad. El archivo EICAR es un estándar seguro.
El antivirus detectará y eliminará los ficheros en cuanto lo permitamos. Es normal que el archivo desaparezca automáticamente al activarse la protección.
Algunas capas de protección deben desactivarse temporalmente para poder descargar y manipular el archivo; deben reactivarse siempre después de cada fase.
No ejecutar ni abrir el archivo EICAR; únicamente trabajarlo a nivel de descarga, extracción y compresión.


3. Procedimiento paso a paso
3.1. Desactivar SmartScreen del navegador y protección basada en la reputación

Abrir Seguridad de Windows.
Acceder a "Control de aplicaciones y navegador".
Dentro de “Protección basada en la reputación”, desactivar temporalmente:

Comprobar aplicaciones y archivos.
SmartScreen para Microsoft Edge.
Bloqueo de aplicaciones potencialmente no deseadas (PUA).


Cerrar la ventana.

3.2. Desactivar temporalmente Windows Defender

Abrir Seguridad de Windows.
Acceder a “Protección antivirus y contra amenazas”.
Seleccionar “Administrar configuración”.
Desactivar temporalmente:

Protección en tiempo real.
Protección basada en la nube.
Envío automático de muestras.


Si el sistema reactiva automáticamente las opciones, desactivar también “Protección contra alteraciones (Tamper Protection)”.

3.3. Descargar el archivo de prueba EICAR

Acceder a https://www.eicar.org.
Localizar la sección de archivos de prueba.
Descargar el archivo comprimido eicar_com.zip.
Guardarlo en el escritorio de la máquina virtual.

Nota: Si el navegador bloquea la descarga, comprobar que SmartScreen está desactivado. Si el archivo se abre como texto en el navegador, copiar su contenido manualmente en un archivo llamado eicar.com.
3.4. Extraer el archivo EICAR

Con el antivirus desactivado, hacer clic derecho sobre eicar_com.zip.
Seleccionar "Extraer aquí" o "Extraer en carpeta".
Confirmar que aparece el archivo eicar.com.

3.5. Reactivar Windows Defender

Volver a Seguridad de Windows.
Activar nuevamente:

Protección en tiempo real.
Protección basada en la nube.
Envío automático de muestras.


Activar también “Protección contra alteraciones”.

3.6. Comprobar la detección del archivo EICAR

Abrir la carpeta donde se encuentra eicar.com.
Esperar unos segundos.
Windows Defender debería detectar el archivo y eliminarlo automáticamente.
Para confirmar la detección, acceder a:

Seguridad de Windows → Protección antivirus y contra amenazas → Historial de protección.


Registrar el mensaje mostrado por el antivirus.

3.7. Prueba con archivos comprimidos en distintos formatos
3.7.1 Preparación de los archivos

Desactivar de nuevo la protección en tiempo real del antivirus.
Restaurar el archivo eicar.com desde la cuarentena si ha sido eliminado, o repetir la extracción desde el ZIP original.
Crear los formatos siguientes:

ZIP: clic derecho → Enviar a → Carpeta comprimida.
TAR: clic derecho → 7-Zip → Añadir al archivo → Formato TAR.
7Z: clic derecho → 7-Zip → Añadir al archivo → Formato 7Z.



3.7.2 Reactivar el antivirus y comprobar detecciones

Volver a activar la protección en tiempo real.
Abrir cada archivo comprimido y observar si el antivirus lo detecta.
Si no lo detecta al abrir, extraerlo y comprobar si lo detecta en la extracción.
Registrar el comportamiento de cada formato.

Resultados esperados:

ZIP suele detectarse de forma inmediata.
TAR puede detectarse al abrir o al extraer.
7Z puede requerir extracción para que el antivirus actúe.


4. Preguntas y respuestas correspondientes a esta primera práctica
Estas son las preguntas que están directamente relacionadas con la primera actividad (detección antimalware y protecciones de Windows 11). Las preguntas sobre WannaCry pertenecen a otra práctica y no se incluyen aquí.
Pregunta 1. ¿Qué protecciones incorpora Windows 11 en la sección “Protección antivirus y contra amenazas”?
Respuesta:
Incluye protección en tiempo real, protección basada en la nube, envío automático de muestras, historial de protección, distintos tipos de análisis (rápido, completo, desconectado y personalizado), protección contra alteraciones (Tamper Protection) y protección contra ransomware mediante acceso controlado a carpetas y copia de seguridad con OneDrive.
Pregunta 2. ¿Qué opciones tenemos en “Control de aplicaciones y navegador”?
Respuesta:
Incluye Smart App Control (en instalaciones nuevas), protección basada en reputación (SmartScreen para aplicaciones y archivos, SmartScreen para Microsoft Edge y para Microsoft Store), bloqueo de aplicaciones potencialmente no deseadas, protección contra vulnerabilidades (Exploit Protection) y opciones de aislamiento del núcleo.
Pregunta 3. ¿Qué incluye la protección contra ransomware en Windows 11?
Respuesta:
Incluye el mecanismo de Acceso controlado a carpetas, que impide que aplicaciones no autorizadas modifiquen archivos en ubicaciones protegidas, así como la integración con OneDrive para mantener copias de respaldo de los archivos y permitir su recuperación en caso de ataque.
