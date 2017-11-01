[![Click to see the youtube video](http://img.youtube.com/vi/ELQLphztOjQ/0.jpg)](https://www.youtube.com/watch?v=ELQLphztOjQ&list=PLmnz0JqIMEzXaeYVzf2TfTzRekPIVoljw&index=2)

Haz click en la imagen para ver el **vídeo en Youtube**

# Descripción

Aprenderemos a **Instalar** la herramienta [Icestudio](https://github.com/FPGAwars/icestudio), que es la que usaremos en estos tutoriales para crear los **circuitos digitales** y sintetizarlos en una **FPGA libre**. Cargaremos un circuito "hola mundo", que enciende un led, en la placa [Icezum Alhambra](https://github.com/FPGAwars/https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/icestudio-13.pngicezum/wiki) para comprobar que está todo funcionando correctamente

# Contenido

* [Sobre Icestudio](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-2:-%C2%A1Poniendo-en-marcha-Icestudio!#sobre-icestudio)
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
      * [1.Conectar la placa de la FPGA al USB](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-2:-%C2%A1Poniendo-en-marcha-Icestudio!#1conectar-la-placa-de-la-fpga-al-usb)
      * [2.Seleccionar el driver](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-2:-%C2%A1Poniendo-en-marcha-Icestudio!#2seleccionar-el-driver)
      * [3.Conectar y Desconectar la placa](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-2:-%C2%A1Poniendo-en-marcha-Icestudio!#3-desconectar-y-conectar-la-placa)
  * [Paso 6: Cargar el circuito *Hola Mundo*](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-2:-%C2%A1Poniendo-en-marcha-Icestudio!#paso-6-cargar-el-circuito-hola-mundo)
* [Resolución de problemas](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-2:-%C2%A1Poniendo-en-marcha-Icestudio!#resoluci%C3%B3n-de-problemas) 
* [Ejercicios propuestos](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-2:-%C2%A1Poniendo-en-marcha-Icestudio!#ejercicios-propuestos-6-bitpoints)
* [Ejercicios entregados](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-2:-%C2%A1Poniendo-en-marcha-Icestudio!#ejercicios-entregados)
* [Autor](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-2:-%C2%A1Poniendo-en-marcha-Icestudio!#autor)
* [Licencia](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-2:-%C2%A1Poniendo-en-marcha-Icestudio!#licencia)
* [Créditos y agradecimientos](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-2:-%C2%A1Poniendo-en-marcha-Icestudio!#cr%C3%A9ditos-y-agradecimientos)
* [Enlaces](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-2:-%C2%A1Poniendo-en-marcha-Icestudio!#enlaces)
* [FAQs](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-2:-%C2%A1Poniendo-en-marcha-Icestudio!#faqs)

# Sobre Icestudio

[Icestudio](https://github.com/FPGAwars/icestudio) es una herramienta para **diseño** y **síntesis** de **circuitos digitales** en **FPGAs libres**, creada por [Jesús Arroyo](https://github.com/Jesus89). Está programada en [nodejs](https://nodejs.org). Es **software libre** y **multiplataforma**. Corre en los sistemas GNU/Linux, Mac OS y Windows

Jesús fue el creador también del **escáner 3D** libre [Ciclop](https://github.com/LibreScanner/ciclop) y del software de escaneado 3D [Horus](https://github.com/LibreScanner/horus)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/logo-icestudio.png)

# Instalación de Icestudio

Para poner en marcha Icestudio hay que seguir los **siguientes pasos**


## Paso 1: Descarga del Instalador de Icestudio

* Nos vamos a la [página del Icestudio en github](https://github.com/FPGAwars/icestudio)

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
|  [icestudio-0.3.1-linux64.AppImage](https://github.com/FPGAwars/icestudio/releases/download/0.3.1/icestudio-0.3.1-linux64.AppImage)                 | GNU/Linux, 64-bits | Appimage ejecutable |
|  [icestudio-0.3.1-win64.exe](https://github.com/FPGAwars/icestudio/releases/download/0.3.1/icestudio-0.3.1-win64.exe) | Windows 10, 8, 7, 64-bits | Instalador (Archivo ejecutable) |
| [icestudio-0.3.1-osx64.dmg](https://github.com/FPGAwars/icestudio/releases/download/0.3.1/icestudio-0.3.1-osx64.dmg) | Mac OSX-64 | Instalador para mac |

Si lo que tenemos es un ordenador de **32 bits**, nos descargamos estos ficheros para nuestra plataforma

|  Fichero a descargar  | Plataforma         | Descripción         |
|-----------------------|--------------------|---------------------|
| [icestudio-0.3.1-linux32.AppImage](https://github.com/FPGAwars/icestudio/releases/download/0.3.1/icestudio-0.3.1-linux32.AppImage)                 | GNU/Linux, 32-bits | Appimage ejecutable |
| [icestudio-0.3.1-win32.exe](https://github.com/FPGAwars/icestudio/releases/download/0.3.1/icestudio-0.3.1-win32.exe) | Windows 10, 8, 7, 32-bits | Instalador (Archivo ejecutable) |
| [cestudio-0.3.1-osx32.zip](https://github.com/FPGAwars/icestudio/releases/download/0.3.1/icestudio-0.3.1-osx32.zip) | Instalador para mac | Mac OSX-32 bits | Instalador para mac |

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
chmod +x icestudio-0.3.1-linux64.AppImage
./icestudio-0.3.1-linux64.AppImage
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

Con la placa de la FPGA conectada, pinchamos en la opción **Herramientas/Drivers/Habilitar** nos aparecerá una ventana con los pasos a seguir

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/Icestudio-w10-08.jpg)

La gestión de los **drivers en Windows** siempre es un reto. Con icestudio suele funcionar a la primera, sin embargo, algunos usuarios han reportado que les ha costado encontrar la combinación exacta de controlador/usb necesarios para que les funcione bien. Pero al final se consigue. **No te preocupes si no te funciona a la primera**

El proceso de instalación para el *driver* de otras placas con FPGA que tengan también un chip FTDI, es el mismo que para la Icezum Alhambra. Por ejemplo la **Icestick**

**Importante**: Es necesario tener permisos de administración para la instalación del driver

#### 1.Conectar la placa de la FPGA al USB

En windows se recomienda que la placa esté conectada un **USB 2.0** si es posible. Una opción que funciona muy bien es conectar un **hub usb 2.0** y conectar la placa a través de él

#### 2.Seleccionar el *driver*

Pinchamos en el botón **OK**. Icestudio lanzará la aplicación [Zadig](http://zadig.akeo.ie/) (que se ha instalado con Icestudio). Es la que nos permite instalar el *driver* de la FPGA. Aparecerá una ventana como la siguiente

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/Icestudio-w10-09.jpg)

Pulsamos en el desplegable superior y seleccionamos la opción **IceZUM Alhambra v.1 - Bxx (Interface 0)**

**¡OJo!** Es muy importante que sea el que pone **(Interface 0)**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/Icestudio-w10-10.jpg)

El deplegable se cerrará y nos aparecerá lo que hemos seleccionado. En la casilla que está encima del boton de "Replace driver" debemos seleccionar el **driver libusK** (es muy probable que sea el que aparece por defecto), pero si no, lo seleccionamos con las flechas

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/Icestudio-w10-11.jpg)

Ahora apretamos **Replace driver** y comienza la instalación del driver

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/Icestudio-w10-12.jpg)

En unos segundos nos aparecerá el mensaje de que se ha **instalado correctamente**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/Icestudio-w10-13.jpg)

Pinchamos en **Close** para cerrarla

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/Icestudio-w10-14.jpg)

y este es el aspecto de **Zadig** una vez **instalado el driver**. Ya podemos cerrar la ventana

#### 3. Desconectar y conectar la placa

En la parte inferior derecha de icestudio nos aparecerá una notificación para recordarnos que debemos **desconetar la placa y volver a conectarla**, para que el driver funcione correctamente

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/Icestudio-w10-15.jpg)

**¡¡¡IMPORTANTE!!!** El driver se ha instalado en el USB donde estaba conectada la placa. Hay que conectarla en el mismo USB

Si se quiere usar la placa en otro USB diferente, habrá que volver a instalar el driver en ese USB

## Paso 6: Cargar el circuito "hola mundo"

Ya lo tenemos todo listo. El último paso es comprobar que podemos **cargar** un circuito de ejemplo en la FPGA. **¡Es el momento de la verdad!**. Abrimos el ejemplo "01.Un LED" desde el menú **Archivo/Ejemplos/1.Básico**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/icestudio-07.png)

Nos aparecerá el circuito en el centro de la pantalla, y una **notificación verde** en la parte inferior derecha indicando que se han abierto correctamente

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/icestudio-08.png)

Lo cargamos en la placa dándole a la opción **Herramientas/Cargar**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/icestudio-09.png)

Nos aparece una **notificación** indicando que comienza la carga

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/icestudio-10.png)

y a los pocos segundos el proceso habrá concluido, y si todo ha ido bien, aparecerá una **notificación verde** en la esquina inferior derecha indicando que la **carga** se ha realizado **correctamente**. Adicionalmente aparecerá otra notificación con **la cantidad de recursos de la FPGA ocupados** por el circuito hola mundo. En los siguientes tutoriales explicará esto con más detalle

En la placa veremos cómo el **LED0** está encendido (verde) y el resto apagados:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/icestudio-12.jpg)

**¡Enhorabuena!** Acabas de sintetizar y probar tu primer circuito en una FPGA libre

## Resolución de problemas

Estos son los errores más comunes y las posibles soluciones

### Placa Icezum Alhambra no detectada

Al **cargar** el programa "hola mundo" nos aparece este mensaje de error

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/icestudio-13.png)

Este mensaje aparece por estos motivos:

1. **La placa NO está conectada al USB**.  Por despiste se nos ha olvidado conectarla, o la hemos conectado a un hub USB que no está conectado al ordenador. Solución: Conectar la placa y volver a cargar

2. **La placa NO está correctamente conectada por el USB**. Desconectarla y volverla a conectar. Asegurarse que se hace buen contacto por ambas partes: el lado del Ordenador y el lado de la FPGA

3. **El cable usado no es de datos**. Algunos cables USB - microUSB son sólo para cargar los móviles u otros dispositivos, y no tienen los hilos de datos. Solución: Usar el cable para conectar un móvil al PC y comprobar si desde el ordenador se detecta el móvil y se pueden transferir datos. Con esto verificamos si el cable es correcto

4. **Problemas con el driver**. El driver no está correctamente instalado, o hace conflicto con algún otro controlador. Esto sucede en algunas **máquinas Windows**. Para solucionar el problema prueba alguna de las siguientes opciones:  
    * Asegúrate de que has conectado la placa en el **mismo USB** donde instalaste el driver. En windows los controladores se instalan para un USB concreto (en los sistemas Linux/Mac son válidos para cualquiera)
    * Enchufa la placa en otro USB, a ser posible USB 2.0. Vuelve a instalar el driver para ese USB y prueba otra vez la carga. Iterar hasta encontrar un USB donde funcione correctamente. En algunos windows ha funciona a la tercera o cuarta. Una vez que funciona, ya lo hace siempre
    * Si el problema persiste, conecta la placa a través de un hub USB 2.0 y vuelve a instalar el driver. Esto suele funcionar bastante bien

5. **El problema persiste**. Si has probado todo lo anterior pero no consigues que funcione, envíanos un correo a la [Lista de FPGAwars](https://groups.google.com/forum/#!forum/fpga-wars-explorando-el-lado-libre), dando todos los detalles que puedas, para que entre todos te echemos una mano

# Ejercicios propuestos (6 BitPoints)

* **Ejercicio 1**: Instalar Icestudio. Abrir el ejemplo **01.LEDON** y sintetizarlo con **Herramientas/Sintetizar**. Aunque no tengáis placa física lo podéis hacer. Enviar el pantallazo en el que aparece la notificación verde de que se ha sintetizado bien por **twitter** o **G+**, con mención a @Obijuan_cube. Valor: **1 BitPoint**

* **Ejercicio 2**: Conectar la placa y cargar el ejemplo **01.LEDON**. Enviar el pantallazo de que la carga se ha realizado correctamente y una foto de la placa con el LED0 encendido, por Twitter o G+, con mención a @Obijuan_cube. Valor: **2 Bitpoins** (uno por cada pantallazo)

* **Ejercicio 3**: Enviar los 3 pantallazos anteriores al [repositorio de entregas del Github](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/tree/master/Tutorial-2), en el directorio **Tutorial-2** y la carpeta con vuestro nombre. Valor: **3 BitPoints** (Uno por cada pantallazo)

# Ejercicios entregados

## Alberto Valero

 ![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-2/avalero/verify.png)

 ![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-2/avalero/upload.png) |

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-2/avalero/foto_ledon.jpg)

### Diego Lale

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-2/DiegoLale/ejercicio_1.png)

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-2/DiegoLale/ejercicio2_1.png)

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-2/DiegoLale/ejercicio%202_2.jpg)

### Miquel Servera

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/entregas/Miquel-servera-Ejercicio-1.jpg)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/entregas/Miquel-servera-Ejercicio-2-1.jpg)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-02/entregas/Miquel-servera-Ejercicio-2-2.jpg)

# Autor

* [Juan González-Gómez](https://github.com/Obijuan) (Obijuan)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/logos-urjc-gsyc-peloto-jderobot.png)

# Licencia

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/attribution-share-alike-creative-commons-license.png)

# Créditos y agradecimientos

* [Clifford Wolf](http://www.clifford.at/) es el Ingeniero Austriaco al que le debemos la aparición de las FPGAs libres. Todo este tutorial,y todas las herramientas creadas a su alrededor no habrían sido posibles sin su gran aportación: [El proyecto Icestorm](http://www.clifford.at/icestorm/). ¡Muchas gracias!
* [Jesús Arroyo](https://github.com/Jesus89) es el creador de [Icestudio](https://github.com/FPGAwars/icestudio) y su desarrollador principal. Gracias a su talento está consiguiendo que cientos de personas puedan acceder al desarrollo de circuitos digitales, de una forma muy sencilla. ¡Muchas gracias!
* **Eladio Delgado**, es el diseñador de la placa IceZum Alhambra. Y el encargado de la gestión de la fabricación de la placa. Todo lo dirige desde su Rural Workshop en [Pinos del Valle](https://es.wikipedia.org/wiki/Pinos_del_Valle) (Granada) ¡Muchas gracias!
* **Andrés Prieto-Moreno**, por todos los pantallazos de Icestudio en Windows 10 y Mac. ¡Muchas gracias!

# Enlaces

* [Proyecto Icestorm](http://www.clifford.at/icestorm/)
* [FPGAwars](http://fpgawars.github.io/): Explorando el lado libre de las FPGAs
* [Icestudio](https://github.com/FPGAwars/icestudio)
* [Tarjeta Icezum Alhambra](https://github.com/FPGAwars/icezum/wiki)
* [AlhambraBits](https://alhambrabits.com/)


# FAQs

* **¿Dónde puedo conseguir la placa Icezum Alhambra?**

Pueden conseguir una desde [Alhambrabits](https://alhambrabits.com/buy/)

* **¿Cómo aprendo a manejar github?**

Hay mucha información en internet. En su momento hice este Tutorial: [Github y FreeCAD](http://www.iearobotics.com/wiki/index.php?title=Tutorial:_Github_y_Freecad) para enseñar a manejarlo. Los ejemplos están hechos con ficheros de FreeCAD, sin embargo, lo que se enseña es genérico. También vale para las entregas de los ejercicios del tutorial de Electrónica digital para makers

