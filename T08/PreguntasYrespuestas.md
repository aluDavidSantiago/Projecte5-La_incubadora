Verificar el funcionamiento de un programa antimalware

¿Cómo se puede desactivar temporalmente el detector del navegador y el de Windows para descargar el archivo EICAR?
Para desactivar la protección del navegador Microsoft Edge se debe acceder a Configuración → Privacidad, búsqueda y servicios y desactivar la opción Microsoft Defender SmartScreen, que bloquea descargas sospechosas.
Para desactivar el antivirus de Windows, se accede a Seguridad de Windows → Protección antivirus y contra amenazas → Administrar la configuración y se desactiva la protección en tiempo real.

¿El antimalware detecta el archivo EICAR una vez activada la protección?
Sí. Al volver a activar la protección en tiempo real, Windows Defender detecta inmediatamente el archivo EICAR y lo elimina, mostrando una alerta en el historial de protección.

¿Detecta el antimalware el archivo EICAR comprimido en formato ZIP?
Sí, el archivo EICAR comprimido en formato ZIP es detectado por el antivirus.

¿Detecta el antimalware el archivo EICAR comprimido en formato TAR?
Sí, el antivirus también detecta el archivo EICAR cuando está comprimido en formato TAR.

¿Detecta el antimalware el archivo EICAR comprimido en formato 7ZIP?
Sí, el archivo EICAR comprimido en formato 7ZIP es detectado correctamente por el antimalware.

Sistemas de protección Windows 11

¿Qué protecciones incorpora Windows 11 en la sección “Protección antivirus y contra amenazas”?
Windows 11 incluye protección en tiempo real, protección basada en la nube, envío automático de muestras, protección contra alteraciones, diferentes tipos de análisis (rápido, completo y personalizado) y un historial de protección donde se muestran las amenazas detectadas.

¿Qué opciones tenemos en “Control de aplicaciones y navegador”?
En esta sección se encuentran opciones como Microsoft Defender SmartScreen para proteger la navegación web, la protección contra aplicaciones potencialmente no deseadas, la protección contra exploits, el aislamiento del núcleo y la integridad de memoria.

¿Qué opciones específicas existen para la protección contra ransomware en Windows 11?
Windows 11 ofrece el acceso controlado a carpetas, que evita modificaciones no autorizadas en carpetas importantes, la posibilidad de permitir aplicaciones concretas y opciones de recuperación de archivos mediante copias de seguridad como OneDrive.

Prueba práctica de protección contra ransomware (PSRansom)

¿Qué ocurre al ejecutar el script PSRansom con la protección contra ransomware desactivada?
Los archivos de la carpeta Documentos son cifrados y se crea un archivo llamado READ_ME.txt que contiene la clave de recuperación.

¿Es posible recuperar los archivos cifrados?
Sí, al tratarse de un ransomware de prueba, el propio script permite descifrar los archivos utilizando la clave indicada.

¿Qué sucede al ejecutar el script con la protección contra ransomware activada?
Windows Defender bloquea el intento de cifrado, los archivos no se ven afectados y se genera una alerta de seguridad.

Ataques de ransomware: WannaCry

¿Por qué WannaCry se propagó tan rápidamente?
Porque explotaba una vulnerabilidad en el protocolo SMB de Windows que permitía propagarse automáticamente por la red sin necesidad de interacción del usuario.

¿Qué vulnerabilidad utilizaba WannaCry y cuál es su CVE?
WannaCry utilizaba la vulnerabilidad CVE-2017-0144, relacionada con el exploit EternalBlue, considerada de gravedad crítica.

¿Se debe pagar el rescate solicitado por WannaCry? ¿Por qué?
No se recomienda pagar el rescate, ya que no garantiza la recuperación de los archivos y fomenta la actividad delictiva.

¿Qué medidas se pueden aplicar para prevenir un ataque de ransomware?
Mantener el sistema actualizado, realizar copias de seguridad periódicas, usar antivirus actualizado, limitar servicios innecesarios y concienciar a los usuarios.

¿Qué medidas se deben aplicar si ya se ha sufrido un ataque de WannaCry?
Aislar el equipo infectado, no pagar el rescate, restaurar copias de seguridad si existen, analizar el sistema y aplicar las actualizaciones de seguridad necesarias.
