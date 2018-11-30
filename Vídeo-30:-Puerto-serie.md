![]()

# Vídeo

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

Haz click en la imagen para ver el **vídeo en Youtube**

# Descripción


# Colección

**Academia-Jedi-HW-30.zip**: Colección para este tutorial. Descargar e instalar 

# Contenido

* [Introducción](#introducci%C3%B3n)
* [Puesta en marcha](#puesta-en-marcha)
  * [Terminal de comunicaciones](#terminal-de-comunicaciones)
    * [Instalación de Arduino-IDE](#instalaci%C3%B3n-de-arduino-ide)
      * [GNU/Linux Ubuntu 18.04](#gnulinux-ubuntu-1804)
      * [Windows 10](#windows-10) 
    * [Instalación del ScriptCommunicator](#instalaci%C3%B3n-del-scriptcommunicator)
      * [ScriptCommunicator en Gnu/Linux Ubuntu 18.04](#scriptcommunicator-en-gnulinux-ubuntu-1804)
      * [ScriptCommunicator en Windows 10](#scriptcommunicator-en-windows-10) 
   * [Primera prueba](#primera-prueba)
     * [Ejemplo 1: Comprobación de las señales a nivel físico](#ejemplo-1-comprobaci%C3%B3n-de-se%C3%B1ales-a-nivel-f%C3%ADsico)
     * [Probando las señales de control con el ScriptCommunicator](#probando-las-se%C3%B1ales-de-control-con-el-scriptcommunicator)
* [Transmisor serie](#transmisor-serie)
  * [Ejemplo 2: Enviando un carácter al apretar un botón](#ejemplo-2-env%C3%ADo-de-un-car%C3%A1cter-al-apretar-un-bot%C3%B3n)
  * [Ejemplo 3: Enviando un número en binario](#ejemplo-3-enviando-un-n%C3%BAmero-en-binario)
  * [Ejemplo 4: Circuito BCD a ASCII](#ejemplo-4-circuito-bcd-a-ascii)
  * [Ejemplo 5-1: Transmisor de 16 bits](#ejemplo-5-1-transmisor-de-16-bits)
    * [Funcionamiento del transmisor de 16 bits](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-30:-Puerto-serie#funcionamiento-del-transmisor-de-16-bits)
  * [Ejemplo 5-2: Bloque transmisor de 16 bits](#ejemplo-5-2-bloque-transmisor-de-16-bits)
  * [Ejemplo 6-1: Enviando una cadena](#ejemplo-6-1-enviando-una-cadena)
  * [Funcionamiento del transmisor de cadenas](#funcionamiento-del-transmisor-de-cadenas)
  * [Ejemplo 6-2: Usando el bloque serial-tx-str](#ejemplo-6-2-usando-el-bloque-serial-tx-str)
  * [Ejemplo 6-3: Leyendo la cadena de un fichero](#ejemplo-6-3-leyendo-la-cadena-de-un-fichero)
  * [Ejemplo 6-4: Generación de una cadena desde un programa en python](#ejemplo-6-4-generaci%C3%B3n-de-una-cadena-desde-un-programa-en-python)
  * [Funcionamiento del transmisor](#funcionamiento-del-transmisor)
  * [Ejemplo 7: Midiendo las señales con el analizador Saleae](#ejemplo-7-midiendo-las-se%C3%B1ales-con-el-analizador-saleae)
* [Receptor serie](#receptor-serie)
  * [Ejemplo 8: Recibiendo datos del PC](#ejemplo-8-recibiendo-datos-del-pc)
  * [Ejemplo 9: Contador de datos recibidos](#ejemplo-9-contador-de-datos-recibidos)
  * [Ejemplo 10: Control de un servo con dos teclas](#ejemplo-10-control-de-un-servo-con-dos-teclas)
  * [Ejemplo 11: Control de un servo a cualquier posición](#ejemplo-11-control-de-un-servo-a-cualquier-posici%C3%B3n)
  * [Funcionamiento del receptor](#funcionamiento-de-receptor)
  * [Ejemplo 12: Midiendo el receptor](#midiendo-el-receptor)
* [Combinando transmisor y receptor](#combinando-transmisor-y-receptor)
  * [Ejemplo 13: Haciendo eco de los datos recibidos](#ejemplo-13-haciendo-eco-de-los-datos-recibidos)
  * [Ejemplo 14: Mini cifrador](#ejemplo-14-mini-cifrador)
* [Aplicaciones](#aplicaciones)
  * [Comunicación con arduino por puerto serie](#comunicaci%C3%B3n-con-arduino-por-puerto-serie)
    * [Servidor hardware en la FPGA](#servidor-hardware-en-la-fpga)
    * [Software en el arduino](#software-en-el-arduino)
    * [Probando la aplicación](#probando-la-aplicaci%C3%B3n)
  * [Comunicando los programas del PC con los circuitos](#comunicando-los-programas-del-pc-con-los-circuitos)
    * [Servidor hardware](#servidor-hardware)
    * [Software en el PC](#software-en-el-pc)
    * [Ejemplo 16: Secuencia de movimiento](#ejemplo-16-secuencia-de-movimiento)
    * [Ejemplo 17: Control interactivo del servo](#ejemplo-17-control-interactivo-del-servo)
* [Ejercicios propuestos (25 Bitpoints)](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-30:-Puerto-serie#ejercicios-propuestos-25-bitpoints)
* [Ejercicios entregados](#ejercicios-entregados)
* [Autor](#autor)
* [Licencia](#licencia)
* [Enlaces](#enlaces)
* [Preguntas frecuentes](#preguntas-frecuentes)

# Introducción

Una forma sencilla de **comunicar** nuestros circuitos de la **FPGA** con el **PC** es usando el [Puerto serie](https://es.wikipedia.org/wiki/Puerto_serie). Se trata de comunicaciones **serie ASÍNCRONAS** y se usan muchísimo en los dispositivos. Con ellas nos podemos comunicar también con otros dispositivos, como bluetooth-serie, Arduinos, microcontroladores, etc

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/intro-01.png)

Se utiliza un **único cable de datos** para cada sentido. El **pin** por el que sale la información se llama **TX**, y por el que entra **RX**. No hay un cable con la señal de reloj, como en las comunicaciones serie síncronas que vimos en el tutorial anterior. La **velocidad** se **acuerda** a priori 

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/intro-02.png)

Este es el **esquema típico** de conexión de dos dispositivos. Las **velocidades** de comunicación están **estandarizadas**, y se deben acordan a priori entre los dispositivos. Tipicamente se usan **9600** ó **115200 baudios** (pero hay más). En este contexto, un baudio equivale a una velocidad de **1 bit por segundo** (bps)

Cuando hablamos de **puerto serie en el PC**, nos estamos refieriendo usualmente a la [Norma RS-232](https://es.wikipedia.org/wiki/RS-232), que además de las comunicaciones serie asíncronas, define más cosas, como por ejemplo **6 cables de control**, que son **opcionales**: DTR, RTS, CTS, DSR, DCD y RI 

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/intro-03.png)

Estos cables de control son muy útiles. La señales **DTR** o **RTS**, por ejemplo, se usan en las placas de **Arduino** para que el PC haga un **reset** de la placa, para activar el bootloader y cargar el programa. Nosotros los podemos usar en nuestros circuitos como **pines de E/S** genéricos, con el PC

Los **ordenadores modernos** no tienen los **conectores** del puerto serie. Pero como se sigue usando mucho, han aparecido unos chips que son **USB-serie**: se conectan al PC por el **USB** y nos ofrecen todas las señales del **puerto serie**. Los más extendidos son los del fabricante [FTDI](https://www.ftdichip.com/)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/intro-04.png)

En la **Icezum Alhambra** se usa el [chip FT2232H](https://www.ftdichip.com/Products/ICs/FT2232H.htm) que ofrece dos **interfaces** a través del **USB**. Uno de **comunicaciones serie síncronas** (bus spi) para realizar la carga de los circuitos y otro de **puerto serie**, realizando la conversión **USB-serie** y dando acceso a las señales de la norma **RS-232** desde la FPGA

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/intro-05.png)

Desde los pines de la FPGA se tiene acceso a las señales **TX** y **RX** para la trasmisión/recepción de datos, así como a las señales de control **DTR**, **RTS**, **CTS**, **DSR** y **DCD**. De estas, dos son de entrada (PC->FPGA) y tres de salida (FPGA->PC)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/intro-06.png)

En **Icestudio** accedemos a los **pines del puerto serie** seleccionando la etiqueta con el nombre de la señal: TX y RX para las señales de **datos**, y DTR, RTS, CTS, SDR y DCD para las de **control**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/intro-07.png) 

# Puesta en marcha

Para empezar a trabajar con el **puerto serie** necesitamos instalarnos un **terminal de comunicaciones**, desde el que **enviar datos** a nuestros **circuitos** en la **FPGA** y en el que visualizar la información **recibida** de ellos. Haremos pruebas para comprobar que funciona correctamente, antes de diseñar nuestros circuitos 

## Terminal de comunicaciones

Se puede utilizar **cualquier terminal** de los que existen, en cada sistema operativo. En este tutorial usaremos dos: el [Arduino-Ide](https://www.arduino.cc/en/Main/Software) (1.8.7) y el [ScriptComunicator](https://github.com/szieke/ScriptCommunicator_serial-terminal) (5.09), que son **libres** y **multiplataforma**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/intro-08.png)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/intro-09.png)

### Instalación de Arduino-IDE

Los **pasos concretos** de instalación dependen del **sistema operativo** usado. En **general**, los pasos son:

* Acceder a la [web del Arduino-IDE](https://www.arduino.cc/en/Main/Software)
* **Descargar** el fichero de instalación del entorno para tu sistema operativo
* **Ejecutar** el fichero de instalación
* **Lanzar** el entorno

#### GNU/Linux Ubuntu 18.04

Si eres usuario de Linux habitual de linux, lo instalarás sin problemas siguiendo las **instrucciones anteriores**. Aquí  voy a poner las instrucciones para hacerlo desde la **interfaz gráfica**, para usuarios que **saben poco a nada de Linux**

* **Paso 0**: Configura el **navegador de archivos** (Nautilus) para poder **ejecutar** programas haciendo **doble click** desde la interfaz gráfica. Esta opción no está activada por defecto
  * Abrir el **navegador** de archivos
  * Abrir las **preferencias** desde el menú Archivos/preferencias (Files/preferences)
  * Seleccionar la pestaña **comportamiento** (Behavior)
  * **Activar** la opción "Preguntar qué hacer" (Ask what to do) en "Ficheros ejecutables de texto" (Executable Text Files)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Arduino-linux-01.gif)

* **Paso 1**: Descarga el fichero **arduino-1.8.7-linux64.tar.xz** (o la última versión) desde la [web de Arduino](https://www.arduino.cc/en/Main/Software)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Arduino-linux-02.gif)

* **Paso 2**: Descomprimir el fichero **arduino-1.8.7-linux64.tar.xz**.  Por defecto tendremos el fichero en la carpeta de **Descargas** (Downloads). Navegamos a esa carpeta y sobre el archivo arduino-1.8.7-linux64.tar.xz apretamos el **botón derecho** del ratón y seleccionamos la opción: **extraer aquí** (extract here)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Arduino-linux-03.gif)

Como el archivo es grande, esta acción tardará unos 15 segundos o más (dependiendo de nuestro ordenador). Al cabo de ese tiempo nos aparecerá la **carpeta arduino-1.8.7-linux64**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Arduino-linux-04.png)

* **Paso 3**: Arrancar el entorno de Arduino. Entramos en la carpeta arduino-1.8.7-linux64, damos **permisos de ejecución** al fichero **arduino** y hacemos **docle click** en él. En la ventana que aparece pinchamos en "Ejecutar" (Run)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Arduino-linux-05.gif)

Nos aparecerá la **ventana principal** del entorno de arduino:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Arduino-linux-06.png)

* **Paso 4** (Opcional): **Instalación** del Entorno de arduino.  Si lo vamos a usar mucho, es mejor tenerlo **instalado en el sistema**, y añadirlo en la barra de aplicaciones favoritas. Lo único que tenemos que hacer es ejecutar el archivo **install.sh**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Arduino-linux-07.gif)

**¡Ya está instalado!** :-) Para arrancarlo pinchamos en el icono para **mostrar las aplicaciones** (abajo a la izquierda)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Arduino-linux-08.jpg)

y nos ahí nos aparecerá el **Arduino Ide**. Lo arrancamos pinchando en su icono. Opcionalmente, una vez arrancado, lo podemos añadir a favoritos para que se quede anclado en la barra de aplicaciones

#### Windows 10

* **Paso 1**: Conéctate a la [web del IDE de Arduino](https://www.arduino.cc/en/Main/Software) y pincha en la primera opción **Windows Instaler** 

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Arduino-win10-01.png)

* **Paso 2**: Descargar el fichero **arduino-1.8.7-windows.exe**, que nos aparecerá al pinchar en la opción **Just Download**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Arduino-win10-02.png)

* **Paso 3**: Ir a la carpeta de **Descargas** y ejecutar el instalador (arduino-1.8.7-windows.exe)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Arduino-win10-03.png)

Al ejecutarlo aparecerá la siguiente **pantalla de aviso**. Pinchamos en **Sí**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Arduino-win10-04.jpg)

Aparece la siguiente pantalla: Pinchamos en **I Agree**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Arduino-win10-05.png)

Por defecto dejamos que se **instale todo**. Pinchamos en **Next**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Arduino-win10-06.png)

El Entorno se instala en **C:\\Program Files(x86)\\Arduino\\**. Dejamos esa ubicación por defecto y pinchamos en **Install**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Arduino-win10-07.png)

Comienza la instalación de los ficheros. Este proceso puede tardar unos minutos. Al terminar pinchamos en **Close**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Arduino-win10-08.png)

* **Paso 4**: Abrir el entorno. En el escritorio aparecerá el icono de Arduino. Pinchamos y lo ejecutamos. Nos aparecerá la pantalla principal:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Arduino-win10-09.png)

¡Ya lo tenemos **instalado** y **listo** para usar!

### Instalación del ScriptCommunicator

Los **pasos concretos** de instalación dependen del **sistema operativo** usado. En **general**, los pasos son:

* Acceder a la [web del ScriptCommunicator](https://github.com/szieke/ScriptCommunicator_serial-terminal)
* **Descargar** el fichero de instalación del entorno para tu sistema operativo
* **Ejecutar** el fichero de instalación
* **Lanzar** el entorno

#### ScriptCommunicator en Gnu/Linux Ubuntu 18.04

Si eres usuario de Linux habitual de linux, lo instalarás sin problemas siguiendo las **instrucciones anteriores**. Aquí  voy a poner las instrucciones para hacerlo desde la **interfaz gráfica**, para usuarios que **saben poco a nada de Linux**

* **Paso 0**: Configura el **navegador de archivos** (Nautilus) para poder **ejecutar** programas haciendo **doble click** desde la interfaz gráfica. Esta opción no está activada por defecto. Sigue las mismas instrucciones del [paso 0 de la instalación del Arduino IDE](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-30:-Puerto-serie#gnulinux-ubuntu-1804), si no lo has hecho ya

* **Paso 1**: Descarga el fichero **ScriptCommunicator_05_09_linux_64_bit.zip** (o la última versión) desde la [web del ScriptCommunicator](https://github.com/szieke/ScriptCommunicator_serial-terminal)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/SC-linux-01.gif)

* **Paso 2**: Descomprimir el fichero **ScriptCommunicator_05_09_linux_64_bit.zip**.  Por defecto tendremos el fichero en la carpeta de **Descargas** (Downloads). Navegamos a esa carpeta y sobre el archivo ScriptCommunicator_05_09_linux_64_bit.zip apretamos el **botón derecho** del ratón y seleccionamos la opción: **extraer aquí** (extract here). Nos metemos en la carpeta **ScriptCommunicator_05_09_linux_64_bit**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/SC-linux-02.gif)

* **Paso 3**: Arrancamos el script communicator. Entramos en la carpeta **ScriptCommunicator_05_09_linux_64_bit**, damos **permisos de ejecución** al fichero **ScriptCommunicator.sh** y hacemos **docle click** en él. En la ventana que aparece pinchamos en "Ejecutar" (Run)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/SC-linux-03.gif)

Nos aparecerá la **ventana principal** del ScriptCommunicator:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/SC-linux-04.png)

¡Ya lo tenemos **listo** para usar!

#### ScriptCommunicator en Windows 10

* **Paso 1**: Conéctate a la [web del ScriptCommunicator](https://github.com/szieke/ScriptCommunicator_serial-terminal) y descarga el archivo **ScriptCommunicatorSetup_05_09_windows.zip**

La zona de descarga se encuentra en la parte final de la web:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/SC-win10-01.png)

Pincha en la primera opción: **Windows**.  Aparecerá una web nueva y al cabo de unos segundos podremos **comenzar la descarga**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/SC-win10-02.png)

**Paso 2**: Descomprime el fichero y ejecuta el instalador

En la carpeta de **Descargas** tenemos el fichero **ScriptCommunicatorSetup_05_09_windows.zip**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/SC-win10-03.png)

Nos situamos encima del fichero, y apretamos el botón derecho del ratón. Pinchamos en la opción **Extraer todo**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/SC-win10-04.png)

Se crea la carpeta **ScriptCommunicatorSetup_05_09_windows** y dentro de ella está el **instalador**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/SC-win10-05.png)

**Ejecutamos** el instalador **como administrador**, situándonos encima y pinchando con el botón derecha. Elegimos la opción **Ejecutar como Administrador**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/SC-win10-06.png)

En algunos equipos nos puede aparece un mensaje de **advertencia**, en el que se **impide** la ejecución del instalador (Windows es muy pesado)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/SC-win10-07.png)

Pinchamos en **más información** y luego en **Ejecutar de todas formas**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/SC-win10-08.png)

...Y nos aparece un nuevo **mensaje de advertencia** (Windows es cansino, cansino...). Pinchamos en **Sí**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/SC-win10-09.jpg)

Ya por fin arranca el instalador. El programa se instala por defecto en **C:\\Program Files (x86)\\ScriptCommunicator_5.09**. Pinchamos en **Next**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/SC-win10-10.png)

Volvemos a pinchar en **Next**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/SC-win10-11.png)

Y ahora en **Install**. Comienzan a instalarse los archivos

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/SC-win10-12.png)

Al cabo de unos segundos el proceso habrá **terminado**, y aparece la última ventana. Pinchamos en **Finish**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/SC-win10-13.png)

**Paso 3**: Lanzar el **ScriptCommunicator**. Al terminar la instalacion se lanza automáticamente. También tendremos un acceso directo desde el **Escritorio** para lanzarlo. Nos aparecerá una pantalla como esta:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/SC-win10-14.png)

¡Ya lo tenemos **listo** para empezar!

## Primera prueba

Haremos una primera prueba para comprobar que está todo funcionando. Esta prueba la haremos a **nivel físico**: no usaremos ningún circuito transmisor ni receptor todavía. Simplemente **uniremos cables** y mostraremos en los **LEDs** las **señales de control**

### Ejemplo 1: Comprobación de señales a nivel físico

Cargamos este circuito en la FPGA. El cable **RX**, por donde llegan los datos, está unido directamente al de **TX**, por donde se envían. Así, todo lo que llega se devuelve, sin ningún tipo de procesado. Las señales de control **DTR** y **RTS** están conectadas a los **LEDs 7** y **0** respectivamente. Y los **pulsadores** a las señales **CTS**, **DCD** y **DSR**, a través de un **decodificador** de 2 a 4

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Ej1-01.png)

Lo **cargamos** en la placa

Primero **probaremos** su funcionamiento con el **Arudino IDE**. Lo lanzamos y seleccionamos el **puerto serie** desde **Tools/Port**. El **nombre** del dispositivo depende del **sistema operativo** que usemos:
* **Linux**: Dispositivo **/dev/ttyUSB1** (Aparecerá también el /dev/ttyUSB0, pero NO es el correcto)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Ej1-02.png)

* **Windows**: Dispositivo **COMx**, donde la X es un número que varía de un ordenador a otro. En el ordenador donde se ha probado estaba en el **COM4**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Ej1-05.png)

* **MAC**: TODO

Abrimos el **terminal serie** y hacemos una prueba de envío de varias cadenas. Veremos cómo recibimos las mismas (el eco). Es indiferente la velocidad a la que esté configurado el terminal

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Ej1-03.gif)

Vemos cómo los **LEDs** de **TX** y **RX** de la Icezum Alhambra se encienden unos instantes. Se corresponden con las señales TX y RX del PC, y nos indican que hay **datos** que se están **intercambiando** con el **PC**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Ej1-04.png)

Desde el entorno de Arduino **NO** tenemos acceso a las señales de control, por lo que para la siguiente prueba usaremos el **ScriptCommunicator**

### Probando las señales de control con el ScriptCommunicator

Abrimos el **ScriptCommunicator**. Pinchamos en el botón de **Settings** para seleccionar el **puerto serie**. Si estamos en Linux seleccionamos el **/dev/ttyUSB1**. La velocidad es indiferente, de momento. Pinchamos en **Close** para volver

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Ej1-06.gif)

En windows es igual, pero seleccionamos el **COM4**, que es donde está el puerto serie de la Icezum Alhambra en este ordenador

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Ej1-07.png)

Para comenzar las pruebas nos conectamos a la placa pinchando en **Connect**. Comprobamos que el **eco funciona** (igual que en el IDE de arduino). Vemos que las señales **CTS**, **DSR** y **DCD** están a **1**. Al apretar los **pulsadores**, se pondrá a **0** la seleccionada (tienen la lógica invertica). Los **LEDS** 7 y 0 estarán **encendidos**. Pinchando en **DTR** y **RTS** se cambia su estado.

En este **vídeo** se muestra el ejemplo en **acción**:

[![Click to see the youtube video](http://img.youtube.com/vi/m4nKp2PAnJ8/0.jpg)](https://www.youtube.com/watch?v=m4nKp2PAnJ8)

Ahora que ya tenemos **todo funcionando**, es momento de **aprender** a hacer circuitos que se **comuniquen** mediante el **puerto serie**

# Transmisor Serie

El **envío de datos** desde la **FPGA** al **PC** lo realizamos a través del **transmisor serie**. El bloque de Icestudio está disponible en el menú **Varios/Serial/Serial-tx** de la colección **Academia-Jedi-HW-30**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/tx-01.png)

El **dato a transmitir** se introduce por la **entrada de datos**, de **8 bits**. Al generar el **tic de transmisión**, se captura el dato y se envía por la línea serie (TX). Es un funcionamiento similar a la captura de los registros

Hasta que el dato no se haya transmitido completamente, **NO** se puede enviar el siguiente. El **estado** del transmisor lo sabemos por su salida **Busy**: que indica si está **ocupado** o no. Cuando se ha enviado el dato actual, emite el **tic de dato transmitido**

La **velocidad de transmisión** la fijamos mediante el **parámetro**. Tenemos que introducir alguna de las velocidades estándares (en baudios): 300, 600, 1200, 2400, 4800, 9600, 19200, 38400, 57600 ó 115200. Por **defecto** se usan **115200 baudios** 

## Ejemplo 2: Envío de un carácter al apretar un botón

Empezaremos con el **ejemplo** más sencillo: Enviar un **carácter constante** al PC cada vez que apretamos el **pulsador SW1** de la Icezum Alhambra. Cuando se haya enviado, encenderemos un **LED** durante **100ms**. El circuito es el siguiente:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/tx-02.png)

El dato a enviar es el carácter **"A"**. Lo introducimos como una **constante de 8 bits**, y bien podemos indicar su código ascii, o bien el propio carácter usando las dobles comillas. El **tic** que aparece al **apretar el pulsador** lo usamos como **tic de tranmsión**, conectándolo a la entrada txmit. El **tic de dato enviado** se introduce en un **temporizador** para generar un **pulso de 100m**s que enciende el **LED 0** durante ese tiempo

La velocidad se ha configurado a **115200 baudios**, mediante el parámetro. La salida **TX** se conecta directamente al **pin de TX**, para que el dato serie llegue al PC

**Cargamos** el circuito y lo **probamos**. En el PC arrancamos el **ScriptCommunicator**, configurado a la velocidad de **115200 baudios**. Comprobamos cómo llega una "A" con cada pulsación, y un parpadeo en el LED0

[![Click to see the youtube video](http://img.youtube.com/vi/lvwHe6r3xLs/0.jpg)](https://www.youtube.com/watch?v=lvwHe6r3xLs)

La **configuración** que estoy usando en el ScriptCommunicator en **Linux** es la siguiente:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/tx-03.png)

y las opciones de la **consola** son estas (como referencia)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/tx-04.png)

En esta **animación** se puede ver con más detalle el funcionamiento del ejemplo anterior. El tamaño de la letra de la consola se ha agrandado para que se vea mejor

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/tx-05.gif)

## Ejemplo 3: Enviando un número en binario

En este ejemplo enviaremos al PC los números introducidos en binario mediante **3 interruptores externos**. Al apretar el botón de **ENTER**, el número se mostrará en el **display de 7 segmentos** y se enviará al PC. Cada vez que se envía un dato se enciende un **LED** durante **100ms**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/tx-06.png)

Como el número es de **3 bits** y el transmisor envía números de **8 bits**, usamos un componente "acoplador" que pasa de 3 a 8 bits, rellenando con 0s los bits de mayor peso. En el **montaje** tenemos los **3 interruptores**, el **botón de enter**, el **LED de transmisión** y el **display de 7 segmentos**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/tx-07.png)

Lo **cargamos** y lo **probamos**. Cada vez que se aprieta el pulsador de **enter** se envía el número actual

[![Click to see the youtube video](http://img.youtube.com/vi/prQutJDUwB4/0.jpg)](https://www.youtube.com/watch?v=prQutJDUwB4)

Lo que se está enviando son **números crudos**. El **ScriptCommunicator** tiene un par de pestañas activables que nos permiten visualizar el **dato recibido** en **hexadecimal** y en **binario**. Si lo visualizamos en ASCII, veremos "Basura", ya que lo que se envían no se corresponde con caracteres ASCII visibles

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/tx-09.png)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/tx-10.png)

Se **activan** desde la ventana de **Settings**, pinchando en las casillas **hex** y **binary**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/tx-08.png)

## Ejemplo 4: Circuito BCD a ASCII

La mayoría de **terminales serie**, como el de Arduino IDE, sólo muestran la **información en ASCII** (y no números en crudo como el ScriptCommunicator). Para poder visualizar los **dígitos 0-9** en estos terminales, hay que realizar una **conversión** de **binario a ASCII**

La **tabla de conversión** es la siguiente:

|  Número BCD | Código ASCII (hex) | Dígito |
|-------------|--------------------|--------|
|  0000       | 30                 | 0      |
|  0001       | 31                 | 1      |
|  0010       | 32                 | 2      |
|  0011       | 33                 | 3      |
|  0100       | 34                 | 4      |
|  0101       | 35                 | 5      |
|  0110       | 36                 | 6      |
|  0111       | 37                 | 7      |
|  1000       | 38                 | 8      |
|  1001       | 39                 | 9      |
 
Esta conversión se implementa muy fácilmente mediante una **tabla** de 4 **entradas** y **8 salidas**. Para los valores superiores a 9 se usan los caracteres **hexadecimales**. De esta forma nos sirve tanto para convertir dígitos decimales y hexadecimales

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/tx-11.png)

Utilizaremos el **spiner** conectado a un **sensor IR** para contar las pasadas que dan sus brazos, en un **contador** decimal de **4 bits**. Su valor se muestra en **decimal** en un **display de 7 segmentos** y se envía el **dígito ASCII** para verlo en el **terminal serie**. El **montaje** es el siguiente:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/tx-12.png)

Este es el circuito. Los **tics del Spiner** incrementan el **contador de 4 bits**, cuya salida se saca por el **display de 7 segments** y se convierte a **dígito ASCII** antes de enviarlo por el **puerto serie**. El primer tic recibido está **retrasado** un periodo para que se incremente primero el contador y empiece a contar desde 1 

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/tx-13.png)

Se han añadido dos componentes auxiliares para hacer el ejemplo más compacto: un **IR de tics con sonido**, que emite un **pitido** cada vez que se recibe un tic del spiner, y el componente **flash** que enciende el **LED** durante 50ms para indicar que el dígito se ha enviado

En este **vídeo** se puede ver el ejemplo en funcionamiento. Se usa el **terminal** del **Arduino IDE** para mostrar los **dígitos** recibidos

[![Click to see the youtube video](http://img.youtube.com/vi/8FGQPXt7DuE/0.jpg)](https://www.youtube.com/watch?v=8FGQPXt7DuE)

Este es el aspecto del terminal del **Arduino IDE** tras girar el **spiner** un tiempo, después de inicializarlo. Se observan los **dígitos ASCII** recibidos, y cómo el primero es el **1**, y no el 0, gracias a la acción del **biestable D** que retrasa el primer tic

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/tx-14.png)

## Ejemplo 5-1: Transmisor de 16 bits

El **puerto serie** funciona con **datos de 8 bits**. Si queremos enviar un **dato de 16 bits**, debemos **partirlo** en dos de 8 bits, y enviarlos por separado. Este es un ejemplo de un circuito que nos permite hacer eso, y que veremos detalladamente a continuación

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Ej-5-1-01.png)

Primero veremos qué hace: al apretarse el **pulsador** se emite un pitido y se envían los caracteres **J** y **A** seguidos, uno a continuación de otro. El LED parpadea cuando se han enviado el dato. Esto es lo que aparecerá en el terminal al **apretar varias veces el botón**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Ej-5-1-02.png)

El **montaje** es muy básico: sólo están el **pulsador** para enviar, el **LED** y el **zumbador**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Ej-5-1-03.png)

Lo **cargamos** y lo **probamos**. Cada vez que se aprieta el pulsador aparece la palabra "JA" en el terminal. Primero se envía la "J" (byte alto) y luego la "A" (byte bajo)

[![Click to see the youtube video](http://img.youtube.com/vi/xAhNkr0uT5w/0.jpg)](https://www.youtube.com/watch?v=xAhNkr0uT5w)

### Funcionamiento del Transmisor de 16 bits

El **transmisor** se encuentra en dos estados: **transmitiendo** y **apagado**. Esto lo determina el **biestable RS** de estado. Inicialmente está a **0** (apagado). Al recibirse el **tic de enviar dato** se activa, y pasa a **1**. En su salida hay un **detector de flanco de subida** que emite un tic cuando **arranca** (paso de apagado a encendido)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Ej-5-1-04.png)

Usamos un **biestable de cambio** para seleccionar qué byte enviar: **0** para el byte de menor peso y **1** para el de mayor. Inicialmente tiene el valor 1, porque primero enviamos el de mayor peso. La salida del multiplexor llega directamente a la entrada de datos del transmisor serie. Cuando llega el siguiente **tic** al Biestable de cambio, cambia a **0** y se selecciona el byte de menor peso 

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Ej-5-1-05.png)

El transmisor seríe sólo recibe **tics de transmisión** cuando el transmisor de 16 bits está **activado**. Una vez apgado, no se permiten más transmisiones. Esto se controla mediante una **puerta AND** conectada al biestable de estado. Se reciben dos tics de transmisión en total, que provienen de diferentes lugar. El primero es el de **inicio**, que lo provoca el biestable al encenderse. El segundo llega cuando se ha terminado de enviar el primero. Ambos se combinan a través de una **puerta OR**
  
![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Ej-5-1-06.png)

El **final** del envío lo determina el **flanco de subida** generado por el biestable de cambio. Cuando ocurre se **apaga el transmisor** poniendo a cero el **biestable de estado**, y ya no se pueden realizar más transmisiones hasta que se active

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Ej-5-1-07.png)

## Ejemplo 5-2: Bloque transmisor de 16 bits

El **transmisor de 16 bits** anterior lo metemos dentro un **bloque** para que sea más fácil su reutilización. Es el bloque **serial-tx16**, y está dispoinible en el menú **Varios/Serial/serial-tx16**. Es igual que el transmisor de 8 bits, pero con **entrada de datos de 16**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Ej-5-2-01.png)

Como segundo ejemplo de pruebas, enviaremos **dos** datos de 16 bits, según el estado de un **interruptor externo**. Usaremos valores que se corresponden con caracteres **ASCII**, para poderlos visualizar en cualquier terminal. El **montaje** es el siguiente:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Ej-5-2-02.png)

En el circuito se usa un **multiplexor 2:1** de **16 bits** para seleccionar el dato. Cuando el interruptor está a 0, se envía el dato **0x2D3E** (que se corresponde con los caracteres ->), y cuando está en 1 se envía una **"A"** y el carácter de **línea nueva** (\n)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Ej-5-2-03.png)

Lo cargamos y lo probamos. En el **terminal** obtenemos algo como estos, según vamos enviando diferentes datos:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Ej-5-2-04.png)

En este **vídeo** se puede ver el circuito en **acción**:

[![Click to see the youtube video](http://img.youtube.com/vi/_F1jUqLjo80/0.jpg)](https://www.youtube.com/watch?v=_F1jUqLjo80)

## Ejemplo 6-1: Enviando una cadena

**Generalizaremos** el ejemplo anterior para enviar **N caracteres** por el puerto serie. Los dejamos almacenados en una memoria (tabla) y usamos un **contador** para recorrerla. En este ejemplo concreto enviamos la cadena "HOLA:)\n" de 7 caracteres

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Ej6-01.png)

El **tamaño de la cadena** lo indicamos mediante el parámetro **módulo** del contador, de forma que cuando se active la **señal de overflow** (ov)  será porque hemos llegado al final, y hay que apagar el transmisor. Usamos el mismo **montaje** que el ejemplo 5-1. En el **terminal** veremos lo siguiente

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Ej6-02.png)

Cada vez que apretamos el **pulsador** aparece la cadena **HOLA:)** y el cursor salta a la **línea siguiente**. En este **vídeo** lo vemos en funcionamiento

[![Click to see the youtube video](http://img.youtube.com/vi/YWHw71KO2g4/0.jpg)](https://www.youtube.com/watch?v=YWHw71KO2g4)

## Funcionamiento del transmisor de cadenas

El funcionamiento del circuito de envío de cadenas es muy **parecido** al que envía **2 bytes**. Colocamos un **biestable RS** para describir su estado: funcionando o apagado. Al recibir el **tic de envío** se activa, y a través del **detector de flancos** de subida envía un **tic inicial** para transmitir el primer carácter

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Ej6-03.png)

La **cadena** se encuentra almacenada en una **memoria**, que en este ejemplo es de **8 bytes**, pero podría ser mayor. Usamos un **contador de 3 bits** para recorrer esta memoria. Inicialmente se accede al carácter de la **posición 0**. Al recibir un **tic** por **cnt** se **incrementa** y apunta al siguiente carácter

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Ej6-04.png)

El **tamaño de la cadena** se introduce como **parámetro módulo** del contador, de forma que cuando se alcanza su valor se emite un tic por **ov** y se sabe que se ha llegado al final. El dato que sale de la memoria se introduce por la **entrada de datos** del tranmisor serie, y se envía al recibir un **tic por txmit**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Ej6-05.png)

Tanto el **contador** como el **transmisor serie** sólo funcionan cuando el **biestable está a 1**, permitiendo el paso de los tics. Al apagarse, se bloquen, y ni se transmiten caracteres ni se incrementa el contador. Los **tics** que les llegan son el **inicial**, y el de **siguiente carácter**, a través de la **puerta OR**

El **final** del envío lo determina la **señal de overflow** del contador, que está conectada a la **entrada de reset** del **biestable**, haciendo que vuelva a cero. Esto a su vez hace que todo quede **deshabilitado** hasta que se vuelva a recibir un nuevo tic de arranque

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Ej6-06.png)

## Ejemplo 6-2: Usando el bloque serial-tx-str

El circuito anterior lo convertimos en un **bloque** y así será más fácil su uso. La **cadena máxima** que se puede enviar con este bloque es de **32 bytes** porque estamos usando un **contador de 5 bits**, y una **memoria de 32 bytes**. Este componente se encuentra en **Varios/Serial/blocks/serial-tx-str32**. Para enviar cadenas más largas sólo hay que crear el componente con un contador y memoria de mayor número de bits

Sin embargo, para que sea más fácil su uso, tenemos el componente **serial-tx-str** que es **paramétrico** (el bloque está implementado en verilog). Nos permite enviar **cadenas de cualquier longitud** (siempre que no desbordemos el tamaño máximo de memoria interna)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Ej7-06.png)

Este transmisor, a diferencia de los anteriores, **NO** tiene entrada de datos. Cuando recibe el **tic de transmisión** envía la cadena completa y emite un tic por **done** cuando ha terminado

En este circuito vemos un **ejemplo** de su uso. Se envía una cadena de **35 bytes** al apretar el pulsador. No se ha introducido nada por el parámetro baudios. En ese caso, se usan **115200** por defecto. 

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Ej6-08.png)

Lo **cargamos** y lo **probamos**. En el terminal veremos el siguiente mensaje, cada vez que apretamos el pulsador

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Ej6-09.png)

Y en este **vídeo** vemos la demo en **acción**:

[![Click to see the youtube video](http://img.youtube.com/vi/4iqM4WTTJhE/0.jpg)](https://www.youtube.com/watch?v=4iqM4WTTJhE)

## Ejemplo 6-3: Leyendo la cadena de un fichero

Las **cadenas** las estamos introduciendo como **parámetro** en la **memoria** (tabla). Cada carácter (8 bits) ocupa una posición de la memoria, empezando por 0. Se codifica en **ASCII hexadecimal**. Así, para representar el carácter **'A'** escribimos **41**, y para representar el **'1'** usamos 31. La cadena **"Hola"** la **almacenamos** así:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Ej6-10.png)

Opcionalmente podemos colocar **comentarios** usando **//**. Así, el contenido de la memoria es más legible y sabemos qué carácter está en cada posición

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Ej6-11.png)

También podemos escribir la información en **horizontal**, separando los caracteres por **espacios**. En esta disposición nos es más difícil saber la dirección en la que se almacena cada dato, sin embargo para representar cadenas no es necesario conocer estos detalles. Además podemos escribir un **comentario inicial** con la cadena

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Ej6-12.png)

Estos mismos datos también pueden estar almacenados en un **fichero de texto**, que debe estar guardado en el **mismo directorio** donde se encuentra nuestro proyecto de **icestudio**. Cuando se realiza la síntesis del circuito, icestudio lee este fichero y **rellena la memoria** con esos datos

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Ej6-13.png)

El **fichero** se introduce como **parámetro**, y debe estar entre **comillas dobles** "". Además, su extensión debe ser **.list**. En este ejemplo hemos usado el fichero **cad.list**. Con cualquier editor de texto lo creamos y editamos. Aquí lo tengo abierto con [Atom](https://atom.io/), que es **libre** y **multiplataforma**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Ej6-14.png)

Este es el **ejemplo completo** de envío de una **cadena** leída de un **fichero**. Adicionalmente se han añadido bloques con otras posibles formas de almacenar la cadena en la memoria

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Ej6-15.png)

## Ejemplo 6-4: Generación de una cadena desde un programa en python

Los **ficheros de datos** para la **memoria** se pueden generar "a mano", escribiendo en el **editor de texto**, o mediante un **programa externo**, hecho en cualquier lenguaje de programación. Este programa **genera los datos**, que luego Icestudio lee, introduce en la memoria y sintetiza el circuito final

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Ej6-16.png)

Estos datos pueden ser **cadenas de caracteres**, como en este ejemplo, **instrucciones en código máquina** si estamos haciendo un microprocesador, o cualquier otro dato (píxeles, notas...) según la aplicación

En este ejemplo estamos imprimiendo cadenas que tenemos que convertir a **ASCII hexadecimal**. Bien, pues hagamos un **programa externo** que haga el trabajo por nosotros. Una primer forma es introducir esta línea de **python** en el **intérprete**, y luego **copiamos la salida** en un fichero de datos o directamente en la **memoria** de icestudio:

```python
print(" ".join(["{:02X}".format(ord(i)) for i in "Mi cadena de texto"]))
```

En estos pantallazos se pueden ver cómo se ejecuta esta línea en el **intérprete de python** lanzado desde un terminal, tanto en **Linux** como **windows**. Se obtiene como salida los **datos ASCII hexadecimales** correspondientes la cadena "Mi cadena de texto": 4D 69 20 63 61 64 65 6E 61 20 64 65 20 74 65 78 74 6F

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Ej6-18.png)
![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Ej6-17.png)

La segunda forma es hacer un **programa completo**, pasándole como argumento la cadena, y que genere directamente el fichero **cad.list** con los datos ASCII hexadecimales. El programa lo puedes descargar de aquí: [gen_str_data.py](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/python/gen_str_data.py). Este es el **código**:

```python
#!/usr/bin/python3
import sys
from pathlib import Path

# Nombre del fichero de datos a generar
FILEDATA = "cad.list"

# Cadena por defecto
CADENA_DEFECTO = "Mensaje de prueba\n"

# Especificar descriptor del fichero
fichero = Path("./{}".format(FILEDATA))

# La cadena a generar es o bien la que se pasa como argumento o bien
# el mensaje de prueba por defecto
cadena = ""
try:
  cadena = sys.argv[1]
except IndexError:
  cadena = CADENA_DEFECTO

# Imprimir la informacion en la consola
print("Cadena: {}".format(cadena))
print("Longitud cadena: {}".format(len(cadena)))
print("Fichero: {}".format(fichero))

# Crear la cadena de datos, con los caracteres en ASCII hexadecimal
data = " ".join(["{:02X}".format(ord(i)) for i in cadena])

# Anadir al comienzo la propia cadena en comentarios
data = "\n".join(["//-- {}".format(cadena), data])

# Imprimir los datos
print(data)

# Crear fichero con los datos
fichero.write_text(data)
```
Si no sabes python no te preocupes. Basta con que te **descargues el fichero** y lo ejecutes desde el terminal. Necesita el intérprete de **python3**. Al ejecutarlo se le pasa como parámetro la cadena que queremos:

```
python3 gen_str_data.py "Hola, probando mi cadena..."
```

En estos pantallazos se muestran las **pruebas** en **Linux** y **windows**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Ej6-19.png)
![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Ej6-20.png)


Además de salir la información por pantalla, para hacer copy&paste, se genera automáticamente el fichero cad.list con la cadena. ¡Listo para que se cargue desde Icestudio!. En esta **animación** vemos el proceso, generando dos cadenas diferentes y probando su envío

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Ej6-21.gif)

**¡Importante!** No olvidar de introducir el tamaño de cada cadena generada en el parámetro size

## Funcionamiento del transmisor

Ya sabemos usar el **transmisor serie**. Es muy fácil. Pero... ¿Cómo funciona? ¿Qué magia tiene en su interior que hace que se envíen los bits?. Desde el menú **Varios/Serial/Blocks/serial-tx** tenemos acceso a los bloques que forman el transmisor. Veremos su **funcionamiento** en detalle

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/transmisor-01.png)

Para **enviar** un dato de **8 bits**, usamos una **trama de 10 bits**. El primer bit debe ser el **bit de start**, que es **0**. A continuación los **8 bits de datos**, empezando por el de menor peso (**bit 0**). Por último el **bit de stop**, que es **1**. Cuando no hay transmisión, la línea está en **reposo**, y debe estar a **1**.

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/transmisor-02.png)

La parte central del transmisor es el **registro de desplazamiento**, que pasa los datos de **paralelo a serie**. Su salida serie es la que se envía a la línea, pasando por un **biestable del sistema** para cumplir con las [reglas de diseño síncrono](https://github.com/Obijuan/open-fpga-verilog-tutorial/wiki/Cap%C3%ADtulo-22%3A-Reglas-de-dise%C3%B1o-s%C3%ADncrono). El registro es de **9 bits**, para almacenar tanto el dato como el **bit de start**. El **bit de stop** se introduce por su entrada serie, de forma que tras 9 desplazamiento está listo en la salida serie

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/transmisor-03.png)

Al **dato a transmitir** (de 8 bits) se le agrega el **bit de start** en la parte de menor peso, y se introduce por la **entrada de datos** del registro. Cuando llegua el **tic de arranque** por **load**, este dato se captura

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/transmisor-04.png)

El **estado** del transmisor lo determina un **biestable RS**. Cuando vale **0**, significa que está **apagado**. Cuando vale **1** está **funcionando**. Este estado se saca directamente por la **salida busy**. Cuando se activa la **señal txmit** para transmitir un dato, el biestable pasa de 0 a 1 y se genera el **tic de arranque**, se está conectado a la entrada load del registro, **cargando** el dato.

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/transmisor-05.png)

 El biestable también activa el **corazón de baudios**, que genera tics a la velocidad necesaria para realizar la transmisión. Estos tics se introducen por la entrada **shift** del registro, y provocan su **desplazamiento**

Los **tics** del corazón de baudios también llegan al **contador de bits**, que se **incrementa** con cada bit enviado. Cuando llega a **10**, se activa su señal de **overflow**. Significa que una trama completa se ha enviado. Como está conectada a la entrada reset del biestable, éste se apaga 

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/transmisor-06.png)

Por último, la señal de overflow, retrasada un periodo, es la que se saca por la salida **done** para indicar que **la transmisión ha terminado**

Esta es toda la **magia** que hay en un **transmisor serie** 😀

## Ejemplo 7: Midiendo las señales con el analizador Saleae

Durante el **diseño de los circuitos digitales** es muy útil **medir** las señales con un **analizador lógico**, para comprobar que se comportan como se espera, o para encontrar fallos y resolverlos. El analizador que uso es uno compatible con **Saleae**. Puedes encontrar **más información** en el [VideoBlog 26](https://github.com/Obijuan/videoblog/wiki/Cap%C3%ADtulo-26:-Probando-el-analizador-l%C3%B3gico-compatible-Saleae-con-la-FPGA) 

Mediremos **4** señales del **transmisor** serie, usando **4 canales** del analizador: **txmit**, **TX**, **busy** y **done**. Hacemos un circuito que envíe el carácter A al apretar el pulsador. Las señales a medir las sacamos por los pines **D1**, **D2**, **D3** y **D4** de la FPGA, y ahí conectaremos el analizador

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/medicion-tx-01.png)

El **montaje** es el mostrado en esta imagen. El analizador es muy pequeño, y coloca en el mismo corcho donde están el resto de componentes

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/medicion-tx-02.png)

Lanzamos el [PulseView](https://sigrok.org/wiki/PulseView), que es un programa **libre** y **multiplataforma** para realizar las mediciones con el analizador y obtenemos el comportamiento de las señales. Usamos la señal **txmit** como **disparador**: cuando llega un flanco de subida se empieza a medir

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/medicion-tx-03.png)

El **PulseView** se ha configurado para muestrear a una frecuencia de **24Mhz** y tomar **5000 muestras**. En **TX** veremos los bits que se envían. Esta señal está a 1 hasta que llega el **tic de txmit** y pasa a cero: transmisión del **bit de start**. Luego continúa con el resto de bits hasta que al final llega el **bit de stop**. En la señal inferior, llamada **UART** podemos ver mejor la **trama** serie: primero el bit de start, luego el dato y por último el bit de stop

También comprobamos cómo la señal **busy** está activa durante toda la transmisión, y se pone a **0** al terminar de enviar el **bit de stop**. Y podemos observar también, cómo al **terminar** se emite un **tic por done**. En este **vídeo** se muestra el **proceso de captura**:

[![Click to see the youtube video](http://img.youtube.com/vi/IYL2-PjHYoo/0.jpg)](https://www.youtube.com/watch?v=IYL2-PjHYoo)

# Receptor serie

Para **recibir datos** en la **FPGA** desde el **PC** usamos el **receptor serie**. El bloque de **Icestudio** está disponible en el menú **Varios/Serial/Serial-rx** de la colección **Academia-Jedi-HW-30**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/rx-01.png)

Los datos en serie llegan por el pin **RX** y salen por un **bus de 8 bits** en paralelo, listos para usarse. Cada vez que llega un dato nuevo, el receptor emite un **tic de recibido**, y la señal de busy se pone a 0. Por el **parámetro velocidad** fijamos los **baudios**. Deben ser los mismos que hemos puesto en el transmisor en el PC, o de lo contrario los datos recibidos serán "basura" 

## Ejemplo 8: Recibiendo datos del PC

Como primer **ejemplo de recepción**, leeremos todo lo que se **envía** desde el **PC a la FPGA** y lo mostraremos en **binario en los LEDs**. Los **4 bits** menos significativos se ven en **hexadecimal** en el **display de 7 segmentos**. Adicionalmente, con cada llegada del dato se emite un **pitido** y un **parpadeo en un LED**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/rx-02.png)

En el **montaje** tenemos el **display de 7 segmentos**, el **LED** de dato recibido y el **zumbador**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/rx-03.png)

Lo **cargamos** y lo **probamos**. Usamos el **ScriptComunicator** para enviar los datos. Cada vez que se aprieta una tecla, se envia a la FPGA. En la ventana del ScriptComunicator no vemos nada porque se ha deshabilitado la visualización de lo enviado. En este **vídeo** lo vemos en acción

[![Click to see the youtube video](http://img.youtube.com/vi/ITKjOOgDCwg/0.jpg)](https://www.youtube.com/watch?v=ITKjOOgDCwg)

Para poder enviar datos pulsando teclas (y no tener que dar al Enter), hay que activar la opción **send input** del ScriptCommunicator

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/rx-04.png)

Y para **no mostrar** en el terminal las teclas que pulsamos, hay que deshabilitar la opción **send** en la pestaña de **Console Options** en la configuración del scriptCommunicator (Settings)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/rx-05.png)

## Ejemplo 9: Contador de datos recibidos

En el siguiente ejemplo contaremos los **caracteres recibidos**, usando un contador **módulo 10**. Sólo cuenta de **0** a **9** y vuelve a comenzar. Con cada carácter se emite un pitido y un flash en el led. Cuando se recibe el **carácter 'r'** (minúscula) se inicializa el contador a 0

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/rx-06.png)

El **tic de dato recibido** se envía al bloque que emite el pitido y el flash, y al **contador**. Mediante un **comparador** se comprueba si el carácter recibido es **'r'**. En ese caso se activa la **señal de reset** del contador. El **montaje** es el mismo que el del ejemplo 8

En este **vídeo** se muestra el circuito en acción. Primero conectamos el **scriptcommunicator**. Cada tecla pulsada se envía por el puerto serie, y el contador se incremente. Al pulsar **r** se inicializa a 0

[![Click to see the youtube video](http://img.youtube.com/vi/N_35sE6Gyaw/0.jpg)](https://www.youtube.com/watch?v=N_35sE6Gyaw)

## Ejemplo 10: Control de un servo con dos teclas

El **puerto serie** nos permite usar el **teclado del PC** para controlador nuestros circuitos. Esto es muy útil, sobre todo en la **depuración**. Este circuito mueve el servo a una posición al pulsar la **tecla '1'**, y a otra al pulsar la **tecla '2'**. Se utiliza el **servobit**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/rx-07.png)

Un **biestable RS** almacena el **bit de posición**. Al recebirse la **tecla 1**, se emite un **tic** que pone este biestable a 1. Cuando se recibe la **tecla 2** se emite otro tic que pone el biestable a 0. El **montaje** es el mismo que el ejemplo anterior, añadiendo el servo **Futaba 3003**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/rx-08.png)

En este **vídeo** se muestra el ejemplo en funcionamiento. Sólo con las **teclas 1** y **2** cambiamos la posición del servo. No hace falta que el servo llegue a la posición final. Se puede cambiar la posición al vuelo

[![Click to see the youtube video](http://img.youtube.com/vi/JRyZmYPrUaE/0.jpg)](https://www.youtube.com/watch?v=JRyZmYPrUaE)

¡Mola mucho! :-)  Y lo más interesante, estamos controlando el servo... ¡sin software! ¡Todo por hardware!

## Ejemplo 11: Control de un servo a cualquier posición

Desde el **puerto serie** podemos envir cualquier **dato de 8 bits** a nuestros circuitos. Eso nos ahorra el tener que conectar muchos interruptores para hacer pruebas de entrada de datos. Basta con **enviar el número por el puerto serie**. Usaremos esta capacidad para **mover un servo a diferentes posiciones**

En el menú **Varios/Servos/ServoPWM-8bits**, de la colección de la **Academia-Jedi-HW-30.zip** encontramos un **controlador de servos genérico**, al que le podemos introducir por una de sus entradas la **posición**, como un número de 8 bits. 

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/rx-09.png)

En el caso de los servos **Futaba 3003** el servo se puede llevar a cualquier posición entre 60 y 225. El periodo de la **señal PWM** vale por defecto **20ms** (el de la mayoría de los servos), pero se puede poner otro valor como **parámetro**, para que funcione con cualquier servo

En este **circuito de ejemplo**, el **dato de 8 bits** que llega por el puerto serie se envía al **servo** para que vaya a esa posición. Si se envían los **comandos 'e'** (enable) o **'d'** (disable) el servo se habilita o deshabilita respectivamente. En esos casos no se escribe en el servo

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/rx-10.png)

Desde el **scriptcommunicator** podemos enviar **datos en decimal** seleccionado en el desplegable **uint8**. Se introduce el **valor en decimal** y se pincha en **send**. Desde la pestaña ASCII también podemos usar las teclas para posicionar el servo y enviar los comandos 'e' y 'd' 

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/rx-11.png)

El funcionamiento se muestra en este **vídeo**.  Primero se lleva el servo a los extremos, introduciendo los valores 60 y 220. Luego al centro con 140. Al apretar las teclas vemos también cómo cambia su posición. Al pulsar la 'd' se deshabilita, y lo movemos con la mano

[![Click to see the youtube video](http://img.youtube.com/vi/k8LCedFwbdw/0.jpg)](https://www.youtube.com/watch?v=k8LCedFwbdw)
 
##  Funcionamiento de receptor

¿Cómo funciona el receptor serie?. Desde el menú **Varios/Serial/Blocks/serial-rx** tenemos acceso a los **bloques** que forman el receptor. Veremos su **funcionamiento** en detalle

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/receiver-01.png)

Los **datos** llegan desde el **exterior**, en serie, y entran por el **pin RX**. Se pasan por el **bloque de sincronización** para evitar los problemas de **metaestabilidad**. La línea está a 1 en reposo. Lo primero que llega es siempre un 0: el **bit start**. Mediante un **detector de flancos de bajada**, activamos el **biestable de estado** del receptor cada vez que llega un dato nuevo

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/receiver-02.png)

Este biestable está a **0** cuando **NO** se reciben caracteres (apagado), y se pone a **1** (encendido) en cuanto se detecta la llegada del primero. Una vez que ha llegado el **bit de start**, el resto de flancos de bajada que hubiese no afectan. El biestable se queda encendido hasta que se active su **señal de reset**

Los bits que llegan entran por la **entrada serie** de un **registro de desplazamiento**. Al activarse el biestable de estado, se habilita el **bombeo de tics** a la velocidad de recepción serie, para desplazar el registro y almacenar los bits que llegan. Sólo hay desplazmiento mientras que el receptor está activo. Al desactivarse, la puerta AND bloquea la llegada de más tics. Las entradas de **load** y **datos** del registro de desplazamiento **NO** se usan. Por q obtenemos el **dato** y el **bit de stop**, en paralelo

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/receiver-03.png)

Cada vez que el corazón se emite un **tic de lectura**, se incrementa el **contador de bits recibidos**. Al llegar a **9** (8 bits de datos + 1 de stop) se activa su señal de overflow que inicializa el **biestable de estado**. Al ser 0, la señal de rst del contador se activa, por lo que se **reinicia a 0** y queda **listo** para recibir el siguiente dato

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/receiver-04.png)

Por último, la señal de **overflow** se usa para almacenar en **el registro de datos** los 8 bits del dato recibido, **descartando** el **bit de stop**. Esta misma señal, retrasada un ciclo, se usa para emitir el **tic de recepción** (rcv), para indicar que hay un dato disponible

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/receiver-05.png)

En este receptor básico, **no hay detección de error**. Si el bit de stop no fuese 1, habría que indicar que el dato recibido NO es correcto.

##  Midiendo el receptor

Igual que hicimos con el transmisor, vamos a **medir el receptor** para comprobar que las señales se comportan como debería, y que todo está funcionando bien. Usamos **tres canales** del **analizador lógico** compatible Saleae, uno para **Rx**, otro para **Busy** y otro para **rcv**. El **montaje** es el siguiente

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/receiver-09.png)

Hacemos un **circuito de pruebas**, con un **receptor serie** conectado a los LEDs, para ver el dato recibido, además de emitir un pitido y un parpadeo en el LED. Sacamos las señales a medir, **Rx**, **busy** y **rcv** por las salidas D1, D2 y D3 respectivamente, donde están conectados los **canales 1**,**2**, y **3** del **analizador**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/receiver-07.png)

Este es el resultado de la **medición** cuando enviamos la cadena **"HOLA"**. Observamos los tics que parecen en **rcv** al terminar la transmisión (en mitado del bit de stop), y también la **señal de Busy**. Nuestro receptor está funcionando **correctamete**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/receiver-06.png)

En esta **animación** se muestra cómo se ha tomado la captura

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/receiver-08.gif)

# Combinando transmisor y receptor

Normalmente, en nuestros circuitos integraremos tanto el **emisor** como el **receptor**. Veremos dos ejemplos de circuitos que los incluyen

## Ejemplo 13: Haciendo eco de los datos recibidos

En este circuito se vuelve a transmitir todo lo que se recibe. Esto se denomina **hacer eco**. Además de enviar cada dato de vuelta, se muestra en los **LEDs**, y se emite un **pitido** en el **zumbador** y un **parpadeo** en el **LED**. La salida de datos del receptor se conecta directamente a la entrada del transmisión, y también la señal de **rcv** a la de **txmit**. El mismo **tic de dato recibido** se usa para transmitirlo de vuelta

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/tx-rx-01.png)

Lo **cargamos** y lo **probamos**. Al escribir en el terminar escuchamos los pitidos y vemos el carácter de vuelta. También si enviamos una cadena completa

[![Click to see the youtube video](http://img.youtube.com/vi/72hspv-_Q08/0.jpg)](https://www.youtube.com/watch?v=72hspv-_Q08)

## Ejemplo 14: mini-cifrador

A partir del mismo ejemplo del eco, podemos hacer un **mini-cifrador**, que **modifica** los bits del datos recibido y lo envíe cifrado. Mediante un **interruptor externo** seleccionamos el modo: cifrado o no. El **montaje** es el siguiente:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/tx-rx-02.png)

El dato que llega del receptor, con sus bits en paralelo, se cifra **intercambiando** los **cables** de los bits. Mediante un **multiplexor** a la entrada del transmisor se selecciona el **dato cifrado** o **sin cifrar**, en función de la posición del **interruptor externo**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/tx-rx-03.png)

Lo **cargamos** y lo **probamos**. Cuando el interruptor está a 0, se hace eco sin cifrar, como en el ejemplo anterior. Al cambiar a 1, se recibe el eco cifrado. Si en modo cifrado enviamos algo ya cifrado, se descifrará

[![Click to see the youtube video](http://img.youtube.com/vi/6bjWKxjhhlY/0.jpg)](https://www.youtube.com/watch?v=6bjWKxjhhlY)

# Aplicaciones

El **puerto serie** da mucho juego. Entre otras cosas, nos permite **comunicarnos con Arduino**, comunicar nuestros circuitos a través de **bluetooth** mediante un conversor bluetooth serie o hacer **programa en el PC** que se comuniquen con ellos

## Comunicación con Arduino por Puerto serie

Otra forma de comunicarnos con **Arduino** es usando el puerto serie. En vez de enviar comandos desde el PC a la FPGA, lo haremos desde el Arduino. Utilizaremos el **puerto serie** proporcionado por la biblioteca **SoftwareSerial.h**, y dejar el **puerto estándar** para la comunicación con el **PC** y poder así depurar los programas

La **conexión** entre **Arduino** y la **FPGA** la haremos mediante 3 cables: **GND**, **TX** y **RX**. La FPGA actúa como un **Servidor**, ofreciendo servicios al Arduino, que es el **Cliente**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Arduino-fpga-01.png)

Usaremos estos **pines** para el **ejemplo**:

| Pin Arduino  |  Pin Alhambra | Descripción  |
|--------------|---------------|--------------|
|  D11         |   D11         | TX. Datos: Arduino->FPGA  |
|  D10         |   D10         | RX. Datos: FPGA->Arduino  |
|  GND         |   GND         | Masa         |


La **FPGA** ofrece **dos servicios** al **Arduino** a través del puerto serie: incremento de un **contador** y lectura de un **interruptor**. Se implementan con los **comandos 'i'** y **'r'**. Cuando el Arduino envía una 'i', la FPGA incrementa un **contador módulo 10**, que se muestra en el **display de 7 segmentos**. Cuando envía el **comando 'r'**, la FPGA devuelve el **estado del interruptor**: dígito '0' cuando si está a 0, y dígito '1' si está a 1

### Servidor hardware en la FPGA

El **montaje** es el siguiente. La FPGA está conectada al **display de 7 segmentos**, un **zumbador**, un **LED** y un **interruptor**. Cuando se recibe el **comando 'i'** se emite un pitido por el zumbador y un parpadeo en el LED. Además, la FPGA está conectada al Arduino mediante 2 cables y masa

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/arduino-fpga-02.png)

Este es el circuito que implementa el **servidor hardware**. Mediante un **comparador** y una **puerta AND** se obtiene el **tic de comando**, que aparece al llegar cada comando. El **tic del comando 'i'** incrementa el contador, genera el pitido y el parpadeo del LED. El **tic del comando 'r'** se usa para transmitir el **estado del interruptor**. El interruptor tiene sólo **1 bit**, y para enviarlo hay que rellenar hasta los 8 bits. Pero si se rellena colocando el número **3** en los **4 bits de mayor peso**, conseguimos convertirlo al dígito '0' ó '1', ya que sus códigos ASCII son 0x30 y 0x31 respectivamente

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/arduino-fpga-03.png)

### Software en el Arduino

El **Arduino** es el cliente, que solicita los **servicios** al **hardware**. Haremos un programa que incremente el contador cada **500 ms**, y que lea el **estado del interruptor** de la FPGA para **actualizar su LED** y enviar los cambios al **PC** para verlos en un terminal

En el Arduino se usan **dos puertos serie**. El implementado con la biblioteca **SoftwareSerial.h** es el que usaremos para comunicarnos con la FPGA, dejando el otro para enviar mensajes al PC y depurar el código. El **programa** es el siguiente ([serial_client.ino](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Arduino/serial_client/serial_client.ino)):

```c
#include <SoftwareSerial.h>

const int LED = 13;
const int RX = 10;
const int TX = 11;

//-- Puerto serie software
SoftwareSerial FPGA(RX, TX); 

void setup() 
{
   pinMode(LED, OUTPUT);
   FPGA.begin(115200); 
   Serial.begin(115200);
   Serial.println("Probando...");
}

void loop()
{ 
  char c;
  char old = 0;

  for(;;) {

    //-- Incrementar el Contador
    FPGA.write('i');
  
    //-- Peticion de lectura del interruptor
    FPGA.write('r');
  
    //-- Esperar la respuesta de la FPGA
    while (!FPGA.available());
    c = FPGA.read();
  
    //-- Cambiar el estado del LED en funcion de la respuesta
    //-- recibida de la FPGA
    if (c=='1') digitalWrite(13, HIGH);
    if (c=='0') digitalWrite(13, LOW);
  
    //-- Mostrar en la consola los cambios del switch
    if (c!=old) {
      Serial.print("Switch: ");
      Serial.write(c);
      Serial.println();
      old = c;
    }  
  
    //-- Esperar
    delay(500);
  }
}
```

### Probando la aplicación

Para probar la aplición cargamos primero el **hardware en la FPGA**, y luego el **software** desde el **entorno de Arduino**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/arduino-fpga-04.png)

En este **vídeo** lo vemos en acción. Primero se carga el hardware y luego el software. Al hacerlo vemos cómo el contador se empieza a incrementar, y escuchamos los pitidos. Si se aprieta el pulsador de reset del Arduino, el contador dejará de incrementarse. Luego abrimos un terminal y cambiamos de posición el interruptor. Cada vez que hay un cambio aparece un mensaje en la consola. Si nos fijamos en el LED de arduino veremos que cambia su estado según el valor de este interruptor

[![Click to see the youtube video](http://img.youtube.com/vi/kKfWSSlbSmY/0.jpg)](https://www.youtube.com/watch?v=kKfWSSlbSmY)

## Comunicando los programas del PC con los circuitos

Para comunicar el PC con los circuitos hemos usado un **terminal de comunicaciones**. Pero... ¿Y no podemos hacer **nuestros propio programas**? ¡Claro que sí! Sólo tenemos que **abrir** el puerto serie y realizar las operaciones de **lectura** y **escritura**. De esa forma, nuestro programa intercambiará datos con la FPGA

El cómo realizar la aplicación depende del **lenguaje de programación** usado. Veremos dos ejemplos en **python**: uno que se ejecuta desde la linea de comandos y otro en un **notebook de Jupyter**. Los aplicaremos al **movimiento de un servo**

### Servidor hardware

Para nuestro servidor hardware usaremos el mismo [circuito del ejemplo 11](#ejemplo-11-control-de-un-servo-a-cualquier-posici%C3%B3n), que **mueve el servo** a la **posición** indicada. Hay dos comandos especiales: la 'e' para **habilitar** y la 'd' para **deshabiliarlo**

### Software en el PC

En el ordenador tenemos que tener instalado [python3](https://www.python.org/download/releases/3.0/), [Jupyter Notebook](http://jupyter.org/), para hacer programas interactivos desde el navegador y la biblioteca [pyserial](https://github.com/pyserial/pyserial), para acceder al puerto serie

### Ejemplo 16: Secuencia de movimiento

El primer programa mueve el servo a diferentes posiciones, **automáticamente**, siguiendo una **secuencia**. Permanece durante **1 segundo** en cada posición, y pasa a la siguiente. El código **python** es:  ([servo-fpga.py](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/python/servo-fpga.py))

```python
#!/usr/bin/env python3
# -*- coding: iso-8859-15 -*-
#-- Relizar una secuencia en el servo conectado a la FPGA
#-----------------------------------------------------------------------

import time
import serial

#-- Poner el nombre del puerto serie aquí
#-- En windows será COMx
SERIAL_PORT = "/dev/ttyUSB1"

#-- Abrir el puerto serie
with serial.Serial(SERIAL_PORT, 115200) as sp:

    #-- Imprimir la información del pueto serie
    print("Puerto serie: {}".format(sp.portstr))

    #-- Habilitar el servo
    sp.write(b'e')

    #-- Mover el servo según una secuencia de posiciones
    pos = [60, 94, 128, 162 ,225, 128]

    for p in pos:
        sp.write(bytes([p])) #-- Enviar la posicion actual a la FPGA
        time.sleep(1)

    #-- Deshabilitar el servo y terminar
    sp.write(b'd');
```

Este programa es **multiplataforma**. Yo lo estoy probando en **Ubuntu Linux**, pero funciona también en **Mac** y **windows**. Sólo hay que **modificar el nombre del puerto serie**. En este **vídeo** se muestra el programa en **acción**. Lo ejecutamos así:

```
python3 servo-fpga.py
``` 

[![Click to see the youtube video](http://img.youtube.com/vi/3xqJ8v76_xo/0.jpg)](https://www.youtube.com/watch?v=3xqJ8v76_xo)

El programa **abre** el puerto serie, a la velocidad de **115200 baudios** y crea el objeto **sp**, con el que accederemos a él. Primero habilita el servo, enviando el comando 'e'. Esto se hace llamando al método **write** de sp. En **python3** indicamos que un  carácter es de tipo **byte** colocando una **b** delante, y luego el carácter. Así, **b'e'**, representa el **carácter ASCII e**, cuyo valor es 0x65

En pos colocamos las posiciones a las que queremos que se mueva el servo en la secuencia. Para los servos **Futaba 3003**, estas posiciones están comprendidas entre **60** y **225**. El bucle principal accede a todas las posiciones de la lista, y las envía la FPGA. Es necesario convertirlas al tipo **byte** usando la expresión **bytes([p])**, y luego se transmiten con write.

Por último se **deshabilita** el servo enviando el **comando 'd'** 

### Ejemplo 17: Control interactivo del servo

Usaremos un **cuaderno de python** en **Jupyter** para mover el servo de manera **interactiva** desde el navegador. Lazamos **Jupyter** y abrimos el cuaderno [servo-fpga.ipynb](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/python/servo-fpga.ipynb)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/jupyter-fpga-01.gif)

Una vez abierto, este es el aspecto que tendrá la página en el navegador

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/jupyter-fpga-03.png)

Conectamos la FPGA, nos aseguramos que en el código hemos puesto el **nombre correcto** del puerto serie y **ejecutamos** el cuaderno, desde la opción **Cell/Run All**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/jupyter-fpga-02.gif)

En la **última celda** tenemos una **barra de desplazamiento** horizontal que es la que nos permite mover el servo, y habilitarlo o deshabilitarlo con la **casilla de verificación**

(Vídeo del notebook en acción)

(TODO)

## Comunicación bluetooth-serie

  * EJemplo del eco desde el movil  (terminal android)
  * Posicionamiento del servo en diferentes posiciones según las pulsaciones (aplicación que no es terminal)


(TODO)

* [Más info. Tutorial verilog](https://github.com/Obijuan/open-fpga-verilog-tutorial/wiki/Cap%C3%ADtulo-20%3A-Comunicaciones-serie-as%C3%ADncronas)

# Ejercicios propuestos (25 BitPoints)

Ver los detalles de los ejercicios y las **entregas** en el menú **Archivos/Ejemplos/2-Ejercicios** de la colección de este tutorial

**Resumen**:

* **Ejercicio 30.1** (Total **x Bitpoints**): 

* **Ejercicio 30.2** (Total **x Bitpoints**): 

* **Ejercicio 30.3** (Total **x Bitpoints**): 

* **Ejercicio 30.4** (**5 Bitpoints**). Ejercicio Libre. Premiar la creatividad. **Entregar** por redes sociales o github: Pantallazos, enlaces, vídeos, etc...

# Ejercicios entregados

## Primero

### Ejercicio 30.1
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 30.2
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 30.3
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 30.4
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()


## Segundo

### Ejercicio 30.1
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 30.2
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 30.3
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 30.4
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

## Tercero

### Ejercicio 30.1
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 30.2
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 30.3
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 30.4
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()


# Autor

* [Juan González-Gómez](https://github.com/Obijuan) (Obijuan)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/logos-urjc-gsyc-peloto-jderobot.png)

# Licencia

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/attribution-share-alike-creative-commons-license.png)

# Créditos y agradecimientos

# Enlaces

* [Repositorio con las colecciones de la Academia Jedi de Hardware](https://github.com/Obijuan/Academia-Jedi-Hw)
* [BricoGeek](http://tienda.bricogeek.com/). Tienda Friki donde comprar componentes electrónicos
* [Repositorio de la Icezum Alhambra](https://github.com/FPGAwars/icezum/wiki)
* Documentación de la Icezum Alhambra:  ([PNG](https://github.com/FPGAwars/icezum/raw/master/doc/pinout/icezum-pinout.png))([SVG](https://github.com/FPGAwars/icezum/raw/master/doc/pinout/Icezum-alhambra-pinout.svg))([PDF](https://github.com/FPGAwars/icezum/raw/master/doc/pinout/icezum-pinout.pdf)) 
* [Icestudio](https://github.com/FPGAwars/icestudio)
* [Monedas Bit imprimibles](https://github.com/Obijuan/3D-parts/wiki/Monedas-Bit)
* [Printbot Beetle](https://github.com/bq/printbots/tree/master/Beetle)
* [Ultimate Gripper](https://github.com/bqlabs/mechatronics/tree/master/grippers/ultimate_gripper)
* [Pinza paralela](http://www.iearobotics.com/wiki/index.php?title=Freecad:_Pinza_mecanica)
* [Robot Educativo Zowi](https://github.com/JavierIH/zowi)
* [Qué es PWM y para qué sirve](https://www.rinconingenieril.es/que-es-pwm-y-para-que-sirve/). Entrada en el bloq de **Rincón Ingenieril**
* [Repositorio de PCBPrints](https://github.com/PCBPrints/PCbPrints)
* [PCBPrint Alhambra-Button](https://github.com/PCBPrints/Alhambra-button/wiki)
* [PCBPrint Alhambra Switch](https://github.com/PCBPrints/Alhambra-switch/wiki)
* [Soporte Icezum Alhambra](https://github.com/FPGAwars/Icezum-Alhambra-3D-support/wiki)
* [Soporte para Servo Futaba 3003](https://github.com/Obijuan/3D-parts/wiki/Soporte-para-servo-Futaba-3003)
* [Puntero para servo Futaba 3003](https://github.com/Obijuan/3D-parts/wiki/Puntero-para-Servo-Futaba-3003)
* [Clavijas de amarre para servos](https://github.com/Obijuan/3D-parts/wiki/Servo-pins-para-Futaba-3003)
* [Tablero indicador binario para servo](https://github.com/Obijuan/3D-parts/wiki/Tablero-indicador-binario-para-Servo)
* [Fijador de esquinas](https://github.com/Obijuan/3D-parts/wiki/Fijador-de-esquinas)
* [Fijador de cables](https://github.com/Obijuan/3D-parts/wiki/Fijador-de-cables-con-chinchetas)
* [Fijador de placas](https://github.com/Obijuan/3D-parts/wiki/Fijador-de-placas)
* [Octopus passive buzzer](http://www.elecfreaks.com/estore/octopus-passive-buzzer-brick-obpb01.html), de Elecfreak
* [Kit de sensores para Arduino](http://tienda.bricogeek.com/kits-arduino/832-kit-de-37-sensores-compatible-arduino-1247563871496.html). BricoGeek. Dentro del kit con 37 módulos, hay uno con zumbador
* [Repositorio de iconos SVG para Icestudio](https://github.com/FPGAwars/icestudio-block-icons/wiki)

# Preguntas frecuentes

* **¿Dónde puedo conseguir la placa Icezum Alhambra?**

Pueden conseguir una desde [Alhambrabits](https://alhambrabits.com/buy/)

* **¿Dónde puedo comprar material electrónico?**. Hay muchos sitios. Uno muy bueno es [Bricogeek](http://tienda.bricogeek.com/)

* **¿Cómo aprendo a manejar github?**

Hay mucha información en internet. En su momento hice este Tutorial: [Github y FreeCAD](http://www.iearobotics.com/wiki/index.php?title=Tutorial:_Github_y_Freecad) para enseñar a manejarlo. Los ejemplos están hechos con ficheros de FreeCAD, sin embargo, lo que se enseña es genérico. También vale para las entregas de los ejercicios del tutorial de Electrónica digital para makers

* **Los pulsadores de la Icezum Alhambra no me funcionan**

Eso es debido a que se han metido restos de flux y no hacen buen contacto. En el apartado [¡No me funcionan los pulsadores!](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-9:-Pulsadores-y-entradas#no-me-funcionan-los-pulsadores) del Tutorial 9 se indica cómo solucionarlo fácilmente

* **¿Dónde puedo encontrar más información sobre las señales PWM?**

Echa un vistazo a [este post de Rincón Ingenieril](https://www.rinconingenieril.es/que-es-pwm-y-para-que-sirve/) sobre el tema

* **He conectado un pulsador externo pero no me funciona. He hecho un circuito para conectar el botón con un led, y al apretar se enciende el LED, pero luego no se apaga. NO funciona bien**

Los pulsadores externos que se conecten a los pines de 5v de la Alhambra (D0 - D13) tiene que llevar una resistencia de pull-up o pull-down con valores entre 460 ohm y 2K. Típicamente usamos 1K. Esto hace que los conversores de nivel se configuren como entradas y que el pulsador funcione correctamente. Puedes encontrar más información [En este enlace](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-12:-Interruptores-y-pulsadores-externos#conexi%C3%B3n-a-pines-de-5v)

* **¿Donde puedo conseguir el switch que habéis usado en la PCBprint [Alhambra switch](https://github.com/PCBPrints/Alhambra-switch/wiki)?**
Es el mismo switch que se ha usado en la propio Icezum Alhambra (aunque la versión sin acodar). Los fabricantes los puedes encontrar en la [lista de componentes de la propia icezum Alhambra](https://github.com/FPGAwars/icezum/blob/master/doc/BOM/icezum-bom.pdf). La referencia del componente en concreto es esta: [Slide Switch, SPDT, On-On, Through Hole, WS-SLTV Series, 500 mA](http://uk.farnell.com/wurth-elektronik/450301014042/switch-slide-mini-on-on/dp/2134452).  Yo te recomiendo que uses la [PCBprint de Diego Lale](https://github.com/PCBPrints/PCbPrints/tree/master/PCBPrint_common_switch), que usa interruptores que puedes conseguir en Bricogeek: [Mini-interruptor de 3 pines](http://tienda.bricogeek.com/interruptores/912-mini-interruptor-para-prototipado.html?vt_product=912&from=UpSell&utm_campaign=Upsell+recommendation+for+prod&vt_campaign=1003027&utm_content=tpl&utm_source=merchandising&utm_medium=email&vt_content=10003986&vt_user=1000002746135894)

* **¿Dónde puedo conseguir el servo de rotación continua SM-4303R**?

Es un servo muy usado y muy estándar. Si buscar por internet encontrarás muchos sitios donde los vendes, a diferentes precios. Aquí en España se puede conseguir muy fácilmente a través de BricoGeek: [Servo SM-4303R Bricogeek](http://tienda.bricogeek.com/motores/118-servomotor-de-rotacion-continua-sm-s4303r.html) y también en Iberobotics: [Servo SM-4303R Iberobotics](https://www.iberobotics.com/producto/servo-rotacion-continua-springrc-sm-s4303r/)

* **Parece ser que los servos Futaba 3003 se pueden trucar para convertirlos en rotación continua. ¿Conoces algún tutorial sobre como hacerlo?**

El Futaba 3003 es uno de los servos que típicamente se han trucado para construir robots móviles con ellos. Robots como [Tritt](http://www.iearobotics.com/proyectos/tritt/tritt.html), [El Skybot](http://www.iearobotics.com/wiki/index.php?title=Skybot) o el [Miniskybot](http://www.iearobotics.com/wiki/index.php?title=Mini-Skybot) los utilizan. Existen muchísimos tutoriales para hacerlo. En esta página puedes encontrar [todas las formas de trucarlos](https://www.diarioelectronicohoy.com/blog/trucar-un-servo-futaba-s3003). El que recomendamos es el caso 2

* **Ya tengo varios PCBprints impresos (de los LEDs y los pulsadores. ¿Dónde podría conseguir los cables que usas para conectarlos directamente a la Icezum Alhambra?**

  Son cables hembra-hembra de tres hilos. Como son los mismos que se usan para la conexión de servos, los puedes encontrar en tiendas donde vendan cualquier tipo de servo. Por ejemplo:  
  * En **Pololu**:  https://www.pololu.com/product/779
  * En **hobby king**: https://hobbyking.com/en_us/10cm-female-to-female-servo-lead-jr-26awg-10pcs-set.html?___store=en_us  

  También se pueden usar cables hembra-hembra aislados. A partir de ellos es muy fácil trenzarlos y hacerte tu propio cable de 3 pines:

  * **Adafruit**:  https://www.adafruit.com/product/266
  * En **Bricogeek**: http://tienda.bricogeek.com/cables/585-set-de-cables-h-h-10-unid.html 
  * En **Iberobotics**: Aquí también tienen los hembra-hembra: https://www.iberobotics.com/comprar/electronica-componentes/cables-y-conectores/ Es otra tienda española que está en Santander



