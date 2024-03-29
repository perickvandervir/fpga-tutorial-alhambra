![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-20/Portada/Tut-20-portada.png)

# Vídeo

[![Click to see the youtube video](http://img.youtube.com/vi/7NsLgfqu--Q/0.jpg)](https://www.youtube.com/watch?v=7NsLgfqu--Q&list=PLmnz0JqIMEzXaeYVzf2TfTzRekPIVoljw&index=20)

Haz click en la imagen para ver el **vídeo en Youtube**

# Descripción

Hasta ahora hemos hecho circuitos que trataban con los bits de manera aislada. Con circuitos más complejos, es mejor **agrupar los cables en buses**, y **tratar la información como números**, en vez de bits aislados. Aprenderemos a crear **buses**, **agrupar** entradas y salidas, y utilizar componentes cuyas entradas y salidas son **números**

# Colección

[Academia-Jedi-HW-20.zip](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-20/Collection/Academia-Jedi-HW-20.zip): Colección para este tutorial. Descargar e instalar 

# Contenido

* [Introducción](#introducci%C3%B3n)
* [Buses](#buses)
  * [Buses de 2 bits](#buses-de-2-bits)
  * [Buses de 4 bits](#buses-de-4-bits)
  * [Buses de 8 bits](#buses-de-8-bits)
* [Números constantes paramétricos](#n%C3%BAmeros-constantes-param%C3%A9tricos)
  * [Ejemplo 4: Constante genérica de 8 bits](#ejemplo-4-constante-gen%C3%A9rica-de-8-bits)
  * [Ejemplo 5: Constante genérica de 4 bits](#ejemplo-5-constante-gen%C3%A9rica-de-4-bits)
  * [Truncado de números](#truncado-de-n%C3%BAmeros)
  * [Números en decimal, hexadecimal y binario](#n%C3%BAmeros-en-decimal-hexadecimal-y-binario)
* [Separadores y agregadores de bus](#separadores-y-agregadores-de-bus)
  * [Buses de 2 bits](#buses-de-2-bits-1)
  * [Buses de 4 bits](#buses-de-4-bits-1)
  * [Buses de 8 bits](#buses-de-8-bits-1)
* [Multiplexores de N bits](#multiplexores-de-n-bits)
* [Ejercicios propuestos (20 Bitpoints)](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-20:-Buses-y-n%C3%BAmeros#ejercicios-propuestos-20-bitpoints)  
* [Ejercicios entregados](#ejercicios-entregados)
  * [Ximo Catalá](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-20:-Buses-y-n%C3%BAmeros#ximo-catal%C3%A1)
  * [Federico Coca (fgcoca)](#federico-coca-fgcoca)
  * [SrViriato](#srviriato)
* [Autor](#autor)
* [Licencia](#licencia)
* [Enlaces](#enlaces)
* [Preguntas frecuentes](#preguntas-frecuentes)

# Introducción

Hasta ahora hemos trabajado con **bits individuales**. Cada bit se transmite por un cable, de un componente a otro. Por ejemplo, si queremos encender **dos LEDs**, hacemos un circuito como este:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-20/Bus-2bits-1.png)

Sin embargo, también podemos **agrupar los bits** en un cable más gordo, que llamamos **Bus**. Los bit se siguen transportando igual, y en paralelo, cada uno por su cable, pero sólo dibujamos un único cable de bus. De esta forma, **los diseños son más sencillos de dibujar y de entender**

Según los **números** con los que trabajemos en nuestro circuito, usaremos buses de un **tamaño** un otro. 

# Buses

Veremos buses de 3 tamaños, a modo de ejemplo. Empezaremos por los **buses más simples**: de **2 bits**. Luego mostraremos de **4** y de **8 bits**

## Buses de 2 bits

Haremos un circuito equivalente al anterior, para **enceder 2 LEDs**, pero usando una **constante**  y un bus de **2 bits**. Primero colocamos la **constante 3** (que en binario es 11) desde el menú **Const/Bus/2-bits/Valor_3**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-20/Bus-2bits-2.png)

Nos aparecerá un bloque con el **número 3**, y el número en binario debajo (11)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-20/Bus-2bits-3.png)

Por la salida de este bloque aparece un cable más gordo de lo normal, con el nombre **k[1:0]**. Se trata de un **bus de 2 bits**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-20/Bus-2bits-4.png)

La letra **k** es el nombre que se le ha dado al bus en la salida de la constante, pero podría tener cualquier otro. Entre **corchetes** se indican los **números de los cables** que transportan los bits más significativo y menos significativo respectivamente. Siempre usaremos el **0** para referirnos al de **menor peso**. Como es un bus de 2 bits, el más significativo será el 1

Los **LEDs** los trataremos como un **bloque** al que le entra un **bus de 2 bits**. Para ello colocamos un pin de salida como hacemos normalmente, pero en el nombre usamos la nomenclatura del bus: **LED[1:0]**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-20/Bus-2bits-5.png)

Al pinchar sobre el **OK** nos aparecerá un **bloque con 2 salidas**, y un bus de entrada. Lo colocamos en el circuito

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-20/Bus-2bits-6.png)

Ahora **tiramos el bus** como si se tratase de un cable cualquiera, uniendo los dos bloques. Y por último seleccionamos los LEDs por lo que enviar los bits. Por ejemplo **LED1** y **LED0**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-20/Bus-2bits-7.png)

Lo **cargamos** y lo **probamos**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-20/Bus-2bits-8.png)

Vemos que los dos LEDs, LED0 y LED1 se encienden. Lo importante es saber que los dos circuitos que hemos probado, el que tiene **cables aislados** y el que tiene el **bus**, **son equivalentes**. Este ejemplo de comparación se encuentra disponible en **Archivo/Ejemplos/1-Ejemplos/01-Bus-2Bits-LEDs**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-20/Bus-2bits-9.png)

Al trabajar con buses nos centramos en los **números**. Lo que transmitimos de un sitio a otro son números. Y eso es lo que nos importa, aunque internamente se transportes los bits individualmente

Los buses se **comportan igual** que los cables que ya conocemos. Si queremos tirar **más de un bus** desde la misma salida lo hacemos igual. En este ejemplo se están encendiendo **4 LEDs** usando **dos buses de 2 bits**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-20/Bus-2bits-1-1.png)

Lo **cargamos** y lo **probamos**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-20/Bus-2bits-10.png)

Las **entradas** también se pueden **agrupar en un bus**. En este ejemplo, agrupamos los dos pulsadores de la Icezum Alhambra en un bloque de entrada de 2 bits, y los conectamos con los **LEDs de salida** mediante un **bus de 2 bits**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-20/Bus-2bits-11.png)

## Buses de 4 bits

El funcionamiento de los **buses de 4 bit** (y de cualquier tamaño) es similar al de dos bits. Este es el circuito de ejemplo para **encender 4 LEDs** usando un bus de 4 bits. Está accesible desde el menú **Archivo/Ejemplos/1-Ejemplo/02-BUS-4bits-LEDs**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-20/Bus-4bits-1.png)

Vamos a fijarnos en la **constante 15**. Es el número 15, que en binario es **1111** (Todos los bits a 1), por lo que al enviarla por el bus, hará que se enciendan todos los LEDs. En la parte inferior derecha de la constante está escrito el carácter **F**, que es el número 15 en **hexadecimal**. El bus de salida utilizado tiene esta notación **k[3:0]**, cuyo significado se muestra en esta figura

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-20/Bus-4bits-2.png)

Es un bus formado por **4 cables**, numerados desde el 0 (que transporta el bit menos significativo) hasta el 3 (que lleva el más significativo). Esta constante está disponible en el menú **Const/Bus/4-bits/Valor_15**

Lo **cargamos** y lo **probamos**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-20/Bus-4bits-3.png)

Ahora ponemos otra **constante de 4 bits**, como por ejemplo el **5**. Cargamos el circuito y vermos que se encienden los LEDs 6 y 4, ya que el 5 en binario es **0101**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-20/Bus-4bits-4.gif)

## Buses de 8 bits

Los **buses de 8 bits** se utilizan muchísimo. Los **procesadores** de los primeros ordenadores que llegaron a nuestras casas, en los inicios de la informática, eran de **8-bits**. Por ejemplo el procesador [Z80](https://es.wikipedia.org/wiki/Zilog_Z80) o el [6502](https://es.wikipedia.org/wiki/MOS_6502), son de 8-bits. Se usaron en los ordenadores de la época, como [ZX-spectrum](https://es.wikipedia.org/wiki/Sinclair_ZX_Spectrum) o el [Amstrad CPC](https://es.wikipedia.org/wiki/Amstrad_CPC) entre otros muchos. Para **transportar** los números de 8 bits, estos procesadores usan **buses de 8 bits**

El circuito para **encender los 8 leds** de la Icezum Alhambra usando un **bus de 8 bits** es el siguiente:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-20/Bus-8bits-1.png)

Hemos utilizado la constante de 8-bits **255**, que se corresponde con el número binario que tiene sus **8 bits a 1**, por lo que al enviarlo por el bus de 8-bits **se encienden todos los LEDs**. El valor en **hexadecimal** es el **FF**. Esta constante se encuentra en el menú **Const/Bus/8_bits/Valor_255**. Como salida tiene un **bus de 8 bits**, que se ha denotado por **k[7:0]**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-20/Bus-8bits-2.png)

El cable que lleva el **bit de mayor** peso se ha numerdo como **7**, y que lleva el de **menor peso** como **0**

Lo **cargamos** y lo **probamos**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-20/Bus-8bits-3.png)

Probamos con otra constante, por ejemplo **170**. Se corresponde con el número hexadecimal **AAh**, y el binario **10101010**, que se caracteriza porque tiene los bits alternados: pares a uno, impares a 0.  La constante **85** (**55h**) es la negada:  se correspone con el número binario 01010101, en el que los bits pares están a 0 y los impares a uno. Ambas constantes, **170** y **85** se **utilizan muchísimo** en hardware, para hacer pruebas

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-20/Bus-8bits-5.gif)

# Números constantes paramétricos

Las constantes que hemos utilizado hasta ahora para introducir valores por los buses, tienen **valores fijos**, que no se puede cambiar. Volvamos al **ejemplo** anterior, que **enciende los 8 leds** de la icezum alhambra a través de la constante 255 en el bus de 8 bits. Si hacemos **doble click** sobre la **constante**, verás que está creada a partir de una **constante genérica k**, a la que se le pasa como **parámetro** el valor que queramos

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-20/constantes-01.gif)

Esa **constante genérica** la podemos colocar desde el menú **Const/Bus/8_bits/Genérico** y luego le pasamos el valor **como parámetro**. 

## Ejemplo 4: Constante genérica de 8 bits

En este **ejemplo** estamos usando una constante genérica de 8 bits al que le pasamos el **valor 129** para mostrar en los LEDs

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-20/constantes-02.png)

Si **cargamos** este circuito en la placa, veremos que se encienden los leds LED7 y LED0, ya que el 129 en binario es 10000001

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-20/constantes-03.png)

Al haber usado una constante genérica, podemos editar este valor y poner el que queramos, de 8 bits. **Podemos introducir cualquier número de 8 bits**

## Ejemplo 5: Constante genérica de 4 bits

Si queremos introducir **constantes de 4 bits** se hace la misma forma, pero ahora colocamos el bloque que está en el menú **Const/Bus/4_bits/Genérico**. En este ejemplo usamos **2 constantes de 4 bits** para activar los LEDs. La primera actúa sobre los 4 leds más significativos, y la segunda sobre los 4 menos significativos. Los valores que enviamos son **12** (1100) y **3** (0011)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-20/constantes-04.png)

Si **cargamos** el circuito en la Icezum Alhambra, se nos **encenderán** los siguientes LEDs

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-20/constantes-05.png)

El resultarío sería exactamente igual si en lugar de 2 constantes de 4 bits enviamos el valor constante **195**, de 8 bits  (que en binario es 11000011)

## Truncado de números

Cuando trabajamos con números y buses es **responsabilidad del diseñador** el usar los valores correctos. Cuando se asignan constantes a buses, se **trunca** la constante a los bits del bus definido, **ignorándose** el resto. Así por ejemplo, si estamos usando un bus de 4 bits, el valor más alto que podemos usar es de 15, o de lo contrario se truncará el valor. En el siguiente ejemplo estamos introduciendo un valor de 16 a un bus de 4 bits

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-20/constantes-06.png)

Lo que ocurrirá es lo siguiente: El **valor 16** en binario es **10000**. Se necesitan 5 bits para representarlo. Como lo estamos sacando por un **bus de 4 bits**, sólo se envían los 4 bits menos significativos, ignorándose el 1 de mayor peso (El número se ha truncado). El resultado es que no se encenderá ningún LED

Es importante recordar esto, y siempre tener en la cabeza los números de bits que estamos usando, para **evitar truncamientos indeseados**

## Números en decimal, hexadecimal y binario

Si no indicamos nada, cuando introducimos los valores como parámetros, **por defecto están en decimal**. Sólo tenemos que tener la precaución de que no se trunque. Todos los valores que hemos introducido hasta ahora estaban en decimal.

Sin embargo, es posible introducirlos también en **hexadecimal** o **binario**, usando la **notación de Verilog**. Esta notación tiene la siguiente **sintáxis**. Usaremos como ejemplo el **valor 255 de 8 bits**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-20/constantes-07.png)

Así, si quieremos **encender los 8 LEDs**, cualquiera de los siguientes valores sería **válido**: 

```verilog
255
8'd255
8'hFF
8'b11111111
```

Y aquí está el **circuito en icestudio**, donde introducimos el valor en **binario**, pero se muestran las otras posibilidades

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-20/constantes-08.png)

Este es otro ejemplo en el que se envían **4 constantes de 2 bits** a los LEDs, usando las cuatro representaciones anteriores: **por defecto**, **decimal**, **hexadecimal** y **binario**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-20/constantes-09.png)


# Separadores y agregadores de bus

En nuestros diseños podemos estar trabajando con **cables sueltos**, y en un momento determinado **unirlos** para convertirlos en un **bus**. Esto lo hacemos usando un componente que denominamos **agregador**. El **símbolo** que utilizamos es el siguiente: 

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-20/agregador-1.png)

Y también podemos hacer la operación inversa, **extraer los cables aislados** a partir de un bus. El componente se llama **separador**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-20/agregador-2.png)

Mostraremos algunos **ejemplos de agregadores** y **separadores** de bus, de tamaños de **2**, **4** y **8** bits, aunque cuando aprendamos a hacer nuestros propios bloques nos podremos crear exactamente los que necesitemos

## Buses de 2 bits

Como ejemplo vamos a **encender 2 LEDs** usando un **bus de 2 bits**, pero **separando** los cables y luego volviendo a **unirlos**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-20/agregador-3.png)

Es simplemente un ejemplo de uso. Este circuito es equivalente al que habíamos usado antes con un único cable de bus. La **constante 3** de **dos bits** se lleva por un bus hasta el **separador**, donde se obtiene sus dos cables, que se llevan de nuevo a un **agregador** para volver a formar un **bus de 2 bits** que se muestra por los LEDs 1 y 0

## Buses de 4 bits

Los **separadores de bus de 4 bits**, parten el bus en otros dos buses de 2 bits. Por los **agregadores** entran dos buses de 2 bits, y se obtiene a la salida un bus de 4 bits. Como ejemplo sacaremos la constante 10 de 4 bits por los LEDs

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-20/agregador-4.png)

La constante va por un **bus de 4 bits** y entra en un **separador**, obteniéndose 2 buses de 2 bits a su salida. Estos buses se llevan a un **agregador** que vuelve a formar otra vez un bus de 4 bits que se lleva hasta los LEDs

Una de las aplicaciones muy usadas de los agregadores y separadores es la de **intercambiar el orden de los bits de un bus**. En este ejemplo enviamos por un lado la constante 10 de 4 bits a los LEDS 7,6,5 y 4 y por otro se intercambian los dos bits de mayor y menor peso y la nueva constante se saca por los LEDS 3,2,1 y 0

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-20/agregador-6.png)

Cambiar las posiciones de los bits es una forma simplificada de **encriptar** información

## Buses de 8 bits

Como último ejemplo hacemos lo mismo pero con **separadores** y **agregadores de 8 bits**. Se envía la constante AAh (10101010) de 8 bits a los LEDs, primero por un bus de 8 bits que entra en un separador, obteniéndose dos buses de 4 bits. Estos entran en un agregador que vuelve a formar el bus de 8 bits que se envía a los LEDs

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-20/agregador-5.png)

# Multiplexores de N bits

Los buses se usan como entradas y salidas de otros componentes, por ejemplo de los multiplexores. Hasta ahora sólo habíamos usados **multiplexores de 1 bit**, en los que los canales que entran son de 1 bit, y la salida son por tanto, también de 1 bit

Con los multiplexores de N bits podemos **seleccionar** qué números se envían por un bus de salida. Los canales, ahora, serán fuentes de números

Como **ejemplo de aplicación** haremos un circuito que encienda alternativamente los **LEDs pares** e **impares** de la Icezum Alhambra. Esto ya lo hemos hecho previamente, pero **pensando en bits aislados**. Ahora lo haremos igual, pero **pensando con números**

Utilizaremos un **multiplexor 2 a 1 de 8 bits**. Se encuentra en el menú **Comb/Mux/8-bits/Mux-2-1**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-20/Mux-Nbits-1.png)

Este multiplexor tiene dos **entradas de datos**, **i1[7:0]** e **i0[7:0]**, que ahora son **buses de 8 bits**. La **salida** es también un bus de 8 bits, que se denota por **o[7:0]**. La entrada de selección es de 1 bit

Para hacer que los LEDs pares se alternen con los impares **pensamos** en los LEDs como un **número de 8 bits**. Si enviamos el número **170** se encenderán los **bits pares**, ya que este número en binario es **10101010** (y en hexadecimal AA). Por el contrario, si enviamos el número **85**, se encenderán sólo los **impares**, porque en binario es **01010101** (y 55 en hexadecimal)

Por tanto, nuestro circuito lo único que tiene que hacer es **enviar alternativamente** los valores **170** y **85** a los **LEDs**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-20/Mux-Nbits-2.png)

Lo **cargamos** y lo **probamos**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-20/Mux-N-bits-3.gif)

De forma similar podemos usar **multiplexores de otro número de bits**. Por ejemplo, en este otro ejemplo usamos un **multiplexor de 4 a 1 de 4 bits** para sacar por los LEDs dos secuencias, según el estado del **pulsador**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-20/Mux-Nbits-4.png)

Cuando el **pulsador** no está apretado (sel1=0), se seleccionan los **canales 0** y **1** cada medio segundo, por lo que por los LEDs se visualizan los **números 3** y **12** (0011 y 1100 en binario). Cuando el pulsador está apretado (sel1=1), se seleccionan los **canales 2** y **3**, enviándose las constantes **10** y **5** (1010 y 0101 en binario) a los LEDs

Lo **cargamos** y lo **probamos**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-20/Mux-Nbits-5.gif)

# Ejercicios propuestos (20 BitPoints)

Ver los detalles de los ejercicios y las **entregas** en el menú **Archivos/Ejemplos/2-Ejercicios** de la colección de este tutorial

**Resumen**:

* **Ejercicio 1** (Total **5 Bitpoints**):  Secuencia de 4 estados en los LEDs

Diseñar un circuito digital que muestre por los **8 LEDs** de la Icezum Alhambra la siguiente **secuencia**: 0, 15, 255 y 15, que se repetirá indefinidamente. Utilizar un multiplexor de 4 a 1 de 8 bits

* **Ejercicio 2** (Total **5 Bitpoints**): Operación AND en bus de 2 bits

Diseñar un circuito digital que saque por los **LEDs 7** y **6** los pulsadores **SW2** y **SW1**, usando un **bus de 2-bits**. Además, se sacará por el **LED0** el resultado de la **operación AND** entre SW1 y SW2, obteniendo sus valores del bus de 2 bits, mediante un separador

* **Ejercicio 3** (Total **5 Bitpoints**): Cifrador de números de 4-bits

Diseñar un circuito digital que **cifre un número de 4-bits** mediante el **intercambio** de sus **bits centrales** (Bits 1 y 2), dejando el de mayor y menor peso iguales (bit 3 y bit 0). El número se introducirá mediante **4 interruptores externos** que entran en la icezum Alhambra mediante un **bus de 4 bits**. El número sin cifrar se sacará por los LEDs 7,6,5 y 4, y el número cifrado por los LEDs 3,2,1 y 0

* **Ejercicio 4** (**5 Bitpoints**). Ejercicio Libre. Premiar la creatividad. **Entregar** por redes sociales o github: Pantallazos, enlaces, vídeos, etc...

# Ejercicios entregados

## Ximo Catalá

### Ejercicio 1
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-20/ximocat/Ejercicio20_1.jpg)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/bNc6v789jKQ/0.jpg)](https://www.youtube.com/watch?v=bNc6v789jKQ)

### Ejercicio 2
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-20/ximocat/Ejercicio20_2.jpg)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/sOGObpO2T9E/0.jpg)](https://www.youtube.com/watch?v=sOGObpO2T9E)

### Ejercicio 3
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-20/ximocat/Ejercicio20_3.jpg)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/YbXP685Pc1w/0.jpg)](https://www.youtube.com/watch?v=YbXP685Pc1w)

### Ejercicio 4
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-20/ximocat/Ejercicio20_4.jpg)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/ct4T0T5qL9s/0.jpg)](https://www.youtube.com/watch?v=ct4T0T5qL9s)

## Federico Coca (fgcoca)

### Ejercicio 1
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-20/fgcoca/Ejercicio-1/Ejercicio20_1%20%E2%94%80%20P.png)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/SWPUMftBi9Y/0.jpg)](https://www.youtube.com/watch?v=SWPUMftBi9Y)

### Ejercicio 2
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-20/fgcoca/Ejercicio-2/-Ejercicio20_2%20%E2%94%80%20P.png)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/uFJECexVCWM/0.jpg)](https://www.youtube.com/watch?v=uFJECexVCWM)

### Ejercicio 3
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-20/fgcoca/Ejercicio-3/-Ejercicio20_3%20%E2%94%80%20P.png)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/IpAWCFdJ9Ac/0.jpg)](https://www.youtube.com/watch?v=IpAWCFdJ9Ac)

### Ejercicio 4
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-20/fgcoca/Ejercicio-4/-Ejercicio20_3%20%E2%94%80%20P.png)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http:/5oroJHIdseU/img.youtube.com/vi//0.jpg)](https://www.youtube.com/watch?v=5oroJHIdseU)

## SrViriato

### Ejercicio 1
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-20/Viriato/Ejercicio-20-1/Captura%20de%20pantalla%20-2018-06-11%2019-02-56.png)

* [Vídeo en twitter](https://twitter.com/SrViriato/status/1006251106442326018)

### Ejercicio 2
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-20/Viriato/Ejercicio-20-2/Captura%20de%20pantalla%20-2018-06-11%2019-03-45.png)

* [Vídeo en twitter](https://twitter.com/SrViriato/status/1006251255902154757)

### Ejercicio 3
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-20/Viriato/Ejercicio-20-3/Captura%20de%20pantalla%20-2018-06-11%2019-04-21.png)

* [Vídeo en twitter](https://twitter.com/SrViriato/status/1006251419182256133)

### Ejercicio 4
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-20/Viriato/Ejercicio-20-4/Captura%20de%20pantalla%20-2018-06-11%2019-54-21.png)

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



