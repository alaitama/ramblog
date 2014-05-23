Title: Manual de guerrilla Git
Date: 2014-05-23 20:10
Author: ramborg
Category: Misc
Tags: Programming
Slug: manual-git

Después de estar un año peleandome con Git, he decidido crear mi propio manual/tutorial para el uso que hago el día a día.

Allá vamos! / Here we go!

## Preparar repositorio local

* Clonar repositorio en local
	git clone $URL
* Crear repositorio desde código existente
	TODO
* Asociar varios repositorios remotos a una carpeta
	TODO (for github+openshift p.e.)

## Revert / Descartar cambios

* Recuperar archivos de ultima versión y perder cambios locales
	git reset --hard
* Borrar todos los ficheros locales que no existen en el repositorio remoto
	git clean -fd
* Recuperar un solo archivo y descartar cambios locales
	git checkout -- filename



## Referencias

* Revert [http://stackoverflow.com/questions/5807137/git-how-to-revert-uncommitted-changes-including-files-and-folders][http://www.norbauer.com/rails-consulting/notes/git-revert-reset-a-single-file.html]

