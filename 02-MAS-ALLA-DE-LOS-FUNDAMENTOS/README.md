# Ver los cambios de los archivos
* `git diff` - Muestra todas las diferencias de todos los archivos modificados
* `git diff --staged` - Muestra todas las diferencias de todos los archivos que estan en el stage


# Actualizaciones de commit
* `git commit --amend -m "Mensaje del commit"` - Permite cambiar el mensaje del último commit
* Si ya agregamos un commit, pero volvemos a modificar el mismo archivo inmediatamente y no queremos agregarlo a un nuevo commit, si no al commit anterior. podemos hacer: 
  * `git reset --soft idCommit | HEAD^` - Regresa al commit seleccionado sin perder los cambios y dejando los archivos en el *Stage*.
  * `git reset --mixed idCommit | HEAD^` - Regresa al commit seleccionado sin perder los cambios pero sacando los archivos del *Stage*
  * `git reset --hard idCommit | HEAD^` - Regresa al último commit seleccionado perdiendo los cambios.
    * **NOTA:** El *HEAD^* apunta un commit anterior
    * Si queremos apuntar 3 commits atrás se debe utilizar `HEAD^3`
    * NO ES RECOMENDABLE IR TAN ATRÁS AL MOMENTO DE MODIFICAR O ACTUALIZAR LOS COMMITS Y MÁS SI YA FUERON ACEPTADOS EN UN PUSH

## Apuntes extras sobre los tipos de reset
Soft

    "Elimina" los commits posteriores al commit al que estas haciendo el reset

    Conserva los cambios en el stage area

    Conserva los cambios que tengas en tus archivos (working directory)

Mixed

    "Elimina" los commits posteriores al commit al que estas haciendo el reset

    Deshace los cambios en el stage area

    Conserva los cambios que tengas en tus archivos (working directory)

Hard

    "Elimina" los commits posteriores al commit al que estas haciendo el reset

    Deshace los cambios en el stage area

    Deshace los cambios que tengas en tus archivos (working directory)


# Reflog
Ayuda a tener un historial de todo los sucedido en orden cronologico en el comando `git reflog` y si queremos ir a un commit en especifico es con `git reset --hard idCommit` **PERO SE PERDERÁN LOS CAMBIOS**


# Cambiando el nombre y eliminar archivos mediante GIT

* Para mover o renombrar el archivo se necesita el comando `git mv nombreActual nuevoNombre` y estará listo para crear un nuevo commit
* Para eliminar un archivo desde GIT necesitamos el comando `git rm nombreDelArchivo` y estará listo para crear un nuevo commit

  Si deseamos deshacer el cambio de *renombramiento* o *eliminado* de un archivo GIT se utiliza el comando `git reset nombreDelArchivo`.

  Pero si queremos regresar al punto donde estabamos antes de realizar el renombramiento o el eliminado se necesita el comando `git reset --hard`

# Cambiando el nombre y eliminar archivos fuera de GIT

  GIT es lo suficientemente listo para verificar si un archivo fue eliminado o renombrado desde la computadora y solo es necesario realizar un nuevo commit.


# Ignorado archivos
  Se crea un nuevo archivo llamado `.gitignore` y ahi se agrega **Directorios** y **Archivos** que se desean eliminar
