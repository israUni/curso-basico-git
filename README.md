# Curso básico de GIT
Bienvenid@ a este curso básico de GIT. El objetivo de este repositorio es proporcionarte las bases elementales necesarias para que puedas usar éste potente Sistema de Control de Versiones (*VCS* "Version Control Systems").  
Para poder tener acceso a información más detallada, puedes consultar la documentación oficial de GIT, disponible en la siguiente [página](https://git-scm.com/docs "Documentación oficial de GIT")

### Notas
- En este curso, se utiliza la notación `< >` para indicar que un comando/valor/nombre debe detallarse de acuerdo a las indicaciones dentro de `< >` y de las condiciones de tu proyecto.
- La notación `" "` es utilizada para indicar que un fragmento de texto debe detallarse de acuerdo a las indicaciones dentro de los `" "` y de las condiciones de tu proyecto.  

## Primeros pasos
Como todo buen programador, lo primero es manejar las herramientas esenciales para llevar a cabo tus proyectos. Una de estas herramientas es sin duda: la terminal. Al principio puede parecer intimidante, pero no es así. La terminal es una herramienta que te permite interactuar con tu sistema operativo y otros programas. En la terminal podrás ejecutar comandos, ver información de tu sistema y mucho más. Existen diversos comandos y herramientas de la terminal que te permitirán interactuar con GIT y el repositorio de tu proyecto. A continuación se enlistan algunos de los comandos básicos que utilizarás (y que con el tiempo y práctica dominarás) durante tu interacción con GIT.

## Comandos básicos de la terminal
Comando | Utilidad
--- | ---
`$ ls` | Listar los archivos y carpetas que componen el directorio actual
`$ ls -a` | Listar todos los archivos y carpetas que componen el directorio actual, incluyendo  los archivos *ocultos*
`$ pwd` | Conocer la ruta completa de la carpeta/directorio en la que te encuentras actualmente
`$ cd <directoryToMove>` | Moverte a un direcorio/carpeta específica dentro de tu directorio actual
`$ cd ..` | Regresar "una posición" hacia atrás a partir del directorio en el que te encuentras actualmente
`$ mkdir <directoryName>` | Creación de un directorio/carpeta dentro de tu posición actual
`$ touch <fileName.ext>` | Creación de un archivo con el nombre y extensión especificados en el directorio/carpeta actual
`$ mv <oldFile> <newFile>` | Comando para modificar/cambiar/actualizar el nombre de un archivo.
`$ rm <fileName>` | Comando para eliminar un archivo que se encuentra dentro de tu directorio actual
`$ clear` | Comando para limpiar la pantalla de tu terminal
`$ git <comand> -h` | Comando para ver las "opciones" de configuración de "`<comand>`" disponibles y sus aplicaciones

## Conceptos básicos
Se puede decir que un **repositorio** de GIT, es un "historial" (que inicialmente se guarda en tu equipo local) de determinados momentos en que decides que un cambio/proceso/actualización de tu proyecto debe estar disponible para su posterior consulta/modificación/eliminación. Es como tener una "cámara" que tomará una "foto instantánea" (un *commit*) de tu proceso de desarrollo cuando tú así lo consideres necesario y cada uno de estos *commits* son puntos de referencia que posteriormente te servirá para saber lo que sucedió hasta ese preciso momento. Esto lo puedes hacer las veces que consideres necesario hasta finalizar con tu proyecto.

Para que comprendas el proceso de creación de un repositorio en GIT, es necesario que conozcas las "*etapas*" que conforman el procceso de creación de un "*commit*" o "confirmación". De forma general, en GIT existen 3 etapas (+1) que conforman el proceso de creación de un *commit* (el conjunto de todos tus *commits* formarán tu historial):
1. ### **Working Directory**
   El *Working Directory* o *Directorio de Trabajo*, es el directorio en el que GIT detecta las actualizaciones/cambios/procesos que aún no están consideradas como parte de tu historial y GIT las coloca de forma automática en esta etapa. Para indicarle a GIT que quieres que  considere dichos cambios en tu historial, debes utilizar el comando `$ git add` (y combinaciones de sus opciones).
2. ### **Staging Area (index)**
   Ahora nuestras actualizaciones/cambios/procesos se ecuentran dentro del *Staging Area* o *Área de preparación* (también llamado *index*), que es donde le indicas a GIT que quieres que dichos procesos se encuentren disponibles para su posterior confirmación e inclusión dentro del historial de tu proyecto, es decir: crear un punto de referencia o *commit*. Para tal efecto, le indicarás a GIT que realice este proceso mediante el comando `$ git commit` (y combinaciones de sus opciones).
3. ### **Repository (local)**
   En esta etapa, todos los cambios confirmados mediante `$ git commit ...` ya forman parte de tu repositorio local, es decir, que ya tienes en tu equipo, las "instantáneas" de tu proceso de desarrollo. Dentro de tu repositorio, ahora existen *puntos de control* que te ayudarán a "viajar" en el tiempo y poder verificar el estado en el que se encontraba tu proyecto en determinado momento y si es necesario, modificarlo de acuerdo a tus necesidades (recomendable hacer uso de ramas [**branchs**]).

![Los tres estados de GIT](/images/index1@2x.png)

Como ves, hasta cierto punto es sencillo entender la forma en la que se compone un repositorio creado con GIT, pero a lo largo de tus desarrollos, te darás cuenta que van a surgir diversos detalles y que deberás conocer a mayor profundidad los comandos que GIT te ofrece para darles solución.  
Por otro lado, ¿qué pasará si por alguna razón, tu equipo falla y no tienes acceso a todo el historial de uno o varios de tus proyectos? Para tener un respaldo de nuestro historial, existen servicios/plataformas como GitHub, GitLab, GitBucket, etc., en los que puedes "subir" y almacenar tu repositorio con todo el historial que tenías de forma local y de esta forma, ya seas tú mismo u otro usuario, puede *clonar* dicho repositorio y tenerlo disponible en su equipo y con ello, poder continuar con tu trabajo desde el último estado en que lo dejaste.
## Primeros pasos con Git
Ahora es momento de empezar a trabajar con GIT.

Para ello, lo primero que tienes que hacer es descargar GIT desde [aquí](https://git-scm.com/ "Descarga sitio oficial") y seguir las instrucciones para instalarlo en tu equipo (también puede instalarse la terminal *GitBash*, que puedes utilizar como tu terminal/consola de trabajo).

Para validar que GIT se ha instalado correctamente, ejecuta el siguiente comando:
```powershell
$ git --version
```
Ya que verificaste que tienes instalado GIT en tu equipo, es tiempo de definir las configuraciones iniciales básicas para que GIT utilice esta información de forma inmutable en cada repositorio creado:

El nombre que se utilizará para identificarte dentro de tus repositorios
```powershell
$ git config --global user.name "Your Real Name"
```

El correo electrónico que se utilizará para identificarte dentro de tus repositorios
```powershell
$ git config --global user.email youremail@mail.com
```

Establecer editor de texto por defecto. En algunos casos GIT abrirá el editor de texto configurado para ingresar información. En este caso, se configura VS Code.  Para ver las configuraciones más utilizadas, consulta [aquí](https://desarrollowp.com/blog/tutoriales/aprende-git-de-manera-sencilla-git-config/).
```powershell
$ git config --global core.editor "code --wait"
```

Activar el uso de colores en la interfaz del usuario
```powershell
$ git config --global color.ui true
```
Comando para listar las configuraciones que tenemos configurados en GIT
```powershell
$ git config --global -e
```
## Compatibilidad entre SO's

Cuando te toque trabajar en un equipo con usuarios que utilizan diversos sistemas operativos como Windows, Linux, MacOS, etc., vas a toparte con la necesidad de estandarizar el "formato" en el que se guardan los cambios en los repositorios.

En Windows se agregan 2 caracteres especiales cuando creamos un "salto de línea":
* CR - Carriage Return
* LF-  Line Feed

Para el caso de Linux/MacOS, se agrega solo un caracter:  
* LF - Line Feed

> Configuración en Windows:
```powershell
$ git config --global core.autocrlf true
```
> Configuración en Linux/MacOS:
```powershell
$ git config --global core.autocrlf input
```
Ahora que hemos realizado diversas configuraciones, podemos revisar dichas configuraciones con el siguiente comando:
```powershell
$ git config --global -e
```
Para más detalles del comando `$ git config` consulta [aquí](https://git-scm.com/docs/git-config "Documentación oficial").
<!-- ## Consideraciones en el manejo de los estados de un repositorio en git
crear un repositorio en tu computadora. Este repositorio estará únicamente en tu computadora, Para ello, debes de ir a la terminal y ejecutar el siguiente comando:
Para la gestión de los cambios realizados dentro de nuestro proyecto con GIT, es necesario saber que vamos a considerar *4 etapas* de control dentro de nuestro flujo de trabajo:

1. LOCAL -> (`$ git init` - **Working Directory**) Lo que hacemos dentro de nuestros archivos y carpetas de forma "local", es decir, la creación de nuestro proyecto en nuestro equipo.
2. STAGE (`$ git add` - **Staging Directory**) -> Etapa donde seleccionaremos los archivos que queremos que pasen a la fase de "preparación", es decir, le vamos a indicar a git los archivos que queremos que formen parte de la etapa de *staging*. En otras palabras, estamos determinando qué cambios queremos que se consideren dentro del desarrollo de nuestro proyecto. Si por alguna razón no queremos pasar determinados cambios, podemos "sacar" dicho archivo de esta etapa.
3. COMMIT (`$ git commit` - **Repository**) -> Etapa donde *confirmaremos* los cambios previamente realizados y pasaran a formar parte de nuestro flujo/árbol de historial en git. Ahora, los archivos que se encontraban en la etapa de *staging* y que son confirmados (o *commiteados*) se "mueven" a la etapa de *Repository*.
4. SERVER [`$ git push `(Github, Gitbucket, otros)] -> Etapa donde llevamos a la "nube" todo nuestro flujo de trabajo que realizamos en local. -->

## Comandos para la gestión básica de un proyecto

Ahora que ya instalaste GIT en tu equipo y has establecido las configuraciones básicas, puedes empezar a utilizar este potente Sistema de Control de Versiones en tus proyectos.

A continuación se enlistan los comando más utilizados en un proyecto con GIT y sus usos:

Inicializar un repositorio GIT dentro de nuestro directorio actual.
```powershell
$ git init
```

Crear un directorio con el nombre `<directoryName>` e inicializar un repositorio GIT dentro del mismo.
```powershell
$ git init <directoryName>
```

Verificar el "estado" en el que se encuentra el seguimiento de nuestro proyecto.
```powershell
$ git status
```

Eliminar los últimos cambios en un archivo que ya tuvo al menos una confirmación y que se ha modificado y NO se ha pasado a la etapa de *staging*, es decir, que no se ha utilizado el comando `git add`.
```powershell
$ git restore <filename>
```

Agregar un archivo o carpeta a la etapa de *staging* de nuestro proyecto.
```powershell
$ git add <fileName>
```

Agregar **todos** los archivos o carpetas a la etapa de *staging* de nuestro proyecto.
```powershell
$ git add . | $ git add -A
```

Sacar" de la etapa de *staging* un archivo/modificación/eliminación y pasarlo a la etapa de *working*, sin ELIMINAR los cambios realizados hasta el momento
```powershell
$ git restore --staged <fileName>
```

Sacar de la etapa de *staging* el archivo especificado y quitarlo del seguimiento de GIT, pasando a un estado de "untracked" (sin seguimiento) sin perder las modificaciones realizadas hasta el mmomento.
```powershell
$ git rm --cached <fileName>

```

Sacar el último proceso que está en la etapa de *staging* para pasarlos a la etapa de *working* sin perder los cambios realizazdos hasta ese momento
```powershell
$ git reset
```

Realizar confirmación/*commit* en el editor de texto configurado detallando el mensaje correspondiente. Cada *commit* contará con un **identificador** (hash) con el que posteriormente podremos acceder a él para realizar las acciones permitidas en un *commit*.
```powershell
$ git commit
```

Realizar confirmación/*commit* detallando el mensaje correspondiente en la misma terminal. Cada *commit* contará con un **identificador** (hash) con el que posteriormente podremos acceder a él para realizar las acciones permitidas en un *commit*.
```powershell
$ git commit -m "Print a descriptive message here"
```

"Alterar" el último *commit* realizado, agregándole "nuevos" cambios y definir el mensaje en el editor de texto configurado. En realidad lo que sucede es que se elimina el último *commit*, se crea uno nuevo y éste último conserva los cambios de ambas confirmaciones.
```powershell
$ git commit --amend
```

"Alterar" el último *commit* realizado, agregándole "nuevos" cambios y definir el mensaje en la misma terminal. En realidad lo que sucede es que se elimina el último *commit*, se crea uno nuevo y éste último conserva los cambios de ambas confirmaciones.
```powershell
$ git commit --amend -m "Message that will replace the previous one"
```

Eliminar todos los committs posteriores realizados a `<hashCommitValue>` y pasa los archivos/modificaciones a la etapa de *working* sin perder los cambios realizados hasta ese momento
```powershell
$ git reset <hashCommitValue>
```

Elimina el(los) commit(s) **POSTERIOR(ES)** al especificado en `<hashCommitValue>` y pasa todo a la etapa de *staging* (listo para confirmar) sin borrar los cambios realizados hasta ese momento
```powershell
$ git reset --soft <hashCommitValue>
```

Elimina **TODOS** los commits y/o estados pendientes de nuestro proyecto **POSTERIORES** al `<hashCommitValue>`, posicionandonos en el estado en que se econtraba nuestro proyecto en `<hashcommitValue>`
```
$ git reset --hard <hashCommitValue>
```

Elimina el(los) commit(s) **POSTERIOR(ES)** al especificado en `<hashCommitValue>` y pasa todo a la etapa de *working*
```powershell
$ git reset --mixed <hashcommitValue>

```

Eliminar de nuestro directorio el archivo especificado. Al ser una modificación en nuestro flujo de trabajo, ahora tendremos esta acción en la etapa de *staging*, lista para ser confirmada y dar detalles de esta acción.
```powershell
$ git rm <fileName>
```

Eliminar de nuestro directorio el archivo especificado en modo FORZADO. Esto eliminará de forma definitiva el archivo sin posibilidades de recuperarlo ya que esta acción no se registra en nuestro historial.
```powershell
$ git rm -f <fileName>
```

Recuperar un archivo eliminado inmediatamente después de haber utilizado `$ git rm <fileName>`
  1. Utilizar: `$ git restore --staged <filename>`
  2. Utilizar: `$ git restore <filename>`

Renombrar un archivo y pasarlo directamente a la etapa de *staging*
```powershell
$ git mv <oldFileName> <newFileName>
```

Mostrar detalles simplificados de las etapas en las que se encuentran nuestros archivos
```powershell
$ git status -s
```
* M  -> Modified  
   *red* = Fuera de la etapa *staging*, listo para ser agregado a la etapa de *staging*  
   *green* = Dentro de la etapa *staging*, listo para ser confirmado(committed)
* ?? -> Archivo sin seguimiento(untracked), usar `$ git add <untrackedFileName>` para incluir el archivo a la etapa de *staging*
* A  -> Archivo agregado a la etapa de *staging* antes de tener algun commit
* AM -> Archivo agregado y modificado, a la espera de su gestión (considerar los colores anteriores)
* D -> Archivo eliminado  
   *red* = Eliminado de nuestro directorio y de la etapa *committed*, dicho proceso pasa a la etapa de *working*  
   *green* = Eliminado sólo del estado *committed* y pasa a la etapa de *working* como "untracked"
> *Al estar todas las flags en verde, ahora podemos hacer el(los) commit(s) necesario(s)*

Para más detalles del comando `$ git status`, visitar esta [página](https://git-scm.com/docs/git-status "Documentación git status")

Posicionarse en el estado en que se encontraba nuestro proyecto cuando confirmamos el commit especificado.
```powershell
$ git checkout <hashCommitValue>
```

Visualizar el historial de commits realizados en nuestro proyecto en diversas presentaciones
```powershell
$ git log | $ git log --oneline | $ git log --oneline --graph | $ git log --oneline --graph --decorate
```

Visualizar las diferencias de los cambios realizados en los archivos que aún no se encuentren en la etapa de *staging*
```powershell
$ git diff
```

Visualizar las diferencias de los cambios realizados en los archivos que *YA* se encuentren en la etapa de *staging*
```powershell
$ git diff --staged
```

Deshacer los últimos cambios realizados en un archivo que se encuentra en la etapa de *working*, para que el archivo quede en su estado original antes de la modificación que se le aplicó
```powershell
$ git checkout -- <filename>
```

## Gestion de etiquetas (tags)

Las etiquetas son una forma de identificar un estado de nuestro proyecto. Generalmente utilizadas para definir una "versión" y llevar un control de hasta donde consideramos que nuestro proyecto es funcional.

---
Crear la etiqueta con el nombre v0.0.1. en el último commit realizado, sin considerar alguna descripción o mensaje definido
```powershell
$ git tag v0.0.1
```

Crear la etiqueta con el nombre v0.0.1. en el último commit realizado, añadiendo una descripción o mensaje específicos
```powershell
$ git tag v0.0.1 -m "Descriptive message for the tag"
```

Modificar el mensaje o descripción definida en la etiqueta v0.0.1
```powershell
$ git tag -f v0.0.1 -m "New descriptive message for the tag"
```

Crear la etiqueta v0.0.1 en el commit especificado y añade un mensaje a dicha etiqueta
```powershell
$ git tag v0.0.1 <hashCommitValue> -m "Descriptive message for the tag"
```

Crear y añadir (o modificar) la etiqueta v0.0.5 en el commit especificado y añade un mensaje a dicha etiqueta
```powershell
$ git tag -f v0.0.5 -m "Descriptive message for the tag" <hashCommitValue>
```

Enlistar las etiquetas de nuestro proyecto
```powershell
$ git tag -l
```

Verificar el contenido de la etiqueta v0.0.1
```powershell
$ git tag -v v0.0.1
```

Eliminar la etiqueta v0.0.1
```powershell
$ git tag -d v0.0.1
```

## Poner cambios en "*pausa*"

En ocasiones necesitaremos poner en "*pausa*" lo que estamos haciendo (sin perder los avances que llevamos hasta el momento) para poder realizar tareas secundarias y una vez que finalizamos estas tares, poder regresar a nuestro flujo de trabajo principal y continuar donde lo dejamos.

Para ello, GIT cuenta con el comando `$ git stash`

---
Poner los cambios/procesos realizados hasta el momento en una etapa temporal/pausada sin perder los avances realizados
```powershell
$ git stash
```

Poner los cambios/procesos realizados hasta el momento en una etapa temporal/pausada sin perder los avances realizados incluyendo un mensaje descriptivo
```powershell
$ git stash save "Your descriptive message goes here"
```

Enlistar los procesos/cambios que se encuentran en la etapa temporal/pausada
```powershell
$ git stash list
```

Obtener información detallada de un cambio/proceso que se encuentra en la posición `<stashValue>` especificado (stashValue = valor que va de CERO en adelante [0 - n])
```powershell
$ git stash show stash@{<stashValue>}
```

Sacar el último cambio/proceso que pusimos en la etapa temporal/pausada y pasarlo a la etapa de *working*
```powershell
$ git stash apply
```

Sacar el cambio/proceso temporal de acuerdo a su posición en el que se encuentra (verificar con `$ git stash list`) y pasarlo a la etapa de *working*
```powershell
$ git stash apply stash@{<stashValue>}
```

Eliminar el último cambio/proceso temporal que pusimos en la etapa temporal/pausada
```powershell
$ git stash drop
```

Eliminar el cambio/proceso temporal especificado en la posición descrita en `<stashValue>`
```powershell
$ git stash drop stash@{<stashValue>}
```

Sacar y eliminar el último cambio/proceso que pusimos en la etapa temporal. Se puede dcir que este comando es la combinación de `$ git stash apply` y `$ git stash drop`
```powershell
$ git stash pop
```

Sacar y eliminar el cambio/proceso especificado en la posición `<stashValue>` que pusimos en la etapa temporal
```powershell
$ git stash pop stash@{<stashValue>}
```

## Gestion de ramas "branches"

A medida que un proyecto va creciendo y por consejo de muchos desarrolladores, es altamente recomendable llevar a cabo nuestro proyecto mediante la implementación de ramas con GIT. Esto ofrece gran flexibilidad de no manipular directamente nuestro proyecto, sino que tenemos la posibilidad de crear "ramificaciones" paralelas a nuestro proyecto y una vez que determinamos que nuestros cambios deben ser aplicados al proyecto en general, simplemente "fusionamos" la rama alterna con la rama principal y mantenemos un flujo de trabajo limpio y ordenado.

---
Enlistar las ramas que existen dentro de nuestro proyecto
```powershell
$ git branch | git branch -l
```

Crear una nueva rama desde el punto donde estamos actualmente con el nombre especificado en branchName
```powershell
$ git branch <branchName>
```

Crea una nueva rama desde el punto donde estamos actualmente con el nombre especificado en branchName y se mueve a esta rama
```powershell
$ git checkout -b <branchName>
```

Eliminar la rama especificada en `<oldBranchName>` y se crea una nueva rama en su lugar con el nombre especificado en `<newBranchName>`
```powershell
$ git branch -m <oldBranchName> <newbranchName>
```

Moverse a la rama especificada en `<branchName>` y se pasan las modificaciones pendientes a esta rama, ahora se podran confirmar y dichas confirmaciones quedarán establecidas en la rama a la que nos cambiamos
```powershell
$ git checkout <branchName>
```

Eliminar la rama especificada en `<branchName>`
```powershell
$ git branch -d <branchName>
```

Eliminar la rama especificada en `<branchName>` de forma "forzada"
```powershell
$ git branch -D <branchName>
```

---
---
**Para recuperar una rama que se eliminó por alguna razón, lo recomendable es contar con el HASH del último *commit* realizado (se puede hacer uso del comando `git reflog`) y el nombre de la rama eliminada, posteriormente, hacer uso de `git branch -b <deletedBranchName> <hashCommitValue>` y esto debe crear la rama nuevamente con los cambios que dicha rama contenía**

---
---

Crear/recuperar una rama eliminada y sus cambios/confirmaciones, con el nombre especificado en `<deletedBranchName>` y con el HASH especificado en hashCommitValue
```powershell
$ git branch -b <deletedBranchName> <hashCommitValue>
```