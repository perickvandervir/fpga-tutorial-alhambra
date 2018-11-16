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

  
(Descripción detallada del funcionamiento)  

(Hacer bloque serial-tx-16) 

(Ejemplo 5-2: Seleccionar para enviar 2 datos de 16 bits. Uno es A + \n. El otro uno hexadecimal cualquiera) 

TODO

## Ejemplo 6: Enviando una cadena

TODO

(Información en fichero?)

## Funcionamiento del transmisor

(TODO)

# Receptor serie

* Encender apagar un led con cualquier dato recibido
* encendido de leds con las teclas  

(TODO)

# Aplicaciones

(Bluetooth-serie)
(Conexión Arduino)
(Comunicándonos con nuestros programas: Python, node)

(TODO)

* Otro ejemplo: habilitar/deshabilitar conexión con un pulsador  
* sudo usermod -a -G dialout $USER
* [Más info. Tutorial verilog](https://github.com/Obijuan/open-fpga-verilog-tutorial/wiki/Cap%C3%ADtulo-20%3A-Comunicaciones-serie-as%C3%ADncronas)
* Dispositivos: pc, arduino, bluetooh-serie, usb-serie,

# Info



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



