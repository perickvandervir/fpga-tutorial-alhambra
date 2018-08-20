![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/Portada/Tut-24-portada.png)

# Vídeo

[![Click to see the youtube video](http://img.youtube.com/vi/vbnDTiyDLg0/0.jpg)](https://www.youtube.com/watch?v=vbnDTiyDLg0&list=PLmnz0JqIMEzXaeYVzf2TfTzRekPIVoljw&index=24)

Haz click en la imagen para ver el **vídeo en Youtube**

# Descripción

Los **displays de 7 segmentos** permiten que nuestros circuitos, que internamente trabajan en binario, muestren información en **dígitos decimales**, que son legibles por los humanos. Para manejarlos simplemente hay que saber **encender LEDs** y saber hacer **circuitos combinacionales** a partir de **tablas de verdad**

# ¡Icestudio 0.3.3!

Este tutorial está hecho con la versión [0.3.3-rc de Icestudio](https://github.com/FPGAwars/icestudio/releases/tag/v0.3.3-rc). Asegúrate de tener instalada esta versión (o superior)

# Colección

[Academia-Jedi-HW-24.zip](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/Collections/Academia-Jedi-HW-24.zip): Colección para este tutorial. Descargar e instalar 

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
* [Mostrando dígitos en el display](#mostrando-d%C3%ADgitos-en-el-display)
  * [Ejemplo 6: Dígito 0](#ejemplo-6-d%C3%ADgito-0)
    * [Ejemplo 7: Dígito 0 desde constante en bloque](#ejemplo-7-d%C3%ADgito-0-desde-constante-en-bloque)
  * [Dígitos decimales 0-9](#d%C3%ADgitos-decimales-0-9)
    * [Ejemplo 8: Probando los dígitos con bloques](#ejemplo-8-probando-los-d%C3%ADgitos-con-bloques)
    * [Ejemplo 9: Seleccionando dos dígitos con un interruptor](#ejemplo-9-seleccionando-dos-d%C3%ADgitos-con-un-interruptor)
  * [Dígitos hexadecimales: A-F](#d%C3%ADgitos-hexadecimales-a-f)
    * [Ejemplo 10: probando los dígitos hexadecimales con bloques](#ejemplo-10-probando-los-d%C3%ADgitos-hexadecimales-con-bloques)
  * [Letras](#letras)
    * [Ejemplo 11: Probando las letras con bloques](#ejemplo-11-probando-las-letras-con-bloques)
* [Decodificadores](#decodificadores)
  * [DisplayBit](#displaybit)
    * [Ejemplo 12: Mostrando el estado de un sensor IR en el display](#ejemplo-12-mostrando-el-estado-de-un-sensor-ir-en-el-display)
    * [Tablas en binario y hexadecimal](#tablas-en-binario-y-hexadecimal)
    * [Bloque DisplayBit](#bloque-displaybit)
  * [DisplayBit2](#displaybit2)
    * [Ejemplo 13: Cuenta cíclica de 0 a 3](#ejemplo-13-cuenta-c%C3%ADclica-de-0-a-3)
  * [DisplayBit3](#displaybit3)
    * [Ejemplo 14: Conversión de binario a decimal](#ejemplo-14-conversi%C3%B3n-de-binario-a-decimal)
  * [DisplayDec](#displaydec)
    * [Ejemplo 15: Prueba de dígitos decimales 0-9](#ejemplo-15-prueba-de-d%C3%ADgitos-decimales-0---9)
  * [DisplayHex](#displayhex)
    * [Ejemplo 16: Mostrando dígitos hexadecimales](#ejemplo-16-mostrando-digitos-hexadecimales)
* [Notas sobre displays de ánodo común](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-24:-Display-de-7-segmentos#notas-sobre-displays-de-%C3%A1nodo-com%C3%BAn)
* [Ejercicios propuestos (25 Bitpoints)](#ejercicios-propuestos-25-bitpoints)
* [Ejercicios entregados](#ejercicios-entregados)
  * [Joaquín Cubillo](#joaqu%C3%ADn-cubillo)
  * [Federico Coca (fgcoca)](#federico-coca-fgcoca)
  * [Ximo Catala (ximocat)](#ximo-catala-ximocat)
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

Para **mostrar digitos** o cualquier otro dibujo en el display, sólo tenemos que determinar qué **segmentos** queremos **encender** y calcular su **valor de 7 bits**. Tendremos un número asociado a cada uno de los dibujos

## Ejemplo 6: Dígito 0

Comenzaremos mostrando el **dígito 0** en el Display. Para lograrlo, hay que encender todos los segmentos salvo el **g**, que debe estar apagado. Por tanto, el **número a enviar** es el **1111110** binario o el **7E** en hexadecimal

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/ejemplos-digitos-01.png)

El **circuito** en Icestudio es el siguiente

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/ejemplos-digitos-02.png)

Lo **cargamos** y lo **probamos**. ¡Ahí tenemos nuestro 0!

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/ejemplos-digitos-03.jpg)

### Ejemplo 7: Dígito 0 desde constante en bloque

El valor de **7 bits** para representar el **dígito 0** lo podemos convertir en un **bloque constante**, por lo que el ejemplo 6 quedaría reducido a este **circuito**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/ejemplos-digitos-04.png)

Estas constantes se encuentra en la colección **Academia-Jedi-HW-24** en el **menú Const/7Seg**

## Dígitos decimales (0-9)

Repetimos el proceso anterior, con el resto de dígitos decimales (0-9), y obtener así todos los **valores de activación**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/ejemplos-digitos-05.png)

Que se **resumen** en esta **tabla**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/ejemplos-digitos-06.png)

### Ejemplo 8: Probando los dígitos con bloques

En este ejemplo se muestra el **dígito 3** a partir de su **bloque constante**. 

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/ejemplos-digitos-07.png)

Están disponibles el **resto de bloques** para hacer pruebas. Sólo hay que **arrastrarlos** y ponerlos encima del que esté conectado para visualizarlo en el display, como se muestra en esta **animación**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/ejemplos-digitos-08.gif)

### Ejemplo 9: Seleccionando dos dígitos con un interruptor

Usando un **interruptor externo**, mostraremos en el display los **dígitos 7** y **9**. Sólo tenemos que colocar los dos **bloques constantes** 7 y 9 y usar un **multiplexor de 7 bits** para seleccionar qué valor enviar a los pines del display

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/ejemplos-digitos-09.png)

Lo **cargamos** y lo **probamos**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/ejemplos-digitos-10.gif)

## Dígitos hexadecimales (A-F)

Con los displays de 7 segmentos también se pueden visualizar **dígitos hexadecimales**. Los dígitos del 0 al 9 ya los tenemos. Nos faltan los del **A** a la **F**. Calculamos sus valores:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/ejemplos-digitos-11.png)

Se resumen en esta **tabla**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/ejemplos-digitos-12.png)

### Ejemplo 10: Probando los dígitos hexadecimales con bloques

En este ejemplo se muestra el **dígito E** a partir de su **bloque constante**, junto al resto de bloques disponibles

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/ejemplos-digitos-13.png)

Lo **cargamos** y lo **probamos**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/ejemplos-digitos-14.jpg)

## Letras

También se pueden **representar letras** en los displays de 7 segmentos. En [este enlace de la wikipedia](https://es.wikipedia.org/wiki/Visualizador_de_siete_segmentos) se muestra la representación de todo el **alfabeto latino**. Sin embargo, algunos caracteres son poco intuitivos. Aquí mostramos los **20** caracteres que son bastante reconocibles: a,b,c,d,e,f,g,h,i,j,l,n,ñ,o,p,q,r,s,u,y

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/ejemplos-digitos-15.png)

Y en esta tabla se **resumen** sus valores

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/ejemplos-digitos-16.png)

### Ejemplo 11: Probando las letras con bloques

En este ejemplo se muestra la **letra J** a partir de su **bloque constante**, junto al resto de bloques disponibles

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/ejemplos-digitos-17.png)

Lo **cargamos** y lo **probamos**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/ejemplos-digitos-18.jpg)

# Decodificadores

Aunque podemos representar diferentes formas en el display, típicamente se usa para **mostrar números**. Para ello se usan unos **circuitos combinacionales**, llamados **decodificadores**. Por su entrada llega un **número binario**, de varios bits, y por la salida se obtienen los **7 bits** para activar los segmentos correspondientes al número de entrada. Se denominan **decodificadores BCD a 7 segmentos**

Para representar los **dígitos del 0 al 9** se nececitan **4 bits**. Por ello, los decodificadores típicos BCD a 7 segmentos tiene **4 bits de entrada** y **7 de salida**

Pero nos puede interesar visualizar números de **menos de 4 bits**. Empezaremos por el más sencillo: el **displayBit**, que muestra el **dígito decimal 0** ó **1** correspondiente al bit de entrada

## DisplayBit

El **decodificador** más sencillo es el que llamaremos **DisplayBit**. Sólo tiene **un bit de entrada** y nos permite visualizar en el display los **dígitos 0** y **1** correspondientes al estado del bit de entrada

Lo diseñamos a partir de una **tabla de verdad**, con un bit de entrada y 7 de salida. A partir del tutorial 24 las tablas se pueden rellenar bien en **hexadecimal** o en **binario**

### Ejemplo 12: Mostrando el estado de un sensor IR en el display 

Mostraremos en el display el **estado de un sensor de IR**. Cuando **no detecta** ningún objeto, el sensor devuelve un **0**, por lo que se visualizará en el display el **dígito 0**. Al **detectar** un objeto devuelve un **1** y se visualiza el **dígito 1**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/DisplayBit-01.png)

El **montaje** es el siguiente

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/DisplayBit-02.jpg)

Lo **cargamos** y lo **probamos**. En este **vídeo** se puede ver en funcionamiento. El controlador **DisplayBit** nos permite "ver" los bits de manera más legible. La **interfaz** con nuestros bits ha mejorado :-)

[![Click to see the youtube video](http://img.youtube.com/vi/boXZusFCCIU/0.jpg)](https://www.youtube.com/watch?v=boXZusFCCIU)

### Tablas en binario y hexadecimal

A partir del 31 de Julio de 2018, [Jesús Arroyo](https://github.com/Obijuan/iceFactory/pull/2) ha incluido en la [fábrica de tablas de Icestudio](https://obijuan.github.io/iceFactory/icetable/icetable.html) la posibilidad de generar tablas con contenido **binario** o **hexadecimal**

Este es el mismo **ejemplo 12**, pero implementando con una **tabla en binario**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/DisplayBit-03.png)

### Bloque DisplayBit

Para hacer **más fácil** el uso del **controlador DisplayBit**, se ha incluido en un **bloque** dentro de la **colección 24**. Está disponible en el menú **Comb/Decodificadores/7Seg/Cátodo_común/DisplayBit**

Este es el mismo ejemplo 12 pero implementado con este decodificador

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/DisplayBit-04.png)

## DisplayBit2

El decodificador **DisplayBit2** tiene **2 bits** de entrada y **7 de salida**. Permite mostrar en el display números de 2 bits. Los **dígitos** que se muestran son: **0**, **1**, **2** y **3**

### Ejemplo 13: Cuenta cíclica de 0 a 3

Se usan dos **corazones** de periodos 2 y 4 segundos para mostrar una **cuenta cíclica** en la que se muestran los **dígitos** del **0** al **3**. Se ha implementado con una **tabla de verdad hexadecimal** de 2 bits de entrada y 7 de salida

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/DisplayBit-05.png)

Lo **cargamos** y lo **probamos**. En este **vídeo** se puede ver en acción:

[![Click to see the youtube video](http://img.youtube.com/vi/nUOlFrh3aeQ/0.jpg)](https://www.youtube.com/watch?v=nUOlFrh3aeQ)

Este **decodificador** lo metemos dentro de un **bloque**. Este es el mismo ejemplo anterior, pero usando el nuevo bloque **DisplayBit2**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/DisplayBit-06.png)

## DisplayBit3

El decodificador **DisplayBit3** tiene **3 bits** de entrada y 7 de salida, y permite visualizar los **dígitos del 0** al **7**

### Ejemplo 14: Conversión de binario a decimal

En este ejemplo colocamos **3 interruptores externos** por los que se introduce un número en **binario** y por el display se muestra el número en **decimal**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/DisplayBit-08.png)

Este es el **montaje**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/DisplayBit-09.jpg)

Lo **cargamos** y lo **probamos**. En este **vídeo** lo vemos en acción

[![Click to see the youtube video](http://img.youtube.com/vi/W0V5RZ-waZg/0.jpg)](https://www.youtube.com/watch?v=W0V5RZ-waZg)

El **decodificador** lo metemos dentro de un **bloque**. Este ejemplo es el mismo que el anterior, pero usando el nuevo bloque **DisplayBit3**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/DisplayBit-07.png)

## DisplayDec

Este es el típico **decodificador BCD a 7 segmentos**. Los números **BCD** (Decimal codificado en binario) con de **4 bits**, y representan los **dígitos decimales** del **0** al **9**

### Ejemplo 15: Prueba de dígitos decimales 0 - 9

Para comprobar que se muestran todos los dígitos correctamente colocaremos **4 interruptores externos** para introducir los **números en BCD** y ver su salida en el display de 7 segmentos

Usamos una **tabla de verdad** de 4 entradas y 7 salidas, que realiza la **conversión** entre **BCD** y los **7 segmentos**. Si se introduce un número **mayor de 9** el display permanecerá **apagado**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/blob/master/wiki/Tutorial-24/DisplayBit-10.png)

Este es el **montaje**. Es igual que el del ejemplo 14, pero con un **interruptor externo adicional**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/DisplayBit-11.jpg)

Lo **cargamos** y lo **probamos**. En este **vídeo** se muestra en funcionamiento. Se puede ver cómo los dígitos mayores a 9 no se muestran

[![Click to see the youtube video](http://img.youtube.com/vi/6J3UF13qh6I/0.jpg)](https://www.youtube.com/watch?v=6J3UF13qh6I)

El **decodificador** lo metemos dentro de un **bloque**. Este ejemplo es el mismo que el anterior, pero usando el nuevo bloque **DisplayDEC**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/DisplayBit-12.png)

## DisplayHex

El último decodificador que veremos es el **DisplayHEX**. Es igual que el DisplayDEC, de 4 bits a 7 segmentos, pero completado para mostrar los **dígitos hexadecimales** **0-9** y **A-F**

### Ejemplo 16: Mostrando Digitos hexadecimales

El **ejemplo** es el mismo que el 15: usaremos **4 interruptores externos** para introducir el **número en binario** y observar su **conversión** a **hexadecimal** en el display

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/DisplayBit-13.png)

Lo **cargamos** y lo **probamos**

[![Click to see the youtube video](http://img.youtube.com/vi/WwU66JwobN0/0.jpg)](https://www.youtube.com/watch?v=WwU66JwobN0)

Y como hemos hechos antes, lo convertimos en el **bloque DisplayHEX** para que sea muy **fácil de utilizar**. El ejemplo anterior se haría de esta forma, con el **nuevo bloque**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/DisplayBit-14.png)

# Notas sobre Displays de ánodo común

En la colección [Academia-Jedi-HW-24.zip](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/Collections/Academia-Jedi-HW-24.zip) se han incluido las **constantes** y los **bloques** para trabajar tanto con **displays de 7 segmentos** de **ánodo común** como de **cátodo común**

Los **ejemplos** del tutorial se han hecho para displays de **cátodo común** (lógica positiva). Para que funcionen con los de ánodo común (lógica negativa) sólo hay que **sustituir los decodificadores** por los equivalente pero de ánodo común (disponibles en la colección 24). En el caso de los ejemplos que envían directamente valores a los segmentos, sólo hay que **invertir estos valores** (sustituir los unos por ceros y los ceros por unos)

# Ejercicios propuestos (25 BitPoints)

Ver los detalles de los ejercicios y las **entregas** en el menú **Archivos/Ejemplos/2-Ejercicios** de la colección de este tutorial

**Resumen**:

* **Ejercicio 24.1** (Total **5 Bitpoints**): **Conexión del 7 segmentos**

Conectar un **display de 7 segmentos** a los pines **GP0 - GP7** de la Icezum Alhambra. Enviar la constante "8" del display para que **se enciendan todos los segmentos** y comprobar que las conexiones están bien (lamp test). Activar también el **punto**

* **Ejercicio 24.2** (Total **5 Bitpoints**): **Mostrar el estado de dos sensores IR**

Hacer un circuito digital para mostrar en un display de 7 segmentos el estado de **dos sensores IR**. Se utilizará un **interruptor externo** para seleccionar qué sensor es el que se visualiza en el display. Para cada sensor IR se visualiza su estado mostrando los **dígitos 0** ó **1**

* **Ejercicio 24.3** (Total **10 Bitpoints**): **Decodificador decimal con caracteres extra**

Hacer un bloque **decodificador** decimal a siete segmentos que tenga **6 caracteres extra** correspondiente a los números del **10** al **15**. Los nuevos caracteres son los siguientes:  

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-24/ejercicio3.png)

* **Carácter 10**: Ningún segmento activado
* **Carácter 11**: segmento d activado
* **Carácter 12**: segmentos d y g activados
* **Carácter 13**: segmentos a,d y g activados
* **Carácter 14**: segmentos a,b, f y g activados
* **Carácter 15**: segmentos c,d,e y g activados

Meter este decodificador en un bloque llamado **DisplayEXTRA**. Utilizar este icono: [7Seg-Extra.svg](https://github.com/FPGAwars/icestudio-block-icons/raw/master/7Seg/7Seg-Extra.svg)

Como **circuito de pruebas** conectar **4 interruptores externos** para seleccionar el carácter a visualizar en el display

* **Ejercicio 24.4** (**5 Bitpoints**). Ejercicio Libre. Premiar la creatividad. **Entregar** por redes sociales o github: Pantallazos, enlaces, vídeos, etc...

# Ejercicios entregados

## Joaquín Cubillo

### Ejercicio 24.1

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-24/jcubilloarr/1.png)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/XE36j6ikips/0.jpg)](https://www.youtube.com/watch?v=XE36j6ikips)

### Ejercicio 24.2

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-24/jcubilloarr/2.png)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/4RBEhuJ93Og/0.jpg)](https://www.youtube.com/watch?v=4RBEhuJ93Og)

### Ejercicio 24.3
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-24/jcubilloarr/3.png)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/6LHMxjH_PBo/0.jpg)](https://www.youtube.com/watch?v=6LHMxjH_PBo)

### Ejercicio 24.4

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-24/jcubilloarr/4.png)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/BPnDNPP1VjA/0.jpg)](https://www.youtube.com/watch?v=BPnDNPP1VjA)

## Federico Coca (@fgcoca)

### Ejercicio 24.1

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-24/fgcoca/Ejercicio-1/Ejercicio24_1%20%E2%94%80%20P.png)

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-24/fgcoca/Ejercicio-1/Ejercicio24_1%20%E2%94%80%20Foto.jpg)

### Ejercicio 24.2
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-24/fgcoca/Ejercicio-2/Ejercicio24_2%20%E2%94%80%20P.png)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/vZb5eIKg76s/0.jpg)](https://www.youtube.com/watch?v=vZb5eIKg76s)

### Ejercicio 24.3

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-24/fgcoca/Ejercicio-3/-Ejercicio24_3_Block%20%E2%94%80%20P.png)

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-24/fgcoca/Ejercicio-3/-Ejercicio24_3_Block%20%E2%94%80%20P-interior.png)

## Ximo Catala (Ximocat)

### Ejercicio 24.1

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-24/ximocat/Ejercicio24_1.jpg)

### Ejercicio 24.2
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-24/ximocat/Ejercicio24_2.jpg)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/DFDa8fraJM4/0.jpg)](https://www.youtube.com/watch?v=DFDa8fraJM4)

### Ejercicio 24.3

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-24/ximocat/Ejercicio24_3.jpg)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/95SYVwP2Mno/0.jpg)](https://www.youtube.com/watch?v=95SYVwP2Mno)

### Ejercicio 24.4

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-24/ximocat/Ejercicio24_4.jpg)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/HrwtUsNxybY/0.jpg)](https://www.youtube.com/watch?v=HrwtUsNxybY)


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



