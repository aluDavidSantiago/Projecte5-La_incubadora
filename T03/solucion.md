Aquí la tienes, Santiago:  
**tu guía completa en Markdown**, limpia, ordenada y lista para entregar o copiar donde necesites.  
Sin teoría, solo pasos.  
Adaptada exactamente a tu práctica.

***

# # Práctica Completa FTP y SFTP

## Transferencia de archivos, chroot, pruebas y capturas

***

# ## Datos del entorno

    Usuario FTP: ftpuser
    Usuario SFTP: sftpuser
    IP servidor: 192.168.56.101
    Archivo local: C:\Users\Usuario\Desktop\archivo.txt

***

# # FASE 1 — Instalación básica de FTP (vsftpd)

```bash
sudo apt update
sudo apt install -y vsftpd
sudo systemctl enable --now vsftpd
sudo adduser ftpuser
```

***

# # FASE 2 — Configuración completa de vsftpd

```bash
sudo mkdir -p /home/ftpuser/ftp
sudo chown root:root /home/ftpuser
sudo chmod 755 /home/ftpuser
sudo chown ftpuser:ftpuser /home/ftpuser/ftp
sudo nano /etc/vsftpd.conf
```

Contenido requerido:

    listen=YES
    listen_ipv6=NO
    anonymous_enable=NO
    local_enable=YES
    write_enable=YES
    local_umask=022

    chroot_local_user=YES
    allow_writeable_chroot=YES

    pasv_enable=YES
    pasv_min_port=40000
    pasv_max_port=40010
    pasv_address=192.168.56.101

    user_sub_token=$USER
    local_root=/home/$USER/ftp

Abrir puertos:

```bash
sudo ufw allow 21/tcp
sudo ufw allow 40000:40010/tcp
sudo systemctl restart vsftpd
```

***

# # FASE 3 — Prueba desde Windows (CMD)

En CMD:

```cmd
cd C:\Users\Usuario\Desktop
ftp 192.168.56.101
```

Login → luego:

```cmd
put archivo.txt
bye
```

***

# # FASE 4 — Prueba FTP con FileZilla + Wireshark

### FileZilla

    Protocolo: FTP
    Host: 192.168.56.101
    Encriptación: FTP simple
    Modo: Normal
    Usuario: ftpuser

Subir `archivo.txt`.

### Wireshark

Interfaz Host-Only.  
Filtro:

    ftp.request.command == "USER" || ftp.request.command == "PASS"

Capturar usuario/contraseña en claro.

***

# # FASE 5 — Instalación y preparación de SFTP

```bash
sudo apt install -y openssh-server
sudo adduser sftpuser
sudo mkdir -p /home/sftpuser/upload
sudo chown root:root /home/sftpuser
sudo chmod 755 /home/sftpuser
sudo chown sftpuser:sftpuser /home/sftpuser/upload
```

***

# # FASE 6 — Configuración del chroot seguro en SFTP

```bash
sudo nano /etc/ssh/sshd_config
```

Modificar:

    Subsystem sftp internal-sftp

Añadir:

    Match User sftpuser
        ChrootDirectory /home/sftpuser
        ForceCommand internal-sftp
        X11Forwarding no
        AllowTcpForwarding no

Reiniciar:

```bash
sudo systemctl restart ssh
```

***

# # FASE 7 — Prueba SFTP desde PowerShell

En PowerShell:

```powershell
cd C:\Users\Usuario\Desktop
sftp sftpuser@192.168.56.101
```

Dentro:

```powershell
pwd
cd upload
put archivo.txt
ls
exit
```

***

# # FASE 8 — Prueba SFTP con FileZilla + Wireshark

### FileZilla

    Protocolo: SFTP
    Host: 192.168.56.101
    Usuario: sftpuser

Entrar en `/upload` y subir `archivo.txt`.

### Wireshark

Filtro:

    tcp.port == 22

Ver solo paquetes cifrados (`Encrypted packet`).

***

# # FASE 9 — Verificación final y pruebas cruzadas

### Servicio FTP:

```bash
sudo systemctl status vsftpd
```

### Servicio SSH:

```bash
sudo systemctl status ssh
```

### FTP (CMD)

```cmd
ftp 192.168.56.101
put archivo.txt
```

### FTP (Wireshark)

    ftp.request.command == "USER" || ftp.request.command == "PASS"

### SFTP (PowerShell)

```powershell
sftp sftpuser@192.168.56.101
put archivo.txt
```

### SFTP (Wireshark)

    tcp.port == 22

Todo cifrado.

***

# ## FIN DE LA PRÁCTICA ✔

FTP funcionando + SFTP funcionando + chroot + pruebas + capturas.

***

Si quieres, también te puedo generar:  
📄 **Un informe final listo para entregar (PDF o Word)**  
📸 **Lista de capturas obligatorias**  
📝 **Resumen técnico final**

¿Quieres alguno?
