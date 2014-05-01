Title: Quitar sonido del PC Speaker
Date: 2012-06-20 15:16
Author: ramborg
Category: GNU/Linux
Tags: Customize
Slug: quitar-sonido-del-pc-speaker

-Quitar sonido de pc speaker, por una sola vez, cambio no pemanente:

\#modprobe -r pcspkr

-Quitar sonid pc speaker, cambio permanente:

Crear fichero .conf dentro de ruta /etc/modprobe.d. En mi caso:

\# vi /etc/modprobe.d/blacklist.conf

Y añadimos la línea:

blacklist pcspkr

Guardamos el fichero, y ya está, al reiniciar ya no tendremos el pitido.
