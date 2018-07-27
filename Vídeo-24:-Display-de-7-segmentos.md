![]()

(En construcción...)

# Vídeo

(En construcción...)

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

Haz click en la imagen para ver el **vídeo en Youtube**

# Descripción

(TODO)

# Colección

**Academia-Jedi-HW-24.zip**: Colección para este tutorial. Descargar e instalar 

# Contenido

* [Introducción](#introducci%C3%B3n)
* [Dibujando con LEDs](#dibujando-con-leds)
  * [La sonrisa de Franky](#la-sorisa-de-franky)
  * [Ejemplo 1: Franky sonríe al apretar el pulsador](#ejemplo-1-franky-sonr%C3%ADe-al-apretar-el-pulsador)
  * [Visualizando los dígitos 0 y 1](#visualizando-los-d%C3%ADgitos-0-y-1)
  * [Ejemplo 2: Mostrando los dígitos 0 y 1 con el pulsador](#ejemplo-2-mostrando-los-d%C3%ADgitos-0-y-1-con-el-pulsador)
* [Display de 7 segmentos](#displays-de-7-segmentos)
  * [Segmentos](#segmentos)
  * [Nomenclatura](#nomenclatura)
  * [Patillaje](#patillaje)
* [Conexión a la placa Icezum Alhambra](#conexi%C3%B3n-a-la-placa-icezum-alhambra)
  * [Display en protoboard](#display-en-protoboard)
  * [Display en placa soldada](#display-en-placa-soldada)
  * [Ejemplo 3: Encendiendo segmentos aislados](#ejemplo-3-encendiendo-segmentos-aislados)
  * [Ejemplo 4: Encendiendo todos los segmentos y el punto](#ejemplo-4-encendiendo-todos-los-segmentos-y-el-punto)
  * [Ejemplo 5: Lamp-test con bus](#ejemplo-5-lamp-test-con-bus)
* Ejercicios propuestos (X Bitpoints)
* [Ejercicios entregados](#ejercicios-entregados)
* [Autor](#autor)
* [Licencia](#licencia)
* [Enlaces](#enlaces)
* [Preguntas frecuentes](#preguntas-frecuentes)

# Introducción

Hasta ahora, los circuitos se han **comunicado** con nosotros en **binario**. La forma más simple ha sido **encender LEDs**. Cuando se enciende, significa que el bit está a **1**, y cuando se apaga, que está a **0**

El **circuito más sencillo** que nos permite **observar un bit** es el que ya conocemos, el hola mundo:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/Intro-02.png)

Mirando el **LED0** sabemos que si está **encendido**, es que este bit está a **1**, y si está **apagado** vale **0**. Es una forma de comunicación **muy básica**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/Intro-01.png)

Mediante los **buses** pasamos de **uno** a **varios bits**. Y esto nos permite visualizar **números en binarios en los LEDs**. Desde nuestro circuito **enviamos un número**, por ejemplo el **6**, de esta forma

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/Intro-03.png)

Y lo veremos en **binario** en los **LEDs**.  Este número **6** en binario (de 8 bits) es **00000110**, por lo que habrá 6 LEDs apagados y **dos encendidos**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/Intro-04.png)

Con este sistema logramos que **nuestros circuitos** nos muestren **cualquier número**. Sin embargo, los humanos no estamos acostumbrados al binario. En vez de ver una serie de LEDs encendidos y apagados, preferiríamos ver el **dígito 6**, en decimal. ¿Cómo podemos lograr esto?

# Dibujando con LEDs

**Encender** y **apagar LEDs** desde nuestros circuitos no tiene ningún misterio. Lo sabemos hacer desde el [tutorial 2](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-2:-%C2%A1Poniendo-en-marcha-Icestudio!). ¿Y si usamos los LEDs para hacer **dibujos con luz** controlada por nosotros? Bueno, esto es algo que en realidad ya hemos hecho. En el [tutorial 8](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos) usamos 2 LEDs para representar los [ojos de Franky](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos#circuitos-sobre-cart%C3%B3n--papel)

![](https://raw.githubusercontent.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/master/wiki/Tutorial-08/Franky-anim.gif)

Es una representación de los ojos muy sencilla. Cada **LED** actúa como un [Píxel](https://es.wikipedia.org/wiki/P%C3%ADxel). Podemos usar más LEDs para representar otras cosas, con más resolución. **Iluminando** ciertos LEDs y **apagando** otros, conseguimos representar **dibujos con luz**

## La sorisa de Franky

Hagámosle una **boca** a Franky, para que pueda **sonreir** o mostrar **indiferencia**. Mis dotes artísticas son muy malas, así que me temo que mi boca será muy cutre, pero espero que sirva de **inspiración** para los que tenéis un sentido artístico más desarrollado 😀

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/franky-01.png)

Nos fijamos en la **boca**. Está creada mediante **6 LEDs**, cuatro en una fila horizontal y otros dos debado. Si sólo **encendemos** los **cuatro LEDs de la parte superior**, nos aparecerá la boca con **forma horizontal**. Si por el contrario encendemos los **dos de abajo** y los de **los extremos superiores**, obtenemos una boca con forma de **sonrisa**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/franky-02.png)

Ya sabemos cómo hacer un circuito de este tipo. Usaremos un **circuito combinacional** definido mediante su **tabla de verdad**. Como la boca puede estar en dos estados, usaremos **un único bit de entrada**, y asignaremos **0** a la **boca horizontal** y **1** a la **sonrisa**. Como necesitamos controlar **6 LEDs**, el circuito tendrá **6 bits de salida**. Esta es la **estructura** del circuito en Icestudio

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/franky-03.png)

Sólo nos falta **rellenar la tabla** con los valores correctos para que se **enciendan** los LEDs adecuados en cada caso. Simplemente tenemos que  darles un nombres y decidir a qué pin de la FPGA lo vamos a conectar. Usaremos los **pines GP** de la Icezum Alhambra (3.3v) que son que ya habíamos usado para los ojos de franky

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/franky-04.png)

**Nombramos** a los LEDs con las letras **a**, **b**, **c**, **d**, **e** y **f**. Tomaremos la **a** como el **bit de mayor peso**, conectándolo a **GP5**, y **f** el de **menor**, conectado a **GP0**. Con estos datos ya podemos determinar los **valores de las salidas**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/franky-05.png)

Y la **tabla de verdad** es la siguiente

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/franky-06.png)

Con ello ya tenemos el **circuito definitivo**. Sólo hay que rellenar la tabla con los valores **3C** y **27**

## Ejemplo 1: Franky sonríe al apretar el pulsador

Este es el circuito que hace que **Franky sonría** cuando se aprieta el **pulsador**. Además los dos ojos se mantienen encendidos

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/franky-07.png)

Y este es el montaje. Se ha colocado un **pulsador externo**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/franky-08.jpg)

**Cargamos** el circuito y lo **probamos**. ¡Hola Franky II!

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/franky-09.gif)

## Visualizando los dígitos 0 y 1

Ya hemos aprendido cómo hacer "dibujos" sencillos con los **LEDs**. Esta técnica nos vale también para **mostrar dígitos** y mejorar así la comunicación con el usuario. En vez de dibujar sonrisas, usamos los LEDs para **dibujar dígitos**. Como ejemplo, dibujaremos los dígitos **0** y **1**, usando **8 LEDs**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/digitos01-1.png)

El procecedimiento ya lo conocemos. Es igual que en el anterior ejemplo. Damos **nombres a los LEDs** y elegimos a qué **pin de la FPGA** conectarlo. Usaremos las letras **a**, **b** ,**c**, **d**, **e**, **f**, **g** y **h** y los conectaremos a los pines **GP7** - **GP0** respectivamente

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/digitos01-2.png)

**Calculamos** el valor **binario** de los LEDs para cada uno de los **dos dígitos** 

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/digitos01-3.png)

Y sacamos la **tabla de verdad**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/digitos01-4.png)

## Ejemplo 2: Mostrando los dígitos 0 y 1 con el pulsador

Como ejemplo haremos un circuito que muestre el **dígito 0** cuando el **pulsador** externo **NO** está **apretado**, y el **dígito 1** cuando **esté pulsado**. Necesitamos un **circuito combinacional** con **una entrada** (el pulsador) y **8 bits de salida** (para los valores de los LEDs)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/digitos01-5.png)

El **montaje** es el siguiente

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/digitos01-6.png)

**Cargamos** el circuito y lo **probamos**. En esta **animación** se muestra el resultado

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/digitos01-7.gif)

# Displays de 7 segmentos

Afortunadamente ya existe un componente que tiene los **LEDs integrados** y nos permite **dibujar** los **dígitos decimales**, del 0 al 9, fácilmente: es el [display de 7 segmentos](https://es.wikipedia.org/wiki/Visualizador_de_siete_segmentos)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/display-01.jpg)

Se inventaron en la **década de los 60s** para mostrar números en las primeras calculadoras electrónicas. Con ellos "dibujamos" los dígitos del **0** al **9**, usando luz, igual que hemos hecho en el [ejemplo 2](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-24:-Display-de-7-segmentos#ejemplo-2-mostrando-los-d%C3%ADgitos-0-y-1-con-el-pulsador)

Aunque actualmente tenemos modos más sofisticados de mostrar la información, los **displays de 7 segmentos** se siguen **usando muchísimo** en aparatos electrónicos, como electrodomésticos, despertadores, etc.

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/display-02.jpg)

Pero sin duda, una de las aplicaciones más **épicas** de los 7-segmentos es en la **interfaz** de la [computadora de guiado del Apolo 11](https://es.wikipedia.org/wiki/Apollo_Guidance_Computer), la nave que llevó al **primer hombre que pisó la Luna**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/display-03.jpg)

## Segmentos

Los **displays de 7 segmentos** están compuestos por **8 LEDs independientes**, 7 de ellos tienen una forma **alargada** para representar las **líneas de los dígitos**, y uno para representar el **punto**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/display-04.png)

Según los **segmentos** que se **enciendan**, se representa un dígito u otro

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/display-05.png)

Pero al tratarse de **segmentos individuales** podemos representar otras cosas, aunque no sean los dígitos del 0 al 9, como por ejemplo la letra H, E... En total hay un total de 128 combinaciones (2 elevado a 7)

## Nomenclatura

Para dibujar los dígitos necesitamos **nombrar** los diferentes **segmentos**, igual que hemos hecho en los ejemplos anteriores. La nomenclatura estándar es usar las letras **a**, **b**, **c**, **d**, **e**, **f** y **g** para los segmentos. El **punto** lo llamaremos **p**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/display-06.png)

## Patillaje

Los displays de 7 segmentos vienen en un encapsulado con **10 patas**, 5 en la parte **superior** y 5 en la **inferior**. En los ejemplos que visto hasta ahora, hemos trabajado con **lógica positiva**: si enviamos un **1** el segmento se **enciende**, y si enviamos un **0** se **apaga**. Los displays que funcionan de esta manera se denominan de **cátodo común**. Pero también existen los de **lógica negativa**: con un 0 se encienden y con un 1 se apagan. Se denominan de **ánodo común**. 

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/display-07.png)

Los patillajes son iguales para ambos tipos de displays, con la diferencia de que en unos las patas del medio se conectan a **GND** (cátodo común) y en otros a **VCC** (ánodo común)

# Conexión a la placa Icezum Alhambra

Conectaremos un **display de 7 segmentos** de **cátodo común** (lógica positiva) a la **icezum Alhambra** a través de los pines de 3.3v: **GP7 - GP0**. Utilizaremos una **resistencia de 100ohm**. El **segmento a** está conectado al bit de **mayor peso** (GP7) y el **segmento g** al de **menor** (GP0)

Como cada **segmento** es un **LED independiente**, el **esquema de conexión** es exactamente el mismo que usamos en el [tutorial 8](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos) para conectar **LEDs externos** a los pines de **3.3v** de la **Icezum Alhambra**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/conexion-01.png)

El **esquema completo** es el siguiente

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/conexion-02.png)

## Display en protoboard

Una forma de poner el display 7 segmentos en funcionamiento es utilizando una **placa entrenadora** y realizar las **siguientes conexiones**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/conexion-03.png)

Esta es una opción muy útil para hacer pruebas rápidas y aprender a manejar el display. El **montaje real** es el siguiente:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/conexion-04.jpg)

## Display en placa soldada

La otra forma es **soldar el circuito** en una placa. Esta es una opción mejor para nuestros proyectos, ya que todo es más **sólido** y es mucho más **fácil** hacer demostraciones

En la parte superior se ha colocado un **conector** con **pines machos** acodados, dividido en dos. En la izquierda están los **7 pines** para controlar los **segmentos**, colocados en el orden **abcdefg**. En la derecha hay **dos pines**, uno para el **punto** y el otro para **GND**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/conexion-05.png)

Esta es la placa conectada a la **Icezum Alhambra**, con **todos los segmentos encendidos** para comprobarlos

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/conexion-06.jpg)

## Ejemplo 3: Encendiendo segmentos aislados

Los displays de 7 segmentos en realidad son **LEDs independientes**, con forma de **segmento** y **punto**. Como primer ejemplo vamos a encendere dos segmentos, el **a** (superior) y el **d** (inferior). Simplemente sacamos un **bit a 1** por los pines **GP6** y **GP3**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/conexion-07.png)

Lo **cargamos** y lo **probamos**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/conexion-08.jpg)

Se deja como **ejercicio** el encender los diferentes segmentos para probarlos. ¿Qué segmentos hay que encender para representar el dígito 1?

## Ejemplo 4: Encendiendo todos los segmentos y el punto

En el siguiente ejemplo haremos lo que se conoce como **prueba de lámpara** (*lamp test*) que consiste en **encender todos los LEDs** para verificar que están operativos. Se usa mucho para comprobar si un montaje está bien conectado

**Encenderemos individualmente** todos los segmentos, y el punto, conectándolos a **bits a 1** (como en el ejemplo anterior)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/conexion-09.png)

Lo **cargamos** y lo **probamos**. ¡*Lamp test* pasado! :-)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/conexion-10.jpg)

## Ejemplo 5: Lamp-test con bus

Para activar los segmentos, es más cómodo utilizar un **bus de 7 bits** y enviar directamente el **número** que hace que se enciendan los segmentos. Para encenderlos todos, basta con enviar el número binario 1111111, que es el 7F en hexadecimal, o el 127 en decimal. El **punto** se controla mediante **1 bit**, colocando el valor del bit en su parámetro

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/conexion-11.png)

Ahora es **muy fácil** introducir valores en el **parámetro** de los 7 segmentos para mostrar **diferentes dígitos**

# Mostrando dígitos en el display

(TODO)

# Ejercicios propuestos (X BitPoints)

Ver los detalles de los ejercicios y las **entregas** en el menú **Archivos/Ejemplos/2-Ejercicios** de la colección de este tutorial

**Resumen**:

* **Ejercicio 24.1** (Total **x Bitpoints**): 

* **Ejercicio 24.2** (Total **x Bitpoints**): 

* **Ejercicio 24.3** (Total **x Bitpoints**): 

* **Ejercicio 24.4** (**5 Bitpoints**). Ejercicio Libre. Premiar la creatividad. **Entregar** por redes sociales o github: Pantallazos, enlaces, vídeos, etc...

# Ejercicios entregados

## Primero

### Ejercicio 24.1
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 24.2
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 24.3
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 24.4
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()


## Segundo

### Ejercicio 24.1
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 24.2
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 24.3
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 24.4
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

## Tercero

### Ejercicio 24.1
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 24.2
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 24.3
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 24.4
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()


# Autor

* [Juan González-Gómez](https://github.com/Obijuan) (Obijuan)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/logos-urjc-gsyc-peloto-jderobot.png)

# Licencia

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/attribution-share-alike-creative-commons-license.png)

# Créditos y agradecimientos

* Foto del display de 7 segmentos. CC BY-SA 3.0, https://commons.wikimedia.org/w/index.php?curid=2550283
* Foto del microondas. De Consumer Reports, CC BY-SA 4.0, https://commons.wikimedia.org/w/index.php?curid=48764116

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



