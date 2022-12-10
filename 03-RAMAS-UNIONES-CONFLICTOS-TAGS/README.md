# Introducción a las Ramas, uniones y conflictos
Una rama es mas que una línea de tiempo de commit y esto ayuda cuando queremos agregar nuevas funcionalidades a nuestro software para después unirlos a la otra rama o descartarla.

Una nueva rama es una línea de tiempo totalmente aparte 

Nosotros podemos realizar uniones *(merge)* con otra ramas de los cuales hay tres posible escenarios que puede suceder:

  * `fast-foward` - Se dispara cuando GIT detecta cuando no hay ningún cambio en la rama principal y los nuevos cambios de nueva rama se pueden reintegrar sin ningún problema como si jamás los hubieramos separado
  * `Uniones automáticas` - GIT detecta que hubo un cambio en la rama principal que la rama secundaria desconoce, pero no hay problema ya que se puede unir y esto no causa conflictos en los archivos
  * `Unión manual` - GIT no puede unir los cambios de la nueva rama a la rama principal de manera automática y tenemos que realizarlo de manera manual y tenemos que realizar un nuevo commit también conocido como **merge commit**


# Creación de ramas
* `git branch nombreDeLaRama` - Crea una nueva rama a partir desde donde se creó.
* `git switch nombreDeLaRama` - Podemos movernos a la nueva rama.
  * Tambien podemos utilizar el `git checkout nombreDeLaRama`

Para unir ramas debemos estar en la rama principal escribir el comando `git merge nombreDeLaRama` y tener los cambios

Para eliminar una rama se utiliza el comando `git branch -d nombreDeLaRama`


# Creación de Tags
Los **tags** son una referencia a un commit y a todo el estado del proyecto a ese punto especifico

* `git tag` - Muestra todos los tags creados
* `git tag nombreDelTag` - Crea un tag
* `git tag -d nombreDelTag` - Elimina el tag seleccionado
* `git tag -a nombreDelTag -m "Aqui va el mensaje"` - Crea un tag pero la bandera **-a (annotated tag)** ayuda a tener más información del momento de su creación, contienen la fecha de creación, nombre, email y un mensaje, mientras que el tag normal, simplemente contienen el nombre identificador del tag.
* `git taf -a nombreDelTag idCommit -m "Aqui va el mensaje"` - Crea un tag a un commit especifico
* `git show nombreDelTag` - Ayuda a ver más información sobre el tag seleccionado