# Desarrolladores de Software Porcicarnes
> Este usuario almacena centralizadamente los repositorios de la empresa Porcicarnes, que administra el área de desarrollo de software.


## Menú
* [Información General](#información-general)
* [Directrices](#directrices)
  - [Clonar el Repositorio desde Azure DevOps](#clonar-el-repositorio-desde-azure-devops)
  - [Publicar Aplicaciones](#publicar-aplicaciones)
* [Comandos de Git](#comandos-de-git)
  - [Agregar Cambios](#agregar-cambios)
  - [Mensajes Commit](#mensajes-commit)
  - [Estructura de las Ramas](#estructura-de-las-ramas)
    + [Comandos para las Ramas](#comandos-para-las-ramas)
    + [Diagrama de las Ramas](#diagrama-de-las-ramas)
* [Integrantes](#integrantes)
* [Estatus](#estatus)


## Información General
Los proyectos que se desarrollan para la empresa Pocicarnes, se almacenan con este usuario para el registro de los cambios, bugs, mejoras, documentación y versiones de las aplicaciones.


## Directrices
Para consultar los comandos básicos de Git haga [click aquí](https://gist.github.com/dasdo/9ff71c5c0efa037441b6).


## Clonar el Repositorio desde Azure DevOps
Para clonar un repositorio desde Azure DevOps, se deberán seguir los siguientes pasos:
* Dar click en el botón **Clone** y seleccionar en **Command Line** la opción **HTTPS** y copiar la URL.
* En el computador abrir la carpeta dónde se almacenará el proyecto, abrir la terminal o el Git Bash y clonar el repositorio con la URL del repositorio:

```
git clone URL
```
> Es posible que al intentar clonar el repositorio, se pida volver a ingresar las credenciales de la Microsoft.

* Dar click en **Generate Git Credentials** y copiar la contraseña.
* Cuando la terminal pida:
```
Password for 'URL':
```
  pegar la contraseña en la terminal.

> La contraseña no se ve en la terminal, al pegar 1 vez el texto dar enter y seguir con el proceso.


## Publicar Aplicaciones
La estrategia elegida para el versionamiento de las aplicaciones es la **Numeración Semántica**, y se basa de una numeración de 3 dígitos: **X.Y.Z (Mayor.Menor.Parche)**.

1. ***La versión mayor (X)*** se incrementa cuando se realizan cambios que rompen la compatibilidad hacia atrás con versiones anteriores. Esto significa que las modificaciones en el comportamiento del software pueden afectar la forma en que los usuarios interactúan con él.
2. ***La versión menor (Y)*** se incrementa cuando se añaden nuevas características o funcionalidades al software de una manera compatible con las versiones anteriores. Esto indica que se han agregado capacidades nuevas sin romper la estructura existente.
3. ***El número de parche (Z)*** se incrementa cuando se realizan correcciones de errores o soluciones para problemas de manera retrocompatible. Estos cambios no deberían alterar la funcionalidad existente ni la interfaz de programación.

Además, se pretende que cada versión tenga su propia **etiqueta o tag** en el repositorio, para tener un control de versiones ordenado, que permita correctamente rastrear versiones específicas del código.


## Comandos de Git
Los comandos normales para subir un cambio a un repositorio es:
```
git add . o git add srchivo o git add -p archivo
git commit -m "Encabezado" -m "Detalle" o git commit (para mensajes más largos que requieren del editor de texto de git para escribir el mensaje)
git pull 
git merge <nombre_de_la_rama_a_fusionar> o 
git rebase -i branch
```


## Agregar Cambios
Los archivos que se agreguen y el mensaje con el que se suben los cambios, debe ser específico y detallar todas las modificaciones, mejoras o aspectos a tener en cuenta con el nuevo código.

- Se recomienda agregar manual el archivo con los cambios en vez de utilizar el comando git add .
- Al agregar los cambios utilizar este comando: ```git add -p nombrearchivo.html```, este comando te permitirá agregar solamente los cambios del archivo que tienen que ver con el commit que se está realizando.

## Mensajes Commit
Para comentar los cambios se debe escribir el comando:
```
git commit -m "Encabezado" -m "Detalle" o git commit (para mensajes más largos que requieren del editor de texto de git para escribir el mensaje).
```

### Esctructura del Mensaje
Tipo de cambio: Título del commit
> En los tipos de cambios se incluyen: add, fix, hotFix, delete o docs y se agrega después de los paréntesis el título del cambio.

Descripción
> Es el detalle de los cambios

Para tener en cuenta
> Aspectos a considerar por los cambios realizados

Issues: #123
> Número de feature, issue o bug que soluciona, cierra o edita el commit a subir


## Estructura de las Ramas
El proyecto tiene 3 ramas principales, la rama ```main```, la rama ```developer``` y la rama ```test```. 
* La rama ```main``` es de dónde saldrán los release (que se verán reflejados en las tags) y la que se modificará únicamente cuando las pruebas sobre la rama de desarrollo hayan sido ejecutadas correctamente.
* La rama ```developer``` es dónde se harán los merge de las ramas que solucionan los bugs y errores específicos de las nuevas funcionalidades del proyecto.
* La rama ```test``` es la rama que duplicará a developer y en la que se generarán las pruebas.
> De la rama ```test``` se hace el merge a la rama ```main``` para el release de una nueva versión de la aplicación.

Las ramas que solucionan bugs, errores específicos o crean nuevas funcionalidades se nombran así ```type/name``` y tienen la siguiente estructura:
* Se escriben en **lowerCamelCase**.
* El tipo se divide en:
  - add: Se generan una nuevas funcionalidades.
  - fix: Se realizan correciones de Bugs.
  - hotFix: Se hacen correcciones de bugs que no pasan por pruebas sino que van directamente a la rama ```main``` para ser desplegados.
  - delete: Se eliminan funciones o archivos.
  - docs: Se generan cambios en la documentación.
* El nombre debe ser corto, sin dar muchos detalles.


## Comandos para las Ramas
Para agregar archivos
```
git commit -m "Encabezado" -m "Detalle" o git commit (para mensajes más largos que requieren del editor de texto de git para escribir el mensaje)
```

Para obtener los cambios
```
git pull
```

Para subir los cambios a una rama
```
git merge <nombre_de_la_rama_a_fusionar> o 
git rebase -i branch
```

Para colocarnos sobre una rama:
```
git checkout main (O el nombre de la rama que vallamos a utilizar)
```

Para crear una nueva rama:
```
git checkout -b nombre/nuevaRama
```

Para tener la rama en el repositorio remoto y no solamente en el local:
```
git push --set-upstream origin nombre/nuevaRama
```

1. Para los commit:
- Se recomienda agregar manual el archivo con los cambios en vez de utilizar el comando git add .
- Al agregar los cambios utilizar este comando: git add -p nombrearchivo.html, este comando te permitirá agregar solamente los cambios del archivo que tienen que ver con el commit que se está realizando.

2. Para subir los cambios a las ramas:

***Opción 1: Usar git merge***

1. Asegúrate de estar en la rama utilizando el comando:

```
git checkout developer
```

2. Fusiona los cambios de la rama "fix/bug" en "developer" usando git merge:

```
git merge fix/bug
```

3. Resuelve cualquier conflicto que pueda surgir durante la fusión. Git te indicará los archivos en conflicto y podrás editarlos para resolver las diferencias.

4. Después de resolver los conflictos, agrega los archivos modificados y realiza un commit para completar la fusión:

```
git add .       # Agrega los archivos modificados
git commit -m "Merge fix/bug into developer"
```

***Opción 2: Usar git rebase (recomendado si deseas una historia de commits más lineal)***

1. Asegúrate de estar en la rama:

```
git checkout developer
```

2. Realiza un rebase interactivo para incorporar los cambios de la rama "fix/bug" en la rama "developer":

```
git rebase -i fix/bug
```

3. Se abrirá un editor de texto con una lista de commits de la rama "fix/bug". Cambia la palabra "pick" por "squash" o "s" en los commits que quieras combinar con el commit anterior. Guarda y cierra el editor.

4. En el siguiente editor que se abra, puedes modificar el mensaje de commit resultante si es necesario. Guarda y cierra el editor.

Si hay conflictos durante el rebase, resuélvelos de la misma manera que en la opción anterior.

5. Una vez que hayas resuelto los conflictos y finalizado el rebase, realiza un push forzado a la rama "developer":

```
git push origin developer --force
```

>Importante: Ten en cuenta que un push forzado (--force) puede sobrescribir la historia de la rama "developer". Utiliza esta opción con precaución y asegúrate de que nadie más esté trabajando directamente en la rama "developer" mientras realizas este proceso.


## Diagrama de las Ramas
![image](https://github.com/devAnt0/devAnt0/assets/142921169/a6d756b1-1c7a-4a3f-a40c-d9895aed6444)


## Integrantes
Los integrantes del equipo de desarrollo son:
* [Juan Esteban Giraldo](https://github.com/YHPSNK99)
* [Juan Estaban Sepulveda](https://github.com/LePaposie)
* [Yersson Hernandez](https://github.com/YHPSNK99)
* [Jaime Areiza](https://github.com/Jareiza99)
* [Isabella Jaramillo](https://github.com/isabela3013)
* [Liset Mosquera](https://github.com/Lissy07)


## Estatus
[![GitHub Streak](http://github-readme-streak-stats.herokuapp.com?user=devAnt0&theme=dark&background=000000)](https://git.io/streak-stats)
