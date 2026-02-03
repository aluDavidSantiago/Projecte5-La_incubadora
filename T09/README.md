# 0226. RA3: Anàlisi vulnerabilitats

En aquesta activitat analitzarem les vulnerabitilitats d'un sistema informàtic mitjançant una eina d'escaneig de vulnerabilitats. L'objectiu és identificar possibles punts febles en la seguretat del sistema i proposar mesures per a mitigar-los.

![Hacking](https://img.shields.io/badge/hacking-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![OpenVAS](https://img.shields.io/badge/OpenVAS-3DDC84?style=for-the-badge&logo=greenhouse&logoColor=white)
![Cybersecurity](https://img.shields.io/badge/Cybersecurity-FF5733?style=for-the-badge&logo=fortinet&logoColor=white)

## Resultats d'aprenentatge i criteris d'avaluació

RA3. Aplica mecanismes de seguretat activa descrivint-ne les característiques i relacionant-les amb les necessitats d'ús del sistema informàtic.

CA3.3 Realitza actualitzacions periòdiques dels sistemes per a corregir possibles vulnerabilitats.

## Entorn de treball

Usarem una màquina virtual OpenVAS com eina d'anàlisi. Aquesta màquina la teniu disponible en forma .ova a la unitat de xarxa. [OpenVAS](https://www.openvas.org) és un producte de codi obert que permet realitzar escanejats de vulnerabilitats en sistemes informàtics. Malgrat això, hi ha diversos nivells de llicència, en funció de les funcionalitats que es vulguin utilitzar.

Com a màquina objectiu, usarem una màquina virtual Linux amb diverses vulnerabilitats conegudes. Aquesta màquina també la teniu disponible en forma .ova a la unitat de xarxa. És la coneguda com a [metasploitable-2](https://sourceforge.net/projects/metasploitable/files/Metasploitable2/). Si la baixeu d'Internet, descarregareu un .zip que conté únicament l'arxiu de disc, però no la màquina virtual completa.

## Preparació de l'entorn

### Equip a escannejar

1. Descarregeu la .OVA corresponent a metasplotible-linux al vostre equip.
2. Importeu la màquina virtual a VirtualBox, **assegureu-vos que la ruta on importarà la màquina és la que voleu utilitzar**.
3. Configureu la màquina per tal que utilitzi xarxa en mode "xarxa-NAT".
4. Inicieu la màquina, les credencials per defecte són:
   - Usuari: `msfadmin`
   - Contrasenya: `msfadmin`
5. Un cop iniciada la màquina, obriu una terminal i executeu la comanda `ip a` per obtenir la IP assignada a la màquina. Anoteu aquesta IP, ja que la necessitareu més endavant.

### Equip amb OpenVAS

1. Descarregeu la .OVA corresponent a OpenVAS al vostre equip.
2. Importeu la màquina virtual a VirtualBox, **assegureu-vos de nou, que la ruta on importarà la màquina és la que voleu utilitzar**.
3. Configureu la màquina per tal que utilitzi dues interfícies de xarxa, la primera en mode "xarxa-NAT" per tal tenir connectivitat a Internet i amb la màquina objectiu, i la segona en mode "host-only" per tal de poder accedir a la interfície web des del vostre equip.
4. Inicieu la màquina, les credencials per defecte són:
    - Usuari: `admin`
    - Contrasenya: `admin`
5. Un cop iniciada la màquina, s'obrirà un menú d'inicialització. En aquest menú, per exemple, us demanen la llicència, que podeu obviar 'Skip'. El que sí que caldrà fer són dues accions importants:
    - Definir l'usuari que usarem per entrar via web, per comoditat triarem un usuari `admin` amb contrasenya `admin`.
    - Configurar la xarxa de les dues interfícies, aquí cal seleccionar en cadascuna d'elles l'opció dhcp de IPv4. Finalment, anoteu les dues adreces.

En aquest vídeo teniu un exemple de com fer aquesta configuració inicial (està fet amb una versió anterior d'OpenVAS, però els passos són similars):  

https://github.com/user-attachments/assets/0aabef5e-ff0a-42a4-bc31-b188e101f2bc

## Procediment pràctic

### Anàlisi de vulnerabilitats

1. Mostra l’accés a OpenVAS via web amb les credencials creades anteriorment. Veuràs que et surt un avís relatiu a la seguretat del certificat, ja que és un certificat autofirmat. Pots ignorar aquest avís.
2. Afegeix la IP de la màquina vulnerable com a Host.
3. Configura un Target amb el Host del punt anterior, inclou les credencials de la màquina vulnerable per accedir via SSH i SMB.
4. Realitza una exploració de vulnerabilitats. Aquest procés pot ser lent, si veieu que us queda poc temps, cancel·leu l’anàlisi i treballeu amb els resultats obtinguts.

Al següent vídeo pots veure un exemple de tot el procés d'anàlisi de vulnerabilitats amb OpenVAS:

https://github.com/user-attachments/assets/da82a5b1-5ccb-450c-a81a-e37827040620

### Recollida de resultats

Un cop acabem l’exploració OpenVAS ens mostra els resultats corresponents a la màquina, podem veure la descripció de la vulnerabilitat i resta de informació significativa. Al darrer vídeo pots veure com es mostren els resultats, tant de vulnerabilitats totals, per serveis, etc.

Al vídeo pots veure un exemple de com visualitzar els resultats obtinguts:

https://github.com/user-attachments/assets/c5e79f0a-9fa8-42f4-aceb-6a6739c9d975

## Documentació de l'activitat

Documenta bé en un arxiu de Google Docs (assegura't de compartir-lo amb el teu professor) o directament en format Markdown, a la carpeta corresponent del repositori GitHub del projecte, els següents punts:

- Documentació del procés d'anàlisi de vulnerabilitats seguit:
  - Configuració de la màquina vulnerable.
  - Configuració de la màquina OpenVAS.
  - Passos seguits per realitzar l'anàlisi.
- Analitza quatre vulnerabilitats trobades:
  - Descripció de la vulnerabilitat incloent el seu CVE.
  - Nivell de gravetat.
  - Possible explotació.
  - Mesures de mitigació proposades.
