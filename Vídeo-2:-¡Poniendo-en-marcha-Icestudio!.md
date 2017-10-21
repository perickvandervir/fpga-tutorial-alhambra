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
    * [Windows](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-2:-%C2%A1Poniendo-en-marcha-Icestudio!#windows)
    * [Mac](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-2:-%C2%A1Poniendo-en-marcha-Icestudio!#mac)
  * [Paso 3: Configurar el idioma](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-2:-%C2%A1Poniendo-en-marcha-Icestudio!#paso-3-configurar-el-idioma)
  * [Paso 4: Instalar la *toolchain*](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-2:-%C2%A1Poniendo-en-marcha-Icestudio!#paso-4-instalar-la-toolchain)
  * [Paso 5: Instalar los *Drivers*](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-2:-%C2%A1Poniendo-en-marcha-Icestudio!#paso-5-instalar-los-drivers)
    * [GNU/Linux](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-2:-%C2%A1Poniendo-en-marcha-Icestudio!#habilitaci%C3%B3n-del-driver-en-gnulinux)
    * [MAC OS](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-2:-%C2%A1Poniendo-en-marcha-Icestudio!#habilitaci%C3%B3n-del-driver-en-mac-os)
    * [Windows](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-2:-%C2%A1Poniendo-en-marcha-Icestudio!#habilitaci%C3%B3ninstalaci%C3%B3n-del-driver-en-windows)

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

No les hacemos caso y le damos a **Ejecutar de todas maneras** (Run Anyway). Aún así, nos puede saltar alguna más:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/Icestudio-w10-02.jpg)

En este caso pinchamos en **Sí**, para indicar que permitimos que el instalador haga cambios

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/Icestudio-w10-03.jpg)

Se nos abre el instalador y le damos a **Siguiente**. El instalador detecta automáticamente si tenemos instalado **Python 2.7**. Si no lo está, se procede a su instalación, y luego a la de Icestudio

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/Icestudio-w10-03.jpg)

A continuación indicamos el directorio donde instalador **Icestudio**. En caso de duda usar el que viene por defecto. Pinchamos en **Install**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/Icestudio-w10-05.jpg)

Comienza la instalación. El procesaso durará unos minutos. Una vez acabado nos aparecerá esta pantalla:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/Icestudio-w10-06.jpg)

Pinchamos en **Finalizar**. Hemos acabado la primera parte de la instalación. Se nos abre Icestudio y nos aparecerá una ventana como esta

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/Icestudio-w10-07.jpg)


### Mac

Lo primero es instalar **python 2.7** si no lo tenemos ya. [Los instaladores se encentran en este enlace](https://www.python.org/downloads/mac-osx/)

También necesitamos instalar [Howbrew](https://brew.sh/index_es.html), que es un instalador de paquetes para MAC. Se instala fácilmente siguiendo las instrucciones en su web

A continuación nos vamos al directorio donde hemos descargado el **instalador de Icestudio**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/Icestudio-mac64-01.png)

Pinchamos en el **instalador .dmg** para abrirlo

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/Icestudio-mac64-02.png)

y al cabo de unos segundos nos aparecerá la **pantalla de bienvenida**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/Icestudio-mac64-03.png)

y se empiezan a copiar los archivos a la **carpeta de aplicaciones**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/Icestudio-mac64-04.png)

Al finalizar podemos ver Icestudio entre las **aplicaciones instaladas**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/Icestudio-mac64-05.png)

Lo abrimos para comprobar que está todo ok

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/Icestudio-mac64-06.png)

Nos aparecerá una **advertencia** indicando que es un software que no conocen y que si estamos seguro de que lo queremos abrir. Pinchamos en **open**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/Icestudio-mac64-07.png)

Al cabo de unos segundos nos debe aparecer una pantalla como esta, con **icestudio abierto**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/Icestudio-mac64-08.png)

## Paso 3: Configurar el idioma

Arrancamos icestudio. Lo primero que haremos será **configurar el idioma**. Nos vamos al menú **Edit/Preferences/Language** y seleccionamos el idoma que queramos. Yo lo voy a poner en castellano (pinchando en Spanish), pero se puede poner en Gallego, Euskera, Catalán y Francés

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/icestudio-05.png)

Nos aparecerá otra vez la **ventana principal**, pero con los textos cambiados a nuestro idioma

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/icestudio-05.png)

## Paso 4: Instalar la *toolchain*

Ya podemos **abrir** ejemplos y modficarlos, pero todavía no podemos sintetizarlos en la FPGA porque hay que **instalar las herramientas** (La *Toolchain*). Para hacerlo nos vamos a **Herramientas/Toolchain/Instalar**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/icestudio-linux-06.png)

Comienza su instalación. Nos aparecerá una ventana con una **barra de progreso**. Este proceso puede durar unos minutos

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/icestudio-linux-07.png)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/icestudio-linux-08.png)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/icestudio-linux-09.png)

Al terminar, nos aparecerá una **notificación** verde en la parte inferior derecha de la pantalla indicando que la **toolchain** está instalada. Debajo aparece otra para indicarnos que pinchemos ahí para **instalar los drivers**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/icestudio-linux-10.png)

## Paso 5: Instalar los drivers

En este estado en que estamos, ya podemos **sintetizar circuitos** con Icestudio (se generará el *bitstream*), sin embargo todavía no los podemos descargar en la placa con la FPGA libres. Para hacerlo hay **que habilitar los drivers**

Nos vamos a la opción del menú **Herramientas/Drivers/Habilitar**. Según nuestra plataforma, el proceso de habilitación será diferente

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/icestudio-linux-11.png)

### Habilitación del driver en GNU/Linux

En las plataformas **GNU/Linux** el *driver* ya está integrado en el propio *kernel*, por lo que el proceso será muy rápido. Al darle a la opción de habilitar el *driver* nos aparecerá una ventana para pedirnos la **clave del usuario** para tener permisos para instalar el driver

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/icestudio-linux-12.png)

Y en unos segundos nos aparece la notificación de que **el driver está habilitado**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/icestudio-linux-13.png)

Finalmente hay que **desconectar la placa y volverla a conectar**. ¡Ya tenemos nuestro icestudio listo para trabajar!

### Habilitación del *driver* en Mac OS

El proceso es el mismo que para GNU/Linux. Hay que pinchar en **Herramientas/Drivers/Habilitar**. En unos segundos se finaliza el proceso, y deberá aparecer una **notificación en verde** en la parte inferior derecha

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/Icestudio-mac64-09.png)

### Habilitación/Instalación del driver en Windows

Pinchamos en la opción **Herramientas/Drivers/Habilitar** nos aparecerá una ventana con los pasos a seguir

(en construcción)

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



