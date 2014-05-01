Title: Como ver nombre de máquinas Windows desde Linux
Date: 2012-06-20 15:18
Author: ramborg
Category: GNU/Linux
Tags: Trick
Slug: como-ver-nombre-de-maquinas-windows-desde-linux

Desde Windows resulta muy facil ver que máquina hay conectadas. Pero
desde Linux hay que saber como, porque no viene por defecto.

Explicaré dos formas, esto es solo para poder ver las máquinas Windows,
los nombres y conectarnos a sus recursos compartidos, no para compartir
recursos nosotros.

**1er Método**(extraido de <https://wiki.archlinux.org/index.php/Samba>,
sección Discovering network shares)**  
**

-   Descargar smbclient y nmap
-   Ejecutar nmap para ver las maquinas con recursos compartidos, en
    este paso pueden ir al zenmap, que es el front-end de nmap.

> nmap -p 139 -sT 192.168.1.\*

Veremos algo como:

>     Starting nmap 3.78 ( http://www.insecure.org/nmap/ ) at 2005-02-15 11:45 PHT
>     Interesting ports on 192.168.1.1:
>     (The 1661 ports scanned but not shown below are in state: closed)
>     PORT     STATE SERVICE
>     139/tcp open netbios-ssn
>     5000/tcp open  UPnP
>
>     Interesting ports on 192.168.1.5:
>     (The 1662 ports scanned but not shown below are in state: closed)
>     PORT     STATE SERVICE
>     6000/tcp open  X11
>
>     Nmap run completed -- 256 IP addresses (2 hosts up) scanned in 7.255 seconds

-   Ahora vemos todas las máquinas con el servicio en el puerto 139 y
    ejecutamos el siguiente comando para ver el nombre de NetBIOS.

> nmblookup -A 192.168.1.x

-   Vermos el grupo de trabajo y el nombre de la máquina y los servicios
    abiertos indicados con \<20\>, algo tal que así

>     Looking up status of 192.168.1.1
>             PUTER           <00> -         B <ACTIVE>
>             HOMENET         <00> - <GROUP> B <ACTIVE>
>             PUTER           <03> -         B <ACTIVE>
>             PUTER <20> - B <ACTIVE>
>             HOMENET         <1e> - <GROUP> B <ACTIVE>
>             USERNAME        <03> -         B <ACTIVE>
>             HOMENET         <1d> -         B <ACTIVE>
>             MSBROWSE        <01> - <GROUP> B <ACTIVE>

-   Para conectarnos al recurso compartido nada mas tendriamos que
    hacer:

> smbclient -L \\\\PUTER

**2º Método, con Thunar**(extraido
de <https://wiki.archlinux.org/index.php/Thunar>, sección Tips and
Tricks)

-   Descargar smbclient, gvfs y gvfs-smb
-   Despues reiniciar XFCE y tendremos una nueva localización en Thunar
    llamada Red donde vemos las máquinas Windows.

**3er Método, con smbtree**

-   Ejecutando

> smbtree

**Nota: **Esto es como los pimientos del padrón...unas veces funciona y
otras non :/
