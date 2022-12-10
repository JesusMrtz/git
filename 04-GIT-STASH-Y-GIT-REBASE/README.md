# Introducción al Stash
> El `stash` Sirve para guardar cambios que aún no estan listos para crear un commit y dejarlo a como el último commit

> No es recomendable trabajar mucho con el Stash ya que se puede desordenar

* `git stash save` - Guarda los cambios al stash pero tambien se puede utilizar el comando `git stash`
* `git stash save "Agregamos un mensaje"` - Guarda los cambios al stash incluyendo un mensaje entender la legibilidad
* `git stash list` - Ver todos los stash guardados con anterioridad
* `git stash pop` - Toma el último stash con los cambios que hicimos anteriormente y lo elimina de la lista de stash
  * Si hay algún problema con los cambios y el Stash, este no se borrará de la lista
* `git stash clear` - Elimina todo los stash en la lista
* `git stash drop "stash@{numero}"` - Eliminar el stash seleccionado de la lista
* `git stash apply "stash@{numero}"` - Recupera el stash selecionado sin eliminarlo de la lista
* `git stash show "stash@{numero}"` - Ver más información sobre el stash seleccionado
* `git stash list --stat` - Vemos más información sobre todos los stash de la lista



# ¿Qué es el Rebase?
> Ayuda a ordenar, unir o separar commit y renombrar los mensajes de los commits

> Se recomienda que se trabaje con el `rebase` si los cambios aún no se suben a repositorio o servidor ya que muchas personas pueden que esten trabajando en el mismo archivo. Tratemos de no cambiar la historia si los cambios ya fueron aceptadas en la rama principal


> DEbo estar en la rama en la cual se mueva los cambios
* Si hago un rebase normal ayuda mucho a actualizar el punto inicial de la rama

## Rebase - Squash

> Sirve para unir dos o más commits en uno solo

> No es recomendable unir commits tan viejos o que ya fueron aceptados en la rama principal, es mejor utilizarlo en nuestra computadoras cuando aún no hacemos la fusión con la rama principal.

* `git rebase -i numeroCommit | HEAD~numerosDeCommits` - Abre la ventana interactiva para poder modificar los commits despues escribimos la palabra `squash` al o los commits que vamos a unir con el anterior (el anterior debe tener la palabra `pick` para unirlo con todos los que dice `squash`).
  * Apretamos la tecla **ESC** y escribimos las letras `:wq!`
  * Preguntara si **Queremos cambiar el mensaje del nuevo commit unido** y volvemos a apretar la tecla **ESC** y escribimos las letras `:wq!`


## Rebase - Reword
> Sirve para poder actualizar el mensaje de los commits seleccionados

> No es recomendable cambiar los mensajes de commits tan viejos o que ya fueron aceptados en la rama principal, es mejor utilizarlo en nuestra computadoras cuando aún no hacemos la fusión con la rama principal.

* `git rebase -i numeroCommit | HEAD~numerosDeCommits` - Abre la ventana interactiva para poder modificar los commits despues escribimos la palabra `reword` al o los commits que vamos a modificar el mensaje.
  * Apretamos la tecla **ESC** y escribimos las letras `:wq!`
  * Preguntara si **Queremos cambiar el mensaje del nuevo commit unido** y volvemos a apretar la tecla **ESC** y escribimos las letras `:wq!`


## Rebase - Edit  
> El rebase edit sirve para poder separar un commit en varias de ello

> No es recomendable separar commits tan viejos o que ya fueron aceptados en la rama principal, es mejor utilizarlo en nuestra computadoras cuando aún no hacemos la fusión con la rama principal.

* `git rebase -i numeroCommit | HEAD~numerosDeCommits` - Abre la ventana interactiva para poder modificar los commits despues escribimos la palabra `edit` al o los commits que vamos a separar.
  * Apretamos la tecla **ESC** y escribimos las letras `:wq!`
  * Preguntara si **Queremos cambiar el mensaje del nuevo commit unido** y volvemos a apretar la tecla **ESC** y escribimos las letras `:wq!`
  * Si todos está bien, creamos un nuevo commit con `git commit --amend -m "Nuevo mensaje"` y después realizar el `git rebase --continue` para salir del estado virtual
  * Si se desea separar los archivos en varios commits se necesita ejecutar el comando `git reset HEAD^`
    * Creamos los commits necesarios con el `git add` y `git commit -m "Mensaje"`
    * Cuando finalicemos de subir cada archivo se ejecutar el `git rebase --continue` para salir del estado virtual