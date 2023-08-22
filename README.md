# Desarrolladores de Software Porcicarnes
> Este usuario almacena centralizadamente los repositorios de la empresa Porcicarnes, que administra el área de desarrollo de software.

## Menú
* [Información General](#información-general)
* [Directrices](#directrices)
* [Integrantes](#integrantes)
* [Estatus](#estatus)

## Información General
Los proyectos que se desarrollan para la empresa Pocicarnes, se almacenan con este usuario para el registro de los cambios, bugs, mejoras, documentación y versiones de las aplicaciones.
	
## Directrices
Para el uso de cualquier repositorio:

### Clonar el Repositorio desde Azure DevOps:
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

### Trabajar Sobre Ramas
El proyecto tiene 3 ramas principales, la rama ```main```, la rama ```developer``` y la rama ```test```. 
* La rama ```main``` es de dónde saldrán los release (que se verán reflejados en las tags) y la que se modificará únicamente cuando las pruebas sobre la rama de desarrollo hayan sido ejecutadas correctamente.
* La rama ```developer``` es dónde se harán los merge de las ramas que solucionan los bugs y errores específicos de las nuevas funcionalidades del proyecto.
* La rama ```test``` es la rama que duplicará a developer y en la que se generarán las pruebas.
> De la rama ```test``` se hace el merge a la rama ```main``` para el release de una nueva versión de la aplicación.
	
## Integrantes
Los integrantes del equipo de desarrollo son:
* [Juan Esteban Giraldo](https://github.com/YHPSNK99)
* [Juan Estaban Sepulveda](https://github.com/LePaposie)
* [Yersson Hernandez](https://github.com/YHPSNK99)
* [Jaime Areiza](https://github.com/Jareiza99)
* [Isabella Jaramillo](https://github.com/isabela3013)

## Estatus
[![GitHub Streak](http://github-readme-streak-stats.herokuapp.com?user=isabela3013&theme=dark&background=000000)](https://git.io/streak-stats)
