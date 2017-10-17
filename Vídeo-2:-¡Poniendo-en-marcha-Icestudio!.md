[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

Haz click en la imagen para ver el **vídeo en Youtube**

TODO

# Descripción

TODO

# Contenido

* [Instalación de Icestudio](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-2:-%C2%A1Poniendo-en-marcha-Icestudio!#instalaci%C3%B3n-de-icestudio)
  * [Paso 1: Descarga del instalador](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-2:-%C2%A1Poniendo-en-marcha-Icestudio!#paso-1-descarga-del-instalador-de-icestudio)
  * [Paso 2: Ejecutar el instalador](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-2:-%C2%A1Poniendo-en-marcha-Icestudio!#paso-2-ejecutar-el-instalador)
    * [GNU/Linux](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-2:-%C2%A1Poniendo-en-marcha-Icestudio!#gnulinux)

# Instalación de Icestudio

La herramienta que vamos a utilizar para **sintetizar** nuestros circuitos es [Icestudio](https://github.com/FPGAwars/icestudio). Tenemos que instalarlo y configurarlo

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/logo-icestudio.png)

## Paso 1: Descarga del Instalador de Icestudio

Icestudio es una aplicación **libre**, creada en [node.js](https://nodejs.org/es/) por [Jesús Arroyo](https://github.com/Jesus89). Se encuentra alojado en [esta página de github](https://github.com/FPGAwars/icestudio)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/icestudio-01.png)

* Pinchamos en una opción de la parte superior, donde pone **Releases**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/icestudio-02.png)

y nos aparecen todas las **versiones de Icestudio** que hay liberadas hasta el momento. La primera que nos aparece es la última liberada, que al día de hacer este tutorial es la **versión 0.3.1**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/icestudio-03.png)

Nos desplazamos hacia abajo hasta llegar a la **zona de Descargas**, donde están los paquetes de Icestudio para los diferentes sistemas operativos

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/icestudio-04.png)

En los ordenadores actuales, lo normal es que sean de **64 bits**. Según nuestro sistema operativo descargamos alguno de los siguientes ficheros:

|  Fichero a descargar  | Plataforma         | Descripción         |
|-----------------------|--------------------|---------------------|
|  [icestudio-0.3.1-rc-linux64.AppImage](https://github.com/FPGAwars/icestudio/releases/download/0.3.1-rc/icestudio-0.3.1-rc-linux64.AppImage)                 | GNU/Linux, 64-bits | Appimage ejecutable |
|  [icestudio-0.3.1-rc-win64.exe](https://github.com/FPGAwars/icestudio/releases/download/0.3.1-rc/icestudio-0.3.1-rc-win64.exe) | Windows 10, 8, 7, 64-bits | Instalador (Archivo ejecutable) |
| [icestudio-0.3.1-rc-osx64.dmg](https://github.com/FPGAwars/icestudio/releases/download/0.3.1-rc/icestudio-0.3.1-rc-osx64.dmg) | Mac OSX-64 | Instalador para mac |

Si lo que tenemos es un ordenador de **32 bits**, nos descargamos estos ficheros para nuestra plataforma

|  Fichero a descargar  | Plataforma         | Descripción         |
|-----------------------|--------------------|---------------------|
| [icestudio-0.3.1-rc-linux32.AppImage](https://github.com/FPGAwars/icestudio/releases/download/0.3.1-rc/icestudio-0.3.1-rc-linux32.AppImage)                 | GNU/Linux, 32-bits | Appimage ejecutable |
| [icestudio-0.3.1-rc-win32.exe](https://github.com/FPGAwars/icestudio/releases/download/0.3.1-rc/icestudio-0.3.1-rc-win32.exe) | Windows 10, 8, 7, 32-bits | Instalador (Archivo ejecutable) |
| [cestudio-0.3.1-rc-osx32.zip](https://github.com/FPGAwars/icestudio/releases/download/0.3.1-rc/icestudio-0.3.1-rc-osx32.zip) | Instalador para mac | Mac OSX-32 bits | Instalador para mac |

## Paso 2: Ejecutar el instalador

Esta operación depende de nuestra plataforma

### GNU/Linux

Antes de arrancar Icestudio debemos instalar sus dependencias: **python2.7** y **xclip**. Para el caso de **Ubuntu**, abrimos un terminal y escribrimos lo siguiente:

```
sudo apt-get install python2.7 xclip
```

Ahora sólo tenemos que ir la carpeta donde hemos descargado el instalador, desde el **navegador de archivos**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/icestudio-linux-01.png)

Nos ponemos encima del archivo y le damos al **botón derecho** de ratón

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/icestudio-linux-02.png)

Pinchamos en **propiedades**. Se nos abre una ventana nueva

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/icestudio-linux-03.png)

Pinchamos en la pestaña **Permisos**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/icestudio-linux-04.png)

y **activamos** la casilla que pone **Permitir la ejecución del programa**

Cerramos la ventana y hacemos **doble click** en el instalador. Se nos abrirá directamente Icestudio

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/icestudio-linux-05.png)

Los **usuarios avanzados** lo harán directamente con estos comandos:

```
chmod +x icestudio-0.3.1-rc-linux64.AppImage
./icestudio-0.3.1-rc-linux64.AppImage
```

### Windows

Mostraremos los pantallazos para **Windows 10**, aunque el proceso es similar para los windows anteriores. Una vez descargado el instalador lo ejecutamos, haciendo doble click en el archivo descargado en el paso 1. Dependiendo de los antivirus que tengamos instalados, podrán salir varias **ventanas de advertencia**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/Icestudio-w10-01.png)

No les hacemos caso y le damos a **Ejecutar de todas maneras** (Run Anyway). Aún así, nos puede saaltar alguna más



TODO

### Mac

TODO

# Ejercicios propuestos

* **Ejercicio 1**: 

* **Ejercicio 2**: 

* **Ejercicio 3**: 

# Ejercicios entregados

# Autor

* [Juan González-Gómez](https://github.com/Obijuan) (Obijuan)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/logos-urjc-gsyc-peloto-jderobot.png)

# Licencia

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/attribution-share-alike-creative-commons-license.png)

# Créditos y agradecimientos



# Enlaces


# FAQs



