![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/Portada/Tut-22-portada.png)

# Vídeo

[![Click to see the youtube video](http://img.youtube.com/vi/JezVCMyrYw0/0.jpg)](https://www.youtube.com/watch?v=JezVCMyrYw0&index=22&list=PLmnz0JqIMEzXaeYVzf2TfTzRekPIVoljw)

Haz click en la imagen para ver el **vídeo en Youtube**

# Descripción

Aprenderemos a construir **circuitos combinacionales de varias salidas**, y veremos de ejemplo de manejo del robot **icebot** con los **pulsadores**, así como la reproducción de secuencias en los **LEDs**. Para crear bloques combinacionales a partir de **tablas de verdad**, con las entradas y salidas que queramos, utilizaremos la **Fábrica de bloques** de Icestudio (IceFactory)

# Colección

[Academia-Jedi-HW-22.zip](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/Collection/Academia-Jedi-HW-22.zip): Colección para este tutorial. Descargar e instalar 

# Contenido

* [Introducción](#introducci%C3%B3n)
* [Controlador de movimiento para el Icebot](#controlador-de-movimientos-para-el-icebot)
  * [Icemove-4](#icemove4)
    * [Ejemplo 1: Probando el icemove-4](#ejemplo-1-probando-el-icemove-4)
    * [Implementación del bloque](#implementaci%C3%B3n-del-bloque)
  * [Icemove-9](#icemove-9)
    * [Ejemplo 2: Probando el icemove-9](#ejemplo-2-probando-el-icemove-9)
    * [Implementación del bloque](#implementaci%C3%B3n-del-bloque-1)
* [Circuitos combinacionales con 1 entrada](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-22:-Circuitos-combinacionales-con-varias-salidas#circuitos-combinacionales-con-1-entrada)
  * [Salidas de 2 bits](#salidas-de-2-bits)
    * [Ejemplo 3: LEDs alternantes](#ejemplo-3-leds-alternantes)
    * [Ejemplo 4: Parpadeo simultáneo de dos LEDs](#ejemplo-4-parpadeo-simult%C3%A1neo-de-dos-leds)
    * [Ejemplo 5: Icebot: Adelante - Stop](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-22:-Circuitos-combinacionales-con-varias-salidas#ejemplo-5-icebot-adelante---stop)
    * [Ejemplo 6: Icebot: Adelante - derecha](#ejemplo-6-icebot-adelante---derecha)
  * [Salidas de 4 bits](#salidas-de-4-bits)
    * [Ejemplo 7: Secuencia de dos estados en 4 LEDs](#ejemplo-7-secuencia-de-dos-estados-en-4-leds)
    * [Ejemplo 8: Dos secuencias en paralelo en los LEDs](#ejemplo-8-dos-secuencias-en-paralelo-en-los-leds)
  * [Salidas de 8 bits](#salidas-de-8-bits)
    * [Ejemplo 9: Secuencia de dos estados en los 8 LEDs](#ejemplo-9-secuencia-de-dos-estados-en-los-8-leds)
* [Circuitos combinacionales con 2 entradas](#circuitos-combinacionales-con-2-entradas)
  * [Ejemplo 11: Movimiento del icebot con 2 pulsadores](#ejemplo-11-movimiento-del-icebot-con-2-pulsadores)
  * [Ejemplo 12: Movimiento del Icebot con 2 pulsadores (II)](#ejemplo-12-movimiento-del-icebot-con-2-pulsadores-ii)
  * [Secuencia de 4 estados en los 8 LEDs](#ejemplo-13-secuencia-de-4-estados-en-los-8-leds)
* [Decodificador de 3 a 8](#decodificador-de-3-a-8)
* [Generación automática de Tablas: IceFactory](#generaci%C3%B3n-autom%C3%A1tica-de-tablas-icefactory)
  * [Creando tu bloque-tabla desde la iceFactory](#creando-tu-bloque-tabla-desde-la-icefactory)
  * [Usando la fábrica sin conexión a Internet](#usando-la-f%C3%A1brica-sin-conexi%C3%B3n-a-internet)
* [Ejercicios propuestos (20 Bitpoints)](#ejercicios-propuestos-20-bitpoints)
* [Ejercicios entregados](#ejercicios-entregados)
  * [Federico Coca (fgcoca)](#federico-coca-fgcoca)
* [Autor](#autor)
* [Licencia](#licencia)
* [Enlaces](#enlaces)
* [Preguntas frecuentes](#preguntas-frecuentes)

# Introducción

En el [tutorial 20](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-20:-Buses-y-n%C3%BAmeros) introdujimos los **buses** y cómo con ellos **agrupamos** los bits y pensamos en **números**. Esto facilita mucho las cosas, y nos permite hacer **circuitos más avanzados**.

Retomaremos los **circuitos combinacionales**, comenzados en el [tutorial 19](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-19:-Circuitos-combinacionales), donde tenían un único bit de salida. Ahora los mezclaremos con **buses** para aprender a hacer **circuitos combinaciones con varias salidas**

El **esquema general** de los **circuitos combinacionales** se muestra en esta figura:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/Intro-01.png)

Hay un **número de entrada**, de **N bits**, y otro de **salida**, de **M bits**. El circuito combinacional **manipula** los bits, convirtiendo el número de entrada en el número de salida. Pero **NO almacena** ningún tipo de información. 

Para practicar, haremos circuitos de **ejemplo** que manejen los **LEDs**, haciendo **secuencias básicas**, y retomaremos el [robot Icebot](https://github.com/Obijuan/icebot/wiki) que vimos en el [tutorial 15](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/VIDEO-15:-Servos-de-rotaci%C3%B3n-continua): lo primero será crear varios **bloques controladores** del Icebot, con  buses de entrada de 2 y 4 bits

# Controlador de movimientos para el Icebot

Para mover el Icebot, en vez de "pensar en bits", utilizaremos **códigos**. Cada código representa un **movimiento**. Utilizaremos los bloques **icemove4** y **icemove16**, uno que permite hacer 4 movimientos y el otro 16. Estos controladores los necesitaremos para el diseño de nuestros circuitos combinacionales de control del icebot

## Icemove4

El controlador **icemove4** tiene un **puerto de entrada de 2 bits**, por el que se introduce el **código de movimiento**. Como salidas tiene dos bits independietes, cada uno para controlar uno de los motores

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/icemove4-1.png)

El **código de los movimientos** se muestra en la siguiente **tabla**. Los 4 movimientos implementados en este controlador son: **Parado**, **adelante**, **giro derecha** (en arco) y **giro izquierda** (en arco)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/icemove4-2.png)

El bloque **icemove4** está disponible en la **colección 22** de la Academia Jedi, en el menú: **Varios/Icebot/icemove4**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/icemove4-3.gif)

### Ejemplo 1: Probando el icemove-4

Para probar este controlador, utilizaremos **dos interruptores externos** por los que introduciremos el **código del movimiento** (en binario). Situaremos el Icebot sobre un **soporte** para que las ruedas estén levantadas y no se pueda desplazar el robot. Así las pruebas son **más sencillas**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/icemove4-5.jpg)

En este **vídeo de Youtube** se pueden ver las **pruebas**, y cómo cambia el movimiento al introducir los diferentes **códigos binarios** con los **interruptores** (Haz click en la imagen para ver el vídeo)

[![Click to see the youtube video](http://img.youtube.com/vi/2LXvQCOBw6Y/0.jpg)](https://www.youtube.com/watch?v=2LXvQCOBw6Y)

Este es el **circuito de pruebas**. El código de movimiento se muestra además por dos LEDs

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/icemove4-6.png)

### Implementación del bloque 

El bloque **icemove4** está formado por los dos bloques **motorbit**, cuyos **sentidos de giro** están fijados a 1 y 0, de manera que ambos **giran hacia adelante** cuando se activan. El código de entrada de 2 bits se corresponde con los 2 bits de activación, para los motores derecho e izquierdo

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/icemove4-7.png)

## Icemove-9

El controlador **icemove9** permite realizar los **9 movimientos** del Icebot (todos los posibles con los controladores motorbit). Tiene un **puerto de entrada de 4 bits**, por el que se introduce el **código de movimiento**. Tiene 2 salidas para controlar los dos motores

El bloque es **igual** al del icemove4, pero con **4 bits de entrada** en vez de 2

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/icemove9-1.png)

La **tabla de movimientos**, con sus códigos asociados se muestra a continuación. Hay movimientos que se consiguen con códigos diferentes. Así, por ejemplo, enviando cualquier de los códigos 0,1,2 ó 3, el robot estará parado

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/icemove9-2.png)

### Ejemplo 2: Probando el icemove-9

Las pruebas del **icemove9** son iguales que las del icemove4 pero usando **4 interruptores externos**. El **montaje** es el siguiente:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/icemove9-3.jpg)

Y este es el **circuito de pruebas**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/icemove9-4.png)

### Implementación del bloque

La **implementación** del bloque es directa. Los **4 bits del bus de entrada** se separan en **cables**. Los dos de **mayor peso** se conectan con los **bits de activación** (on) de las ruedas derecha e izquierda, y los dos de **menor peso** con las **entradas de dirección** (dir)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/icemove9-5.png)

# Circuitos combinacionales con 1 entrada

Empezaremos a diseñar circuitos combinaciones de **varias salidas**, desde lo más sencillo: los que tienen sólo **una entrada**. Haremos ejemplos de circuitos con salidas de **2**, **4** y **8 bits**

Las **tablas de una entrada** que usaremos en este tutorial se encuentran en el menú **Comb/Tablas/Tablas-1-input/**, de la colección **Academia-Jedi-HW-22.zip**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/comb-2-1-02.png)

## Salidas de 2 bits

Los **circuitos combinacionales** de **1 entrada** y **dos salidas** tienen **2 filas**. En la izquierda se coloca el **número de fila**: 0 ó 1, y en la derecha el **número de 2 bits** que queremos que salga. En las tablas de Icestudio, este número lo expresaremos siempre con **dígitos hexadecimales**. Aunque con números de 2 bits, los dígitos decimales y hexadecimales **coinciden** (ya que sólo tenemos los números 0, 1, 2 y 3)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/comb-2-1-01.png)

Las constantes **X**, **Y** representan los **números de dos bits** que se obtienen en la **salida**. Al ser de dos bits, sólo pueden valer **0**, **1**, **2** ó **3**. El funcionamiento es muy sencillo: Cuando se recibe un **0** por la entrada, por la salida sale **X**. Cuando se recibe un **1**, sale **Y**

**Practicaremos** con algunos ejemplos muy sencillos

### Ejemplo 3: LEDs alternantes

Comenzamos con el circuito que ya conocemos de hacer parpadear **dos LEDs** de forma **alternada**: cuando uno está encendido el otro está apagado, y viceversa. Los números de salida son: 1 y 2, que en binario (de 2 bits) se escriben: **01** y **10**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/Ejemplo3-01.png)

Lo **cargamos** y lo **probamos**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/Ejemplo3-02.gif)

### Ejemplo 4: Parpadeo simultáneo de dos LEDs

Partiendo del ejemplo anterior, si ahora queremos que los **LEDs parpadeen de otra forma**, por ejemplo simultáneamente, sólo hay que cambiar los valores de la tabla de verdad, manteniendo **la misma estructura** del circuito

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/Ejemplo4-01.png)

Colocamos los números de salida **0** (00) y **3** (11), por lo que los dos LEDs estarán siempre en el **mismo estado**. Lo **cargamos** y lo **probamos** en la placa:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/Ejemplo4-02.gif)

Además, en este ejemplo hemos añadido **comentarios** en la tabla. Usando los caracteres // añadimos comentarios a los números de salida. Estos comentarios se renderizan en **color verde**, para diferenciarlos de los valores de la tabla (en azul). Los números de fila están en negro

### Ejemplo 5: Icebot adelante - stop

En este ejemplo mostraremos un circuito que hace que el **robot Icebot** esté **parado** o se mueva hacia **adelante** según el estado de un **pulsador externo**. Utilizaremos el controlador **icemove4**, presentado en los apartados anteriores.  Utilizaremos una **tabla de dos entradas** y **una salida**, que almacenará el **código de movimiento** asociado a la pulsación o no del botón. 

Para que el robot esté **parado**, hay que enviar el **código 0** (00), y para **avanzar** el **código 3** (11). El **circuito** es el siguiente:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/Ejemplo5-01.png)

Lo **cargamos** y lo **probamos** en el Icebot. En este **vídeo de youtube** se muestra su funcionamiento (pulsar en la imagen para verlo)

[![Click to see the youtube video](http://img.youtube.com/vi/nWfF1Lpiolo/0.jpg)](https://www.youtube.com/watch?v=nWfF1Lpiolo)

Sólo cuando se aprieta el pulsador, el robot avanza 

### Ejemplo 6: Icebot: Adelante - derecha 

En este ejemplo **cambiaremos la secuencia**, para hacer que **avance** cuando **no** se aprieta el **pulsador**, y que **gire a la derecha** en arco cuando se pulsa. Vemos que el circuito es exactamente **el mismo**, pero con los valores de la tabla **actualizados**. Ahora son **3** (11) y **1** (01), en vez de 0 y 3

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/Ejemplo6-01.png)

**Actualizamos** los valores y **cargamos** el circuito para **probarlo**. Comprobamos que efectivamente su comportamiento reactivo se ha modificado. En este **vídeo de youtube** se puede ver el nuevo comportamiento

[![Click to see the youtube video](http://img.youtube.com/vi/buo6BuwAR3o/0.jpg)](https://www.youtube.com/watch?v=buo6BuwAR3o)

## Salidas de 4 bits

Los **circuitos combinacionales** de **1 entrada** y **cuatro salidas** tienen **2 filas**. En la derecha está el **número de 4 bits** que queremos que salga. Este número debe estar en **hexadecimal**, en las tablas de Icestudio. Como es de **4 bits**, se representa utilizando sólo **1 dígito hexadecimal**: 0,1,2,3,4,5,6,7,8,9,A,B,C,D,E y F

La tabla se encuentra en el menú **Comb/Tablas/Tablas-1-input/Tabla-1-4**

### Ejemplo 7: Secuencia de dos estados en 4 LEDs

En este primer ejemplo generamos una **secuencia** de **2 estados** en los **4 LEDs** de menor peso: 3,2,1 y 0 de la Icezum Alhambra, enviando alternativamente los números 12 y 3, que en **hexadecimal** son **C** y **3**, y en binario **1100** y **0011**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/comb-4-1-01.png)

Lo **cargamos** y lo **probamos**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/Ejemplo7-02.gif)

### Ejemplo 8: Dos secuencias en paralelo en los LEDs

Cambiando los valores de la tabla, conseguimos otra secuencia, sin tener que modificar la estructura del circuito. En este ejemplo añadimos otra secuencia diferente en los **LEDs de mayor peso**: 7,6,5,4. Se envían los números 5 y 10, que en hexadecimal son **5** y **A**, y en binario **0101** y **1010**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/Ejemplo8-01.png)

Las dos secuencias se realizan en **paralelo**. Una sobre los 4 LEDs de **mayor peso** y la otra en los 4 LEDs de **menor peso**. Lo **cargamos** y lo **probamos**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/Ejemplo8-02.gif)

Aquí se están reproduciendo a la misma frecuencia (1Hz), pero al ser independientes podríamos ejecutarlas con frecuencias diferentes

## Salidas de 8 bits

Para finalizar con los circuitos combinaciones con una entrada, veremos ejemplos de circuitos con **una entrada** y **8 salidas**. En este caso en la tabla hay que colocar **números hexadecimales** entre **0** y **FF** (255), es decir, con **2 dígitos hexadecimales**

### Ejemplo 9: Secuencia de dos estados en los 8 LEDs

En este ejemplo generamos la famosa **secuencia** de prueba **0x55** - **0xAA** que alterna los bits pares con los impares en los **8 LEDs**, a una frecuencia de 2Hz

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/Ejemplo9-01.png)

Lo **cargamos** y lo **probamos**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/Ejemplo9-02.gif)

### Ejemplo 10: Dos secuencias de dos estados en 8 LEDs

Añadimos otra **secuencia** de 2 estados, para los **8 LEDs** y la combinamos con la anterior mediante un **multiplexor de 2 a 1**. Usando un **interruptor externo** seleccionamos entre una y otra. En la nueva secuencia se envían los números **0F** (00001111) y **F0** (11110000) para iluminar alternativamente los 4 leds de menor peso y los 4 de mayor, a la frecuencia de **1 Hz**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/Ejemplo10-1.png)

Lo **cargamos** y lo **probamos**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/Ejemplo10-2.gif)

# Circuitos combinacionales con 2 entradas

Los circuitos combinacionales con **2 entradas** se definen mediante una tabla de verdad de **4 filas**. Son muy útiles para la implementación de **comportamientos reactivos** en **robots** como seguir la línea negra, seguir objetos, etc. Veremos **tres ejemplos** de circuitos combinaciones con 2 entradas y diferentes salidas: 2, 4 y 8 bits. 

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/comb-2-inputs.png)

### Ejemplo 11: Movimiento del Icebot con 2 pulsadores

Diseñaremos un circuito combinacional que nos permita **controlar el icebot** mediante **dos pulsadores externos**. Uno lo usaremos para que **gire hacia la derecha** (en arco), el otro a la **izquierda** (también en arco) y al pulsar los dos que vaya hacia **adelante**. Cuando no se aprietan los pulsadores el robot estará **parado**

Utilizaremos el controlador **icemove4**, que recibe códigos de movimiento de 2 bits. Los dos **pulsadores externos** se usan como entradas del circuito combinacional, y su salida de 2 bits se conecta al icemove4. En la **tabla** se almacenan los **códigos de los movimientos** a realizar según la combinación de pulsadores apretados.

El circuito es el siguiente:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/Ejemplo11-1.png)

Da la casualidad que los códigos de los movimientos a realizar coinciden con el número de fila, pero es una mera **coicidencia**. Cargamos el circuito y lo probamos. En este **vídeo de youtube** se muestra el funcionamiento

[![Click to see the youtube video](http://img.youtube.com/vi/RzkW_pF2-KU/0.jpg)](https://www.youtube.com/watch?v=RzkW_pF2-KU)

Si querremos asignar una combinación de movimientos diferentes a los pulsadores, sólo hay que cambiar el **contenido de la tabla**, manteniendo la misma estructura del circuito

### Ejemplo 12: Movimiento del Icebot con 2 pulsadores (II)

Modificamos el ejemplo anterior para usar el controlar **icemove9**, que permite nuevos movimientos. Ahora el circuito combinacional tiene **2 entradas** y **4 salidas**. Los movimientos que queremos son: **adelante**, cuando no se aprieta ningún pulsador, **atrás**, cuando están apretado ambos, **giro a la derecha** al apretar el pulsador derecha y **giro a la izquierda** al apretar el izquierdo

Los **códigos de movimimiento** que hay que introducir en la tabla, en **hexadecimal** son: E (15), C (12), F (15), y D (14)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/Ejemplo12-1.png)

Lo **cargamos** y lo **probamos**

[![Click to see the youtube video](http://img.youtube.com/vi/E7AeNKPwjvQ/0.jpg)](https://www.youtube.com/watch?v=E7AeNKPwjvQ)

### Ejemplo 13: Secuencia de 4 estados en los 8 LEDs

Como ejemplo de un circuito combinacional de **2 entradas** y **8 salidas** haremos uno que reproduzca una secuencia de **4 estados** en los **8 LEDs**. La secuencia envía los números **0**, **7**, **3F** (63) y **FF** (255) a los leds para se vayan **encendiendo progresivamente**: primero todos apagados, luego 3, luego 6 y finalmente los 8. 

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/Ejemplo13-1.png)

Para recorrer la tabla se utilizan dos **corazones** de **1** y **2 Hz**. Con esto se consigue que se envíen los números 0,1,2 y 3 consecutivamente, y luego se vuelve a empezar (Más adelante en los tutoriales veremos cómo esto se hace más fácilmente usando contadores)

Lo **cargamos** y lo **probamos**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/Ejemplo13-2.gif)

# Decodificador de 3 a 8

Como **ejemplo** de un circuito combinacional de **3 entradas** y **8 salidas**, haremos un **decodificador de 3 a 8**. Los decodificadores se utilizan muchísimo en el diseño de microprocesadores para activar los periféricos o zonas de memoria a partir de una dirección

El decodificador de 3 a 8 tiene una entrada de **3 bits**, por la que se recibe un número entre 0 y 7. La salida tiene **8 bits**. El decodificador activa **una y solo una** de las salidas en función del número de entrada. Su **tabla de verdad** es la siguiente:

| Entrada (3 bits) | Salida (8 bits)     |
|------------------|---------------------|
| 0                | **01** (00000001)   |
| 1                | **02** (00000010)   |
| 2                | **04** (00000100)   |
| 3                | **08** (00001000)   |
| 4                | **10** (00010000)   |
| 5                | **20** (00100000)   |
| 6                | **40** (01000000)   |
| 7                | **80** (10000000)   |

Si nos fijamos en el número de salida en binario, vemos que en todos los casos sólo hay un **bit activado**, y los demás están a 0

Este es el **circuito de prueba** del decodificador. Por las entradas conectados **3 interruptores externos** por los que introducimos el código de entrada. Las salidas se conectan a los **LEDs** de la Icezum Alhambra. 

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/Ejemplo-14-1.png)

Lo **cargamos** y lo **probamos**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/Ejemplo-14-2.gif)

Con los **interruptores** introducimos **todos los números**, desde el 0 hasta el 7 y vemos cómo se encienden consecutivamente **todos los LEDs**, del 0 al 7, uno cada vez

# Generación automática de tablas: IceFactory

Los **bloque de icestudio** que nos permiten implementar **circuitos combinacionales** mediante **tablas de verdad**, que hemos usado en este tutorial, están disponibles en el menú **Comb/tablas**. Sin embargo, sólo están disponibles unos pocos de todos los que podríamos necesitar. **¿Y si necesitamos hacer una tabla que no se encuentra en esta colección?**. La podemos crear de manera muy sencilla a través de la **Fábrica de bloques de Icestudio**: [IceFactory](https://obijuan.github.io/iceFactory/index.html)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/IceFactory-01.png)

## Creando tu bloque-tabla desde la IceFactory

Los **pasos** para generar tu **bloque-tabla**, del tamaño que quieras, son los siguientes:

*  Accede a la [Página principal de la Fábrica](https://obijuan.github.io/iceFactory/index.html)
* En la sección **Generadores**, pincha en el **icono de la tabla**. Esto te llevará a la **página web** de la **generación de tablas**. También puedes acceder directamente a través de este enlace: [Icetables](https://obijuan.github.io/iceFactory/icetable/icetable.html)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/IceFactory-02.png)

* Introduce el **número** de **bits de entrada** y **bits de salida** de tu circuito. Por defecto los valores que hay son 2 y 4. Modifícalos para introducir los de tu circuito

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/IceFactory-03.png)

* **Pulsa** en el botón azul de **generar**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/IceFactory-04.png)

* Aparecerá un **enlace nuevo**, con el nombre de la tabla generada, debajo del texto que pone **Paso 3**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/IceFactory-05.png)

* **Pincha** en él para **grabar** el bloque en tu ordenador

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/IceFactory-06.png)

* **Importa** el bloque en **Icestudio** desde la opción **Archivo/Añadir como bloque**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/IceFactory-07.png)

**¡Listo!** ¡Ya tienes tu tabla lista para usarla con tus circuitos! :-)

El **proceso completo** se resume en esta **animación**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/IceFactory-08.gif)

## Usando la fábrica sin conexión a internet

La fábrica de bloques está implementada en **Javascript**, y usa una **interfaz web** para la generación de los bloques. Se puede ejecutar sin problemas desde nuestro **navegador** en **local**, sin necesidad de estar conectados a internet

Para **probarlo en local** hay que seguir los siguientes **pasos**:

* **Descargar** el [repositorio IceFactory de github](https://github.com/Obijuan/iceFactory): bien clonándolo o bien bajando el fichero .zip y descomprimiéndolo

* **Entrar en la carpeta iceFactory** (iceFactory-master si lo hemos descomprimido del .zip)

* Hacer **doble click** en el fichero **index.html** para abrir la fábrica en el **navegador en local**

* **Generar los bloques** de la misma forma que se ha mostrado en el **apartado anterior**, pero todo se hace en local, sin conectarse a internet

En esta **animación** se resume el proceso

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/IceFactory-09.gif)

# Ejercicios propuestos (20 BitPoints)

Ver los detalles de los ejercicios y las **entregas** en el menú **Archivos/Ejemplos/2-Ejercicios** de la colección de este tutorial

**Resumen**:

* **Ejercicio 22.1** (Total **5 Bitpoints**): **Secuencia de 4 estados en los LEDs**

Hacer un circuito que muestre por los LEDs una **secuencia de 4 estados** en la que primero se encienden los LEDS 0,1 y 2. Despúes los 3 y 4, luego los 5,6,7 y por último nuevamente los LEDs 3 y 4. El proceso se repite a una frecuencia de 2Hz. Utilizar un circuito combinacional de **2 entradas** y **8 salidas**

La secuencia resultante tiene que ser como la mostrada en [Este vídeo de Youtube](https://www.youtube.com/watch?v=klusAMMd7Ac)

[![Click to see the youtube video](http://img.youtube.com/vi/klusAMMd7Ac/0.jpg)](https://www.youtube.com/watch?v=klusAMMd7Ac)

* **Ejercicio 22.2** (Total **5 Bitpoints**):  **Icebot San Fermín**

Hacer un circuito que implemente el comportamiento reactivo de **embestir** en el Icebot. Se conectan dos sensores de **Infrarrojos** para detectar el objeto delante del icebot. El comportamiento de embestir se define mediante la siguiente **tabla de verdad**:

| IR izquierdo | IR derecho  | Movimiento del icebot  |
|--------------|-------------|------------------------|
| No detecta  |  No detecta  |  Parado                |
| No detecta  |  Detecta     |  Giro izquierda (Arco) |
| Detecta     |  No detecta  |  Giro derecha (arco)   |
| Detecta     |  Detecta     |  Adelante              |

Los valores a introducir en la tabla dependen de los sensores IR utilizados. Algunos devuelven 1 al detectar un objeto delante y 0 cuando NO. Otros se comportan al revés (lógica negativa)

Utilizar el controlador **Icemove4**. Y un **circuito combinacional de 2 entradas y 2 salidas**  

El **comportamiento** del icebot se muestra en [Este vídeo de Youtube](https://www.youtube.com/watch?v=Wr5cy3I2vWA)

[![Click to see the youtube video](http://img.youtube.com/vi/Wr5cy3I2vWA/0.jpg)](https://www.youtube.com/watch?v=Wr5cy3I2vWA)

* **Ejercicio 22.3** (Total **5 Bitpoints**):  **Control manual del Icebot**

Diseñar un circuito de control de Icebot, que tenga **3 entradas**: una será un **interruptor**, y las otras **dos pulsadores**. El interruptor selecciona el **modo** de movimiento del icebot: Directo e inverso.  

En el **modo directo** controlamos el icebot con los dos pulsadores. Con uno **gira a la derecha**, con otro a la **izquierda**, y si se aprietan ambos se mueve hacia **adelante**

En el **modo inverso** los pulsadores se usan con otro propósito. Con uno el robot hará un **arco atrás-izquierda**, con el otro un **arco atrás-derecha** y cuando se pulsan los dos irá hacia **atrás**

Hay que usar un circuito combinacional con **3 entradas y 4 salidas**, y el controlador **icemove9**. La **tabl**a no está en la colección por lo que habrá que generarla en la **IceFactory**

El **comportamiento** del icebot se muestra en [Este vídeo de Youtube](https://www.youtube.com/watch?v=mT3gG4sRomU)

[![Click to see the youtube video](http://img.youtube.com/vi/mT3gG4sRomU/0.jpg)](https://www.youtube.com/watch?v=mT3gG4sRomU)

* **Ejercicio 22.4** (**5 Bitpoints**). Ejercicio Libre. Premiar la creatividad. **Entregar** por redes sociales o github: Pantallazos, enlaces, vídeos, etc...

# Ejercicios entregados

## Federico coca (fgcoca)

### Ejercicio 22.1

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-22/fgcoca/Ejercicio-1/Ejercicio22_1%20%E2%94%80%20P.png)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/TyTgp5TBxMI/0.jpg)](https://www.youtube.com/watch?v=TyTgp5TBxMI)

### Ejercicio 22.2
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-22/fgcoca/Ejercicio-2/-Ejercicio22_2%20%E2%94%80%20P.png)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/ajGbk1BbypQ/0.jpg)](https://www.youtube.com/watch?v=ajGbk1BbypQ)

### Ejercicio 22.3
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-22/fgcoca/Ejercicio-3/Ejercicio22_3%20%E2%94%80%20P.png)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/m2Iac755hpo/0.jpg)](https://www.youtube.com/watch?v=m2Iac755hpo)

## Segundo

### Ejercicio 22.1
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 22.2
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 22.3
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 22.4
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

## Tercero

### Ejercicio 22.1
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 22.2
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 22.3
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 22.4
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




