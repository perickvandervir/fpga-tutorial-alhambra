![]()

(En construcción...)

# Vídeo

(En construcción...)

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

Haz click en la imagen para ver el **vídeo en Youtube**

# Descripción

TODO

# ¡Icestudio 0.3.3-beta!

Hemos liberado hace muy poco [Icestudio 0.3.3-Beta](https://github.com/FPGAwars/icestudio/releases/tag/v0.3.3-beta). La que estábamos usando antes era la 0.3.2. Por favor, **actualizarse** a esa versión. La colección empleada en este tutorial está hecha con esta versión, y en las anteriores no se verá correctamente

# Colección

**Academia-Jedi-HW-19.zip**: Colección para este tutorial. Descargar e instalar 

# Contenido

* [Introducción](#introducci%C3%B3n)
  * [Tablas de verdad](#tablas-de-verdad)
* [Circuitos combinacionales de 1 entrada y 1 salida](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-19:-Circuitos-combinacionales#circuitos-combinacionales-de-1-entrada-y-1-salida)
  * [Ejemplo 1: Puerta NOT con tablas](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-19:-Circuitos-combinacionales#ejemplo-1-puerta-not-con-tablas)
  * [Ejemplo 2: Cable con tablas](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-19:-Circuitos-combinacionales#ejemplo-2-cable-con-tablas)
* [Circuitos combinacionales de 2 entradas y 1 salida](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-19:-Circuitos-combinacionales#circuitos-combinacionales-de-2-entradas-y-1-salida)
    * [Ejemplo 3: Comparador de bits](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-19:-Circuitos-combinacionales#ejemplo-3-comparador-de-bits)
    * [Las puertas NAND y NOR](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-19:-Circuitos-combinacionales#las-puertas-nand-y-nor)
    * [Las puertas XOR y XNOR](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-19:-Circuitos-combinacionales#las-puertas-xor-y-xnor)
    * [Ejemplo 4: Puerta XOR con tablas de verdad](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-19:-Circuitos-combinacionales#ejemplo-4-puerta-xor-con-tablas-de-verdad)
* [Circuitos combinacionales de 3 entradas y 1 salida](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-19:-Circuitos-combinacionales#circuitos-combinacionales-de-3-entradas-y-1-salida)
  * [Ejemplo 5: multiplexor de 2 a 1 con tabla de verdad](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-19:-Circuitos-combinacionales#ejemplo-5-multiplexor-de-2-a-1-con-tabla-de-verdad)
* [Circuitos combinacionales de 4 entradas y 1 salida](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-19:-Circuitos-combinacionales#circuitos-combinacionales-de-4-entradas-y-1-salida)
  * [Ejemplo 6: Comparador de números de 2 bits](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-19:-Circuitos-combinacionales#ejemplo-6-comparador-de-n%C3%BAmeros-de-2-bits)
* Ejercicios propuestos (X Bitpoints)
* [Ejercicios entregados](#ejercicios-entregados)
* [Autor](#autor)
* [Licencia](#licencia)
* [Enlaces](#enlaces)
* [Preguntas frecuentes](#preguntas-frecuentes)

# Introducción

Los circuitos digitales realizan tres operaciones con los bits: **manipular**, **almacenar** y **transportar**. El transporte se realiza gracias a los cables. Los circuitos que realizan las **manipulaciones** pero no hacen ningún tipo de almacenamiento de información se denominan **combinacionales**. Ya hemos visto varios ejemplos de ellos: las puertas lógicas (AND, OR, NOT) y los multiplexores, pero hay muchos más circuitos combinacionales

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-19/intro-1.png)

Todos los circuitos combinaciones se caracterizan porque **NO tienen memoria**. Las operaciones que realizan son siempre las mismas, y **no dependen** de los datos que hayan recibido en el pasado. Una operación AND entre dos bits es siempre la misma, da igual el valor de las entradas en el pasado. Da igual si en el pasado ha hecho 2000 operaciones. Si en el instante actual ambas entradas están a 1, entonces la salida será 1 

## Tablas de verdad

Una característica **muy importante** de los **circuitos combinaciones** es que quedan **totalmente definidos** por su **tabla de verdad**. En ella se especifica el valor de todas sus salidas para todas las combinaciones posibles de sus entradas. Así, de forma genérica, un circuito combinacional de dos entradas y una salida tendrá una tabla con la siguiente pinta:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-19/intro-2.png)

El circuito de ejemplo tiene **2 entradas**, llamadas **a** y **b**, y una **salida**, denominada **c**. En la **tabla de verdad** se representan las salidas del circuito cuando se dan todas las **combinaciones** posibles en las entradas. Estas combinaciones de a y b es lo que se muestra en la parte de la izquierda de la tabla. En la derecha se ponen los valores asociados a sus entradas. En el dibujo se han marcado como **X** para indicar que pueden valer tanto 0 como 1 (esto depende del circuito particular que implementemos)

## Circuitos combinacionales de varias entradas y una salida

En este tutorial nos centraremos en los **circuitos combinacionales** con **una única salida**, y **varias entradas**. En realidad, los que tienen varias salidas se construyen mediante la **superposición de circuitos de una salida**. Pero esto lo veremos en los tutoriales venideros

# Circuitos combinacionales de 1 entrada y 1 salida

Comenzaremos por los circuitos combinaciones **más sencillos posibles**: los que tienen una entrada y una salida. Sólo hay dos, que se corresponde con la **puerta NOT** y la **puerta "identidad"**. Esta última un simple **cable** que sólo transmite bits

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-19/comb-1x1-1.png)

## Ejemplo 1: Puerta NOT con tablas

A partir de la versión **0.3.3** de Icestudio podemos hacer circuitos combinacionales muy fácilmente a partir de las **tablas de verdad**. Como ejemplo, vamos a crear la **puerta NOT**. Utilizaremos el pulsador integrado **SW1** de la Alhambra como entrada, y el **LED0** como salida. Colocamos primero los pines de entrada y salida

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-19/comb-1x1-2.png)

Ahora colocamos el elemento **tabla-1-1**, disponible en el menú **Comb/tablas/tabla-1-1** de la colección **Academia-Jedi-HW-19**. Es un componente que representa un **circuito combinacional genérico** con una entrada y una salida. Determinamos la tabla de verdad asignándosela como parámetro. Para ello colocamos el nuevo elemento **Basico/memory**. Es una **tabla de verdad** que podemos **editar**. Escribirmos la tabla de verdad de la **puerta NOT**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-19/comb-1x1-3.gif)

El **circuito** queda de esta manera:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-19/comb-1x1-4.png)

Lo **cargamos** en la placa y lo **probamos**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-19/comb-1x1-4.gif)

Comprobamos que efectivamente es una **puerta NOT**. Cuando **no** está apretado el pulsador, se recibe un **0** por la entrada del circuito, que se convierte en un **1** en la salida y por tanto se **enciende el LED**. Al **apretar el pulsador** sucede lo contrario: entra un **1**, que se convierte en un **0** y se **apaga** el LED0

## Ejemplo 2: Cable con tablas

Como segundo ejemplo vamos a **editar la tabla de verdad** para obtener el otro posible circuito de una entrada y una salida: la **puerta indentidad**, que en realidad es un **cable**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-19/comb-1x1-5.png)

Lo **cargamos** y lo **probamos**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-19/comb-1x1-6.gif)

Ahora se comporta como un **simple cable**: inicialmente el LED0 está apagado. Al apretar el botón se recibe un 1 que se transmite al LED y se enciende

Lo interesante de estos dos ejemplos es que conseguimos tener **dos circuitos diferentes** simplemente **cambiando los valores de la tabla de verdad**

# Circuitos combinacionales de 2 entradas y 1 salida

Los siguientes circuitos en complejidad con los que tiene **2 entradas**. Como cada una de las entradas puede encontrase en dos estados: 0 ó 1, en total hay **4 casos posibles**, por lo que las **tablas de verdad** tendrán **4 filas**. Todas las **puertas lógicas** de dos entradas, como las que hemos visto (AND y OR) son circuitos combinaciones de este tipo

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-19/comb-2x1-1.png)

Fíjate que hemos añadido una **columan nueva** en la izquierda, con el **número de fila empezando** por el 0. Ese núero de fila es el **valor en decimal** correspondiente a al número binario definido por las entradas. Así, en la fila 3, al pasar a binario tenemos que es 11. Esto quiere decir que la primera entrada está a 1 y la segunda también a 1

## Ejemplo 3: Comparador de bits

Vamos a **diseñar** nuestro primer circuito combinacional de 2 entradas y una salida. Haremos un **comparador de bits**. Cuando las dos entradas estén al mismo valor, la salida se activará a 1. En caso contrario permanecerá a 0.

Lo primero que hacemos es **definir** su **tabla de verdad**. Como tiene 2 entradas, en total tendrá **4 filas**. Las numeramos del 0 al 3 y ponemos todos los casos posibles de sus entradas. Esta parte de la tabla siempre será igual. Ahora **asignamos valores a las salida**s. Sólo estará a uno en la fila 0, ya que las dos entradas son iguales (0 y 0) y en la 3 ya ambas entradas están a 1

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-19/comb-2x1-2.png)

Ahora creamos el **circuito en icestudio** utilizando el componente **Comb/Tablas/tabla-2-1**. Conectaremos los dos bits de entrada de circuitos a los pulsadores **SW1** y **SW2** y la salida al **LED0**. Añadimos el elemento **Basico/memory** para definir la **tabla de verdad**. El circuito nos queda así:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-19/comb-2x1-3.png)

Lo **cargamos** y lo **probamos**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-19/comb-2x1-4.gif)

Vemos que el LED0 sólo se enciende cuando **los dos pulsadores están en el mismo estado**. Bien porque no están apretados, o bien porque lo están ambos

## Las puertas NAND y NOR

Además de las puertas básicas que ya conocemos, **AND**, **OR** y **NOT**, existen otras que son muy usadas. Todas ellas las podemos definir a partir de sus tablas de verdad. Las versiones **negadas** de las puertas AND y OR se denominan, **NAND** y **NOR** respectivamente

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-19/comb-2x1-5.png)

Una característica de estas puertas es que permiten crear **cualquier circuito lógico** usando sólo el mismo tipo de puertas: bien puertas NAND, o bien puertas NOR.  El computador que realizó los cálculos de navegación en el [Apolo 11](https://es.wikipedia.org/wiki/Apolo_11), la nave que llevó al primer hombre a la luna, estaba hecho **sólo con puertas NAND**

Ambas puertas, **NAND** y **NOR** se encuentran disponibles en el menú **Comb/Puertas** de la colección **Academia-Jedi-HW-19.zip**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-19/comb-2x1-6.png)

## Las puertas XOR y XNOR

Hay otras dos puertas lógicas que se usan mucho en electrónica digital: la **XOR** y la **XNOR**. La XOR se denomina **O-exclusivo**. Funciona igual que una puerta OR salvo en el caso en el que las dos entradas son 1, cuya salida es 0 en vez de 1. Las puertas **XOR** se usan muchísimo para implementar **circuitos aritméticos** (como sumadores, por ejemplo)

La puerta **XNOR** es una XOR negada, y se usa para **comparar bits**. Su tabla de verdad es justo la que hemos implementado en el ejemplo 3: comparador de bits

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-19/comb-2x1-7.png)

Ambas puertas, **XOR** y **XNOR** se encuentran disponibles en el menú **Comb/Puertas** de la colección **Academia-Jedi-HW-19.zip**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-19/comb-2x1-8.png)

## Ejemplo 4: Puerta XOR con tablas de verdad

Como ejemplo implementaremos una **puerta XOR** usando la **tabla de verdad** (en vez del propio componente). El circuito es exactamente igual que el ejemplo 3, pero con diferentes valores aplicados a su tabla de verdad

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-19/comb-2x1-9.png)

Lo **cargamos** y lo **probamos**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-19/comb-2x1-10.gif)

Efectivamente es una puerta XOR. Cuando no hay ningún pulsador apretado, el LED0 está apagado. Y también si los dos están apretados a la vez. Sólo en el caso de que haya uno, y sólo uno de los pulsadores apretados, se enciende el LED0

# Circuitos combinacionales de 3 entradas y 1 salida

Los circuitos combinaciones de 3 entradas se definen mediante **tablas de verdad de 8 filas**, ya que hay 8 posibles **combinaciones** de sus entradas

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-19/comb-3x1-1.png)

## Ejemplo 5: Multiplexor de 2 a 1 con tabla de verdad

El multiplexor 2:1 que ya conocemos es un **circuito combinacional** de 3 entradas y una salida. Las entradas son el **canal 1** (*i1*), el **canal 0** (*i0*) y la **selección** (*Sel*). Como es combinacional, lo podemos construir mediante su tabla de verdad

Partimos de este **circuito de ejemplo**, que también conocemos, que hace parpadear el **LED0** a diferentes frecuencias, según el valor del pulsador **SW1**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-19/comb-3x1-2.png)

La **tabla de verdad** de este multiplexor es la siguiente

| Fila | i1  |  i0  | Sel | Salida |
|------|-----|------|-----|--------|
|  0   |  0  |   0  |  0  |    0   |
|  1   |  0  |   0  |  1  |    0   |
|  2   |  0  |   1  |  0  |    1   |
|  3   |  0  |   1  |  1  |    0   |
|  4   |  1  |   0  |  0  |    0   |
|  5   |  1  |   0  |  1  |    1   |
|  6   |  1  |   1  |  0  |    1   |
|  7   |  1  |   1  |  1  |    1   |

Ahora ya podemos implementar el ejemplo anterior usando la **tabla** que encontramos en **Comb/Tablas/tabla-3-1**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-19/comb-3x1-3.png)

**Cargamos** y **probamos**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-19/comb-3x1-4.gif)

Al apretar el pulsador **SW1**, la frecuencia de parpadeo del LED0 cambia. **¡Nuestro multiplexor hecho con tablas de verdad está funcionando!**

# Circuitos combinacionales de 4 entradas y 1 salida

Los circuitos combinaciones de 4 entradas se definen mediante **tablas de verdad de 16 filas**, ya que hay 16 posibles **combinaciones** de sus entradas

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-19/comb-4x1-1.png)

## Ejemplo 6: Comparador de números de 2 bits

Los **comparadores** con unos circuitos muy usados en electrónica digital. Nos permiten generar eventos cuando dos números son iguales, establecer umbrales, activación de zonas de memoria, detección de caracteres, limitación de contadores...

En este ejemplo haremos un **comparador muy sencillo**, para números de bits, basado en **tablas de verdad**. Utilizaremos **4 interruptores externos**, divididos en 2 grupos de 2, para representar la entrada de los 2 números de 2 bits. Cuando ambos números son iguales, se enciende un LED externo. El montaje es el siguiente:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-19/comb-4x1-2.jpg)

La **tabla de verdad** la creamos a partir de la **definición de comparador**. La salida sólo será uno si los dos bits del primer número (i3, i2) son iguales a los del segundo (i1,i0), en el resto de casos será 0

| Fila | i3     | i2     | i1     | i0     | Salida |
|------|--------|--------|--------|--------|--------|
|  0   |  **0** | **0**  |  **0** |  **0** | **1**  |
|  1   |  0     | 0      |  0     |  1     |   0    |
|  2   |  0     | 0      |  1     |  0     |   0    |
|  3   |  0     | 0      |  1     |  1     |   0    |



TODO

* Ejercicio 3: Detector de paridad de números de 4 bits

# Ejercicios propuestos (X BitPoints)

Ver los detalles de los ejercicios y las **entregas** en el menú **Archivos/Ejemplos/2-Ejercicios** de la colección de este tutorial

**Resumen**:

* **Ejercicio 1** (Total **5 Bitpoints**): Franky en modo defensivo

Diseñar un **circuito combinacional**, de dos entradas y una salida, mediante su **tabla de verdad**, para controlar la posición del cuello de Franky con dos **sensores de infrarrojos**: izquierdo y derecho. Cuando ningún sensor esté activado, o sólo lo esté el izquierdo, Franky mirará hacia la izquierda. Cuando el sensor derecho está activado, o ambos (izquierdo y derecho), Franky mirará hacia la derecha

* **Ejercicio 2** (Total **5 Bitpoints**): Apertura de caja fuerte

Diseñar un **circuito combinacional**, mediante su **tabla de verdad**, para abrir la puerta de una caja fuerte cuando se introducen los códigos correctos. Se usarán 3 interruptores externos para introducir la clave. Cuando esta clave sea **101** ó **011** se moverá un servo a la otra posición, simulando la apertura de la caja

* **Ejercicio 3** (Total **x Bitpoints**): 

* **Ejercicio 4** (**3 Bitpoints**). Ejercicio Libre. Premiar la creatividad. **Entregar** por redes sociales o github: Pantallazos, enlaces, vídeos, etc...

# Ejercicios entregados

## Primero

### Ejercicio 1
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 2
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 3
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 4
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()


## Segundo

### Ejercicio 1
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 2
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 3
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 4
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

## Tercero

### Ejercicio 1
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 2
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 3
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 4
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



