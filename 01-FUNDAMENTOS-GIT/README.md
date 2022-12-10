# ¿Porqué nos interesa saber GIT o un sistema control de versiones?
* Git hace que tu proyecto se convierta en una especie de máquina del tiempo ya que genera un historial de los cambios de los archivos que hemos realizado y nos da el poder de regresar a un commit anterior.
* Para GIT el término proyecto equivale a un **repositorio**
  

## Maneras de trabajar con los repositorios

## Repositorio central
* Nuestro equipo de desarrollo trabaja directamente en el servidor

## Repositorio distribuido
* Todo integrante del equipo de desarrollo tiene una copia del repositorio.
  > También existe un repositorio central en el cuál el equipo de desarrollo sube sus cambios y reciben los cambio de los demás integrantes del equipo.



# Primeros comandos en GIT
* `git --version` -  Se obtiene la versión de GIT instalada en la computadora
* `git --help` - Aparece la ayuda de GIT
* `git config --global user.name "NombreDelUsuario"` - Se configura un usuario dentro de las configuraciones globales de GIT
* `git config --global user.email "correo@correo.com"` - Se configura un correo electrónico dentro de las configuraciones globales de GIT

> NOTAS IMPORTANTES

Las configuraciones del usuario y el email son por usuarios de la cuenta de la computadora.

GIT trabaja con la confianza de la persona que integra el equipo de desarrollo.

GIT piensa que los desarrolladores somos honestos y asi deberia de ser.

También se recomiendo que el correo electrónico que se está configurando en las configuraciones globales de GIT haga MATCH con el correo de la cuenta de GITHUB

* `git config --global -e` - Muestra las configuraciones globales en modo de escritura
  * Si realizó una modificación y quiere guardar los cambios y salir de la consola, tiene que apretar la tecla de **ESC** y escribir en la consola `:wq!` 
  * Si realizó una modificación y no quiere guardar los cambios y salir de la consola, tiene que apretar la tecla de **ESC** y escribir en la consola `:q!`
  * Si no realizó una modificación y quiere salir de la consola, tiene que apretar la tecla **ESC** y escribir en la consola `:q`
* `git config --global -l` - Muestra las configuraciones globales en modo de lectura
* `git init` - Inicializa un repositorio
*  `git status` - Este comando les dará información sobre los commits, la rama donde se encuentran
*  `git add nombreDelArchivo` - Agregar un archivo al Stage para después realizar un commit
*  `git add .` - Agrega todos los archivos modificados al Stage para después realizar un commit
*  `git reset nombreDelArchivo` - Baja el archivo del Stage y ya no será parte del commit a generar
*  `git reset directorio/` - Bajar archivos de un directorio completo del Stage para que no sea parte del commit a generar
*  `git reset *.*` - Bajará todos los archivos del Stage
*  `git commit -m "Mensaje para el commit"` - Genera un commit en el proyecto
*  `git log` - Revisamos todos los commits realizados
*  `git checkout -- .` - Reconstruye el proyecto al último commit guardado
*  `git branch -m nombreActual nuevoNombre` - Sirve para renombrar una rama
*  `git commit -am "Mensaje para el commit"`  - Es un atajo a los commando `git add .` y `git commit -m ""` al mismo tiempo


## Diferentes formas de agregar archivos al escenario
* `git *.html` - Agregamos todos los archivos html dentro del directorio
* `git css/` - Agrega todo los archivos dentro de la carpeta *css*
* `git css js/*.html` - Agrega todos los archivos con extensión html que se encuentre dentro de la carpeta 
*js*

## Creando alias dentro de GIT
  * `git config alias.NombreDelAlias "ComandoAEjecutar"` - Creamos un nuevo alias
    * `git config alias.s "status --short"` - Creamos un alias con el nombre "*s*" que ejecuta el nuevo comando `git s` y esto ejecutará `git status --short`