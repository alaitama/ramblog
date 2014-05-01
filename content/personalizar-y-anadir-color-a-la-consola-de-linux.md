Title: Personalizar y añadir color a la consola de Linux
Date: 2012-06-20 15:17
Author: ramborg
Category: GNU/Linux
Tags: Customize
Slug: personalizar-y-anadir-color-a-la-consola-de-linux

Actualmente la mayoria de distribuciones de linux ya vienen con un poco
de color, al menos el ls, pero a veces no.

Para añadir color a la consola de linux es necesario:

-   Crear un archivo en la ruta del usuario de normbre ".bashrc",
    también se puede encontrar una plantilla en /etc/skel/(al menos en
    Arch).

-   Añadir alias, por ejemplo:

> *        alias ls='ls --color=auto'*
>
> *        alias grep='grep --color=auto'*

-   Tambien se puede personalizar el prompt de la consola, yo no lo
    cambio, pero al final dejo un enlace donde explica como.

-   A parte del color, para mi es importante el "autocomplete" de las
    opciones de los comandos, para esto hay que tener descargado el
    paquete "bash-completion" y añadir lo siguiente a nuestro .bashrc:

>      * if [ -f /etc/bash\_completion ]; then*  
>  *            . /etc/bash\_completion*  
>  *      fi*

-   Por último, si se usa Vim como editor, para poner color a la
    sintaxis, se hace creando un archivo ".vimrc" y escribiendo en el:

>      *syntax on*

**Nota**: en mi caso el .bashrc para root no me lo reconocia. Existe el
fichero /etc/bash.bashrc donde también se pueden poner estos cambios.

Los articulos de donde he sacado la información son los siguientes:

Personalización consola(mas completo, tiene lo del prompt):

<http://jfibergran.wordpress.com/2009/04/10/personalizar-la-consola-de-linux-bashrc/>

Vim con color:

<http://rm-rf.es/activar-colores-en-vim/>
