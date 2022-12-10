# GitHub

**GitHub** es una plataforma de desarrollo colaborativo de software para alojar proyectos.

**GitHub** es tan popular porque:
1. Tiene repositorios ilimitados
2. Puedes alojar páginas HTML, CSS y Js Ilimitadas
3. Push, pull y clone ilimitados
4. Issues, Wikis, Estadisticas ilimitadas 
5. Organizaciones ilimitadas
6. Participación gratuita en proyectos privados
7. Github desde enero 2019 permite crear repositorios privados gratuitamente

> `Git` no maneja el acceso al repositorio

`git remote add origin url ` - Se crea un origen remoto hacia la URL
 * `add` agrega un nuevo remote y podemos tener varios remote en un mismo repositorio
 * `origin` - Es el nombre de nuestro remote (es estandar que se llame origin)
  
`git remote -v` - Sirve para revisar las fuentes remotas que tenemos agregadas al repositorio

`git push -u origin master`
* `origin` es el nombre que actualizamos con anterioridad
* `master` - Es la rama que deseamos subir
* `-u` Nos ayuda que la próxima vez que queremos hacer un push, no necesitamos especificar la rama


## Subir los tags a GitHub
* `git push --tags` - Sube los tags al origen remoto que está establecido por defecto

Si le damos en descargar el *zip* solo descarga el contenido a como estaba el repositorio cuando se creó ese tag **pero no se descarga el repositorio con el git**

La diferencia entre un tag y un *release tag* es que básicamente es que yo especifico de que esto va a hacer un punto que puede descargar de github las personas.


# GitHub Avanzado 

#### Agregando nuevos remote
* Para agregar nuevo remote tenemos que ejecutar el siguiente comando `git remote add nombreDelRemote url`.
* Normalmente se le llama *upstream* para crear un nuevo *remote* para solo bajar cambios (normalmente se hacen para los proyectos al que creamos un **fork**)
  * `git remote add upstream https://github.com/Klerith/legion-del-mal.git` - Creamos un *upstream* para bajar los cambios del proyecto principal de nuestro **fork**
  * Para bajar cambios a nuestra rama, ahora podemos ejecutar el siguiente comando `git pull upstream master`

#### Actualizamos un alias
* Ejecutamos el comando `git config --global -e` y después actualizamos el alias.
* Apretamos la tecla de **ESC** y escribimos `:wq!`

#### Crear un nuevo remote
* Escribimos el comando `git push --set-upstream origin ramaRemota` para realizar la conexión de la rama remota con la local

#### Revisar trabajo de un compañero 
* `git branch --all` - Obtiene todos las ramas que estan en el origin y seleccionamos la rama que deseamos revisar.
* `git checkout nombreDeLaRama` - Sirve para hacer track a la rama.

#### Limpiar ramas que ya no necesitamos 
* Me muevo a la rama principal **master**
* Borramos las ramas locales que ya no necesitamos con `git branch -d nombreDeLaRama`
* Si ya no existe las ramas remotas, se puede utiizar el comando `git remote prune origin` para eliminar aquellas ramas que ya no existen
* Hacemos un `git branch --all` para verificar