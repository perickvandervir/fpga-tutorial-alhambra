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
      * [Windows 10](#windows-10)  (TODO)
    * [Instalación del ScriptCommunicator](#instalaci%C3%B3n-del-scriptcommunicator)
      * [ScriptCommunicator en Gnu/Linux Ubuntu 18.04](#scriptcommunicator-en-gnulinux-ubuntu-1804)
      * [ScriptCommunicator en Windows 10](#scriptcommunicator-en-windows-10) (TODO)
   * [Primera prueba](#primera-prueba)
     * [Ejemplo 1: Comprobación de las señales a nivel físico](#ejemplo-1-comprobaci%C3%B3n-de-se%C3%B1ales-a-nivel-f%C3%ADsico)
     * [Probando las señales de control con el ScriptCommunicator](#probando-las-se%C3%B1ales-de-control-con-el-scriptcommunicator)
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

(TODO)

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

(TODO)

## Primera prueba

Haremos una primera prueba para comprobar que está todo funcionando. Esta prueba la haremos a **nivel físico**: no usaremos ningún circuito transmisor ni receptor todavía. Simplemente **uniremos cables** y mostraremos en los **LEDs** las **señales de control**

### Ejemplo 1: Comprobación de señales a nivel físico

Cargamos este circuito en la FPGA. El cable **RX**, por donde llegan los datos, está unido directamente al de **TX**, por donde se envían. Así, todo lo que llega se devuelve, sin ningún tipo de procesado. Las señales de control **DTR** y **RTS** están conectadas a los **LEDs 7** y **0** respectivamente. Y los **pulsadores** a las señales **CTS**, **DCD** y **DSR**, a través de un **decodificador** de 2 a 4

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Ej1-01.png)

Probaremos su funcionamiento primero con el **Arudino IDE**. Lo lanzamos y seleccionamos el puerto serie desde **Tools/Port**. Esto depende del **sistema operativo** que usemos:
* **Linux**: Dispositivo **/dev/ttyUSB1** (Aparecerá también el /dev/ttyUSB0, pero NO es el correcto)
* **Windows**: XXXX
* **MAC**: XXXX

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Ej1-02.png)

Abrimos el **terminal serie** y hacemos una prueba de envío de varias cadenas. Veremos cómo recibimos las mismas (el eco). Es indiferente la velocidad a la que esté configurado el terminal

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Ej1-03.gif)

Veremos cómo los **LEDs** de **TX** y **RX** de la Icezum Alhambra se encienden. Se corresponden con las señales TX y RX del PC, y nos indican que hay **datos** que se están **intercambiando** con el **PC**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-30/Ej1-04.png)

Desde el entorno de Arduino **NO** tenemos acceso a las señales de control, por lo que para la siguiente prueba usaremos el **ScriptCommunicator**

### Probando las señales de control con el ScriptCommunicator

(TODO)

## Trabajando a nivel físico

* Otro ejemplo: habilitar/deshabilitar conexión con un pulsador 
(TODO)
sudo usermod -a -G dialout $USER

 TODO

## Transmisor Serie

 TODO

## Ejemplos
* Envío de un carácter ascii
* Envío de un número pelado
* Circuito BCD a Ascii
* Envío de una cadena
* Envío de varias cadenas

## Receptor serie

* Encender apagar un led con cualquier dato recibido
* encendido de leds con las teclas  

(TODO)

* [Más info. Tutorial verilog](https://github.com/Obijuan/open-fpga-verilog-tutorial/wiki/Cap%C3%ADtulo-20%3A-Comunicaciones-serie-as%C3%ADncronas)
* Dispositivos: pc, arduino, bluetooh-serie, usb-serie,


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



