![]()

# Vídeo

(TODO)

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

Haz click en la imagen para ver el **vídeo en Youtube**

# Descripción

(TODO)

# Colección

**Academia-Jedi-HW-28.zip**: Colección para este tutorial. Descargar e instalar 

# Contenido

* [Introducción](#introducci%C3%B3n)
* [Detectores de flancos](#detectores-de-flancos)
* [Biestables de cambio (T)](#biestables-de-cambio-t)
  * [Ejemplo 1: Encendido y apagado con pulsador](#ejemplo-1-encendido-y-apagado-con-pulsador)
  * [Pulsador de cambio](#pulsador-de-cambio)
  * [Ejemplo 2: Nivel 1 del Circuit Scramble, en físico](#ejemplo-2-nivel-1-del-circuit-scramble-en-f%C3%ADsico)
  * [Ejemplo 3: Divisor de frecuencia ](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-28:-Biestables-de-datos-y-cambio#ejemplo-3-divisor-de-frecuencia)
  * [Ejemplo 4: Encadenamiento de biestables de cambio](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-28:-Biestables-de-datos-y-cambio#ejemplo-4-encadenamiento-de-biestables-de-cambio)
* [Biestables de datos](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-28:-Biestables-de-datos-y-cambio#biestables-de-datos)
  * [Ejemplo 5-1: Capturando un 1](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-28:-Biestables-de-datos-y-cambio#ejemplo-5-1-capturando-un-1)
  * [Ejemplo 5-2: Capturando un 0](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-28:-Biestables-de-datos-y-cambio#ejemplo-5-2-capturando-un-0)
  * [Ejemplo 6: Capturando un dato genérico](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-28:-Biestables-de-datos-y-cambio#ejemplo-6-capturando-un-dato-gen%C3%A9rico)
  * [Biestables D en paralelo](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-28:-Biestables-de-datos-y-cambio#biestables-d-en-paralelo)
    * [Ejemplo 7: Capturando un dato de 3 bits](#ejemplo-7-capturando-un-dato-de-3-bits)
* [Desplazamiento de bits](#desplazamiento-de-bits)
  * [Desplazamientos básicos](#desplazamientos-b%C3%A1sicos)
    * [Ejemplo 8: Desplazamiento de bits con el pulsador](#ejemplo-8-desplazamiento-de-bits-con-el-pulsador)
    * [Ejemplo 9: Conexión en anillo](#ejemplo-9-conexi%C3%B3n-en-anillo)
  * [Multiplicaciones por 2](#multiplicaciones-por-2)
    * [Ejemplo 10: Multiplicación por 2 básica](#ejemplo-10-multiplicaci%C3%B3n-por-2-b%C3%A1sica)
  * [Conversión serie-paralelo](#conversi%C3%B3n-serie-paralelo)
    * [Ejemplo 11: Conversión serie-paralelo de un número de 3 bits](#ejemplo-11-conversi%C3%B3n-serie-paralelo-de-un-n%C3%BAmero-de-3-bits)
  * [Conversión paralelo-serie](#conversi%C3%B3n-paralelo-serie)
    * [Ejemplo 2: Conversión a serie de un número de 3 bits](#ejemplo-12-conversi%C3%B3n-a-serie-de-un-n%C3%BAmero-de-3-bits)
* [Ejercicios propuestos (20 Bitpoints)](#ejercicios-propuestos-20-bitpoints)
* [Ejercicios entregados](#ejercicios-entregados)
* [Autor](#autor)
* [Licencia](#licencia)
* [Enlaces](#enlaces)
* [Preguntas frecuentes](#preguntas-frecuentes)

# Introducción

Los **biestables** nos permiten **almacenar** un bit, que usaremos con diferentes propósitos. Unos bits son para representar el **estado** de nuestro circuito. Otros serán para representar **datos**. Los tres biestables que usaremos son: **D**, **T** y **RS**. Usaremos estos **bloques en Icestudio**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/Intro-01.png)

Aunque todos se pueden usar para ambos propósitos, los **biestables RS** los solemos usar principalmente para **almacenar el estado** del circuito y **los biestables D** para almacenar **datos**. En este tutorial nos centraremos en los **biestables de Cambio** (T) y en los de **Datos** (D)

Los tres biestables tiene un **parámetro** para especificar su **valor inicial** (cero o uno). También tienen en común que sólo tienen **una única salida**: el valor del bit que almacenan, y a todos les llega el **reloj del sistema**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/Intro-02.png)

# Detectores de flancos

La **información** almacenada en los **biestables** va cambiando durante el funcionamiento del circuito. Mediante los **detectores de flancos** podemos **generar tics** cuando se produzcan estos cambios. Bien cuando un bit cambie de **cero a uno** (flanco de subida) o bien cuando cambie de **uno a cero** (flanco de bajada). Los bloques en **Icestudio** son los siguientes:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/Detector-01.png)

El **funcionamiento** es muy sencillo. Se **transforman** los **flancos en tics**, como se muestra en esta **animación**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/detector-02.gif)


# Biestables de cambio (T)

Los **biestables de cambio**, también conocidos como **biestables tipo T**, **cambian** su valor cada vez que reciben un **tic** por su **entrada T** (toggle). Si inicialmente tiene el **valor 0**, al llegar un tic **cambiará a 1**. Y en el **siguiente tic** volverá otra vez a **0**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/Cambio-01.png)

En esta **animación** se muestra su **funcionamiento**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/Cambio-02.gif)

## Ejemplo 1: Encendido y apagado con pulsador

Utilizaremos un **biestable de cambio** para encender y apagar **un LED** usando un **único pulsador**. Al apretarlo la primera vez el LED se enciende. Al apretarlo la siguiente vez se apagará. El **circuito** es el siguiente:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/Cambio-03.png)

El biestable se encuentra en **Varios/Biestables/Cambio**. El escenario es muy básico: sólo ponemos un **pulsador** y un **LED**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/Cambio-04.png)

**Cargamos** el circuito y lo **probamos**:

[![Click to see the youtube video](http://img.youtube.com/vi/UV7w26jg46I/0.jpg)](https://www.youtube.com/watch?v=UV7w26jg46I)

¿No te recuerda a algo el funcionamiento de este pulsador con luz? ¡Exacto! ¡A los **pulsadores del Circuit Scramble**! ¡Funcionan igual! Una pulsación y se activan. Otra y se apagan

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/Cambio-05.gif)

Si quisiéramos que el **LED** estuviese **encendido inicialmente**, en vez de estar apagado, sólo hay que poner el valor inicial como **parámetro** del biestable T:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/Cambio-06.png)

## Pulsador de cambio

Estos **pulsadores** que se activan al apretar y se desactivan al volver a apretar se denominan **pulsadores de cambio** (Toggle buttons) y se utilizan muchísimo. Por eso tienen su **propio bloque**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/Pulsador-cambio-01.png)

No es más que un **pulsador de tics** en serie con un **Biestable de cambio**, pero al estar en un único bloque los circuitos quedan **más compactos**. Si rehacemos el **ejemplo 1**, en el que se usa el pulsador para encender/apagar un LED, el circuito queda así:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/Pulsador-cambio-02.png)

Este componente se encuentra en **Varios/Pulador/Pulsador-cambio**. Si ahora queremos que **inicialmente** el botón esté **apretado** (y el LED encendido) sólo hay que pasarle como **parámetro** el valor 1:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/Pulsador-cambio-03.png)

## Ejemplo 2: Nivel 1 del Circuit Scramble, en físico

Ahora que ya tenemos el **pulsador de cambio**, podemos hacer una implementación de los niveles del **Circuit Scramble**, pero en **físico** :smiley: Haremos el **nivel 1**. El **circuito** en Icestudio es:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/Cambio-07.png)

Además de los **4 pulsadores**, se han añadido **7 LEDs**, uno por cada uno de los **cables**, para mostrar su estado. Y un **Servo** que se activa cuando se ha **completado** el nivel. El **montaje** es el siguiente

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/Cambio-06.png)

Lo **cargamos** y lo **probamos**. ¡A jugar! :smiley:

[![Click to see the youtube video](http://img.youtube.com/vi/-qt9mZB6Lww/0.jpg)](https://www.youtube.com/watch?v=-qt9mZB6Lww)

Y si **sustituimos** los bloques por otros con los iconos del **Circuit scramble**, mola más :smiley: 

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/Cambio-08.png)

## Ejemplo 3: Divisor de frecuencia

Los **biestbles de cambio** se usan también como **divisores de frecuencia**. En nuestro caso, nos permiten dividir entre dos la frecuencia de una señal compuesta por **tics periódicos**

Partimos de un circuito, que ya conocemos, que hace **parpadear un LED a 1Hz**. El **corazón de tics** genera la **temporización**: se envía un tic cada segundo (1000ms). Mediante un **temporizador** establecemos la **anchura del pulso** a 500ms (aunque nos valdría cualquier otra anchura)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/Cambio-09.png)

Ahora analizamos las **señales**. El **corazón** envía **tics** separados un tiempo de **1000ms**. Al pasar por el **temporiador** se convierten en **pulsos de anchura de 500ms**, pero la frecuencia se mantiene igual:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/Cambio-10.png)

Ahora colocamos en paralelo un **biestable de cambio**, conectado a otro LED para comparar visualmente las señales

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/Cambio-11.png)

Si observamos las señales, a la salida del **biestable T** obtenemos una **señal del doble de periodo** que la de los tics:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/Cambio-12.png)

**Cargamos** el circuito y lo **probamos** para comprobarlo

[![Click to see the youtube video](http://img.youtube.com/vi/SChH5APwpFM/0.jpg)](https://www.youtube.com/watch?v=SChH5APwpFM)

## Ejemplo 4: Encadenamiento de biestables de cambio

Para que el biestable de cambio se comporte como se ha descrito, su **entrada debe ser un tic**. Si lo que se introduce es un **pulso de anchura mayor**, el biestable cambiará de estado tantas veces como tics del sistema ocurran en esa anchura, como se muestra en este ejemplo

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/Cambio-13.png)

La anchura de la señal a la entrada es **mayor de un tic**, por lo que el biestable **cambia varias veces**. Esto es **muy importante** recordarlo. En los ejemplos que usaremos **siempre** enviaremos señales de **1 tic de anchura**

Debido a esto, **NO podemos encadenar biestables T directamente**, ya que por su salida no salen tics. Para lograrlo hay que usar **detectores de flancos**, que emiten un tic cuando llega el flanco indicado. En este ejemplo encadenamos dos biestables T para obtener una señal de frecuencia 4 veces inferior (o un periodo 4 veces mayor).

Si partimos de un **corazón de tics de 1 segundo**, con este circuito obtenemos una **señal de periodo 4 segundos**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/Cambio-14.png)

Lo que está sucenciendo en las **señales intermedias** se muestra en esta **figura**: Los **tics originales** se convierten en una **señal de periodo el doble**. Luego se obtiene una nueva señal que tiene **tics en los flancos de subida**. Finalmente se crea otra de **periodo el doble de la anterior** (y cuatro veces la inicial)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/Cambio-15.png)

Lo **cargamos** y lo **probamos**

[![Click to see the youtube video](http://img.youtube.com/vi/D5te5cxt-7g/0.jpg)](https://www.youtube.com/watch?v=D5te5cxt-7g)

# Biestables de Datos

Los **biestables D** se usan para almacenar **datos**, y retenerlos hasta que lleguen los siguientes. En el bloque de icestudio usamos el icono de una **chincheta** para representar esta idea de **fijar** datos:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/Datos-01.png)

Además del **reloj del sistema**, el biestable D tiene una **entrada de un bit** por donde llega el **dato** a almacenar, 0 ó 1. Este dato está fuera del biestable hasta que se recibe un tic por su **entrada de carga**, que llamamos **tic de captura**. En ese instante el **dato se almacena**, y es visible por su **salida**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/Datos-02.gif)

## Ejemplo 5-1: Capturando un 1

Para ver en la práctica el **funcionamiento del biestable D**, empezamos por un ejemplo muy sencillo, que **captura un bit 1 constante** al apretar un **pulsador**. Una vez capturado, hay que pulsar el **reset de la placa** para volver al estado inicial y repetir el experimento

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/Datos-03.png)

Al **apretar el pulsador** se genera un **tic** que hace que el biestable **capture el 1 de su entrada**. Una vez almacenado, el LED conectado a su salida se **enciende**. En el **montaje** sólo tenemos un **pulsador** y un **LED**

![](https://raw.githubusercontent.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/master/wiki/Tutorial-28/Cambio-04.png)

Lo **cargamos** y lo **probamos**. Si apretamos varias veces el pulsador no ocurre nada: el LED sigue encendido porque se están capturando unos

[![Click to see the youtube video](http://img.youtube.com/vi/ohMgFBgZRlg/0.jpg)](https://www.youtube.com/watch?v=ohMgFBgZRlg)

## Ejemplo 5-2: Capturando un 0

Ahora haremos el ejemplo opuesto: **Capturar un 0**. Utilizaremos el parámetro del biestable para **iniciarlo a 1**. El LED estará encendido. Al apretar el pulsador se captura un 0 y se apaga

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/Datos-04.png)

Lo **cargamos** y lo **probamos**

[![Click to see the youtube video](http://img.youtube.com/vi/o62mK_SpjEI/0.jpg)](https://www.youtube.com/watch?v=o62mK_SpjEI)

## Ejemplo 6: Capturando un dato genérico

Ahora que ya sabemos cómo funciona el **biestable D**, lo usaremos para **capturar los bits** que llegan de un **interruptor externo**. Utilizaremos un **pulsador** para capturar el dato. En el **escenario** tenemos un interruptor, un pulsador y dos LEDs

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/Datos-05.png)

El LED al lado del interruptor nos muestra el **dato a capturar**, y el LED junto al pulsador el **dato capturado**. Al apretar el pulsador se captura el dato (LED amarillo) y se muestra en el LED rojo. El circuito es el siguiente:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/Datos-06.png)

Lo **cargamos** y lo **probamos**. ¡Nuestra primera captura de un dato genérico!

[![Click to see the youtube video](http://img.youtube.com/vi/GJ9FqUe0TTA/0.jpg)](https://www.youtube.com/watch?v=GJ9FqUe0TTA)

## Biestables D en paralelo

Como ya vimos en el [tutorial 20](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-20:-Buses-y-n%C3%BAmeros), en los circuitos trabajamos con datos formados por **varios bits**. Para **almacenar** un **dato de N bits**, necesitamos colocar **N biestables D** en **paralelo**, cada uno almacenando un bit del dato. Se usa una **única señal de carga** que se conecta a la **entrada load de todos los biestables**. De esta forma, para capturar un dato basta con emitir un **tic** por esta señal, que hace que todos los biestables capturen sus bits correspondientes

La **agrupación de biestables en paralelo**, con un **única señal de captura**, se denomina **registro**. En este tutorial nos centraremos en los biestables. Los registros los dejamos para el siguiente

### Ejemplo 7: Capturando un dato de 3 bits

Haremos un ejemplo de captura de un **dato de 3 bits**. El dato proviene de **tres interruptores externos**, y la señal de captura de un **pulsador**.  Cuando se aprieta este botón se **captura el dato** y se muestra en un **display de 7 segmentos**. El escenario es el siguiente:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/Datos-07.png)

El circuito está formado por **tres biestables D en paralelo**, cuyas **entradas de datos** están conectadas a los **interruptores**. Las **entradas de load** de todos están conectadas al **pulsador de captura**. El **dato capturado** se inyecta en un **bus** y se muestra en el **display de 7 segmentos**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/Datos-08.png)

Lo **cargamos** y lo **probamos**. Introducimos los **números en binario** por los interruptores y apretamos el **pulsador**, que funciona como si fuese la **tecla enter**

[![Click to see the youtube video](http://img.youtube.com/vi/DF8t8AawiAo/0.jpg)](https://www.youtube.com/watch?v=DF8t8AawiAo)

# Desplazamiento de Bits

Los **biestables D** nos permiten realizar **desplazamientos de bits**. Esta es una operación importantísima, que usamos para implementar operaciones aritméticas como la **multiplicación** o **división** entre **2**, o la **conversión de serie a paralelo** y paralelo a serie entre otras

## Desplazamientos básicos

Los desplazamientos se realizan mediante el **encadenamiento de Biestables D**, también conocido como **conexión en serie**. Los bits pasan de un biestable al siguiente cuando reciben el **tic de captura**. Hay un **desplazamiento físico** real, de los bits, como se muestra en esta **animación**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/shift-01.gif)

### Ejemplo 8: Desplazamiento de bits con el pulsador

Como ejemplo de **desplazamiento** de bits implementaremos la animación anterior. Cada vez que se apriete un **pulsador** el bit se moverá **una posición a la derecha**. En el **montaje** tenemos el **pulsador** y **tres LEDs**, cada uno conectado a la salida de un **Biestable D**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/shift-02.png)

El circuito está formado por **3 biestables D** encadenados, cuyas salidas se sacan por **LEDs**. Todas sus señales de **load** están unidas y controladas simultáneamente mediante el **pulsador**. El biestable de la izquierda está **inicializado** a **1** y por su entrada de datos le llegan ceros. Los restantes biestables están inicializados a 0 

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/shift-03.png)

Lo **cargamos** y lo **probamos**. El **LED 1** está encendido inicialmente. El dato inicial es **100**. Al apretar el botón se desplaza un bit a la izquierda, obteniéndose el **010**. Al apretar otra vez, el **001** y finalmente el **000**. El '1' se ha desplazado hacia la derecha

[![Click to see the youtube video](http://img.youtube.com/vi/AxTHelRvFn8/0.jpg)](https://www.youtube.com/watch?v=AxTHelRvFn8)

### Ejemplo 9: Conexión en anillo

Igual que ya hicimos con los temporizadores en el [tutorial 26](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-26:-Tiempo,-tics-y-temporizadores#encadenamiento-en-anillo), los **biestables D** los podemos conectar formando **un anillo**, en el que el **último** está conectado con **el primero**. Los datos que están almacenados se van moviendo de un biestable a otro, con cada tic, formando un **bucle físico**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/shift-04.gif)

Para probarlo, **conectaremos** el circuito del **ejemplo** anterior en **anillo**, de manera que el dato que llega al biestable de la izquierda es la salida del último, en lugar de 0 

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/shift-05.png)

Lo **cargamos** y lo **probamos**. Al apretar por tercera vez el pulsador, se regresa al estado inicial, y se vuelve a comenzar

[![Click to see the youtube video](http://img.youtube.com/vi/aEfeunf8DqM/0.jpg)](https://www.youtube.com/watch?v=aEfeunf8DqM)

## Multiplicaciones por 2

En el **sistema de numeración decimal**, el que usamos normalmente, hay una operación que es muy sencilla de hacer: la **multiplicación por 10**. Basta con añadir un cero por la derecha. O lo que sería lo mismo: desplazar el dígito hacia la izquierda: Así, si tenemos el número 3, al multiplicarlo por 10 queda 30

De igual modo, en el **sistema binario**, que es el que usan los circuitos digitales, existe una operación **muy fácil de realizar**: la **multiplicación por 2**. Sólo hay que **desplazar los dígitos** en la dirección de los de mayor peso. Así, si tenemos el número binario **001**, al desplazarlo un bit a la izquierda tenemos: **010** (2), y si lo desplazamos nuevamente tendremos **100** (que es 4)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/shift-07.gif)

La regla es: **Para multiplicar cualquier número binario por dos, sólo hay que desplazarlo un bit a la izquierda, y añadir un cero en la derecha**. Para hacer **divisiones entre 2** es lo mismo, pero desplazando en la dirección opuesta

### Ejemplo 10: Multiplicación por 2 básica

**Implementaremos** un circuito para hacer las multiplicaciones por dos mostradas en la **animación**: partimos del número 1, y al multiplicarlo por 2 obtendremos 2, y al volver a multiplicar obtenemos 4

En el escenario tenemos un **display de 7 segmentos** para ver el resultado en **decimal**, y **tres LEDs** para ver el **número en binario**. Al apretar el **pulsador** se hace una **multiplicación por dos**. En el display inicialmente hay un **1**, al apretar el pulsador aparece un **2** y luego un **4**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/shift-08.png)

El circuito es el mismo que el del ejemplo 8: tres **biestables D encadenados**. El de menor peso está inicializado a **1**. Están conectados a un **display de 7** segmentos para mostrar el número en decimal, y a tres **LEDs** para verlo en binario. Cada vez que se aprieta el pulsador, los bits se desplazan hacia el bit de mayor peso, realizando la multiplicación por 2

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/shift-06.png)

Lo **cargamos** y lo **probamos**. Comprobamos que inicialmente aparece el **1**. Al apretar vemos el **2**, y luego el **4**. Para volver a la **situación inicial** pulsamos el **reset de la placa**

[![Click to see the youtube video](http://img.youtube.com/vi/mszYjCyN4xo/0.jpg)](https://www.youtube.com/watch?v=mszYjCyN4xo)

Si inicializamos los biestables con el valor **011** (3), al apretar obtendremos el **110** (6). Este método nos funciona con cualquier número binario. Sin embargo, su visualización la tenemos limitada por usar sólo un display de 7 segmentos

## Conversión serie-paralelo

En muchos **periféricos** el envío de los bits se hace en **serie**: uno detrás de otro, como en los buses I2C, SPI, comunicaciones serie asíncronas, etc. Para procesarlos en nuestros circuitos necesitamos almacenarlos en paralelo, colocando un bit en cada **biestable D**. Es lo que se denomina **conversión serie-paralelo**.

Una forma de hacerlo es colocando **biestables encadenados** para recibir los **datos en serie**, y luego **biestables D** para su carga en paralelo y almacenamiento. En este animación se muestra un ejemplo de **recepción** de un dato serie de **3 bits**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/Serie-01.gif)

Primero se recibe el número **101**, bit a bit, y se introduce en los biestables serie. Luego esos bits se cargan en paralelo en los otros biestables, cuyas salidas están conectadas al display de 7 segmentos, y permiten ver el númmero recibido en decimal

### Ejemplo 11: Conversión serie-paralelo de un número de 3 bits

Haremos un **circuito** para implementar la animación anterior, en la que se recibe por serie el **número 5** y se muestra en el **display** de 7 segmentos.  El proceso lo haremos "manualmente" mediante pulsadores. En el montaje hay  **tres pulsadores**, **cuatro LEDs** y el **display**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/Serie-02.png)

Con el **pulsador 1** establecemos el valor del bit serie y se muestra en el LED de su derecha. Cada vez que se aprieta el pulsador 2, se hace el desplazamiento, tomándose el bit serie e introduciéndolo en el bit 0 (que se muestra en el led amarillo de la derecha). Esta operación de establecer el bit serie y hacer el desplazamiento se repite dos veces más hasta recibir los **bits 1** y **2**. Por último, con el **botón 3** se carga el valor recibido y se muestra en el display de 7 segmentos. El circuito es el siguiente:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/Serie-03.png)

Lo **cargamos** y lo **probamos**. Usamos los mismos datos que en la animación: introducimos los bits serie **101**. Por cada bit pulsamos el botón de desplazamiento y por último el de carga

[![Click to see the youtube video](http://img.youtube.com/vi/AMaEM1yzPgI/0.jpg)](https://www.youtube.com/watch?v=AMaEM1yzPgI)

## Conversión paralelo-serie

Cuando queremos **enviar datos** desde nuestros circuitos a periféricos que tienen una **interfaz serie** (como I2C, SPI, puerto serie...) necesitamos pasar los datos de **paralelo a serie**, para enviarlos **bit** a **bit**. Esta conversión se hace en dos fases: 

* **Fase de carga**:  carga del dato a enviar en los biestables encadenados
* **Fase de desplazamiento**: Desplazamiento de los bits de los biestables encadenados, para enviar un bit tras otro 

En esta **animación** se muestran estas dos fases, aplicadas al envío serie del dato **101** en binario

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/Serie-04.gif)

El dato que llega a cada biestable proviene de **dos fuentes** diferentes: del **biestable D encadenado** anterior, o bien del exterior. Para elegir en cada momento qué dato debe capturar el biestable colocamos un **multiplexor 2:1**  en su entrada:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/Serie-05.png)

Durante la **fase de carga**, se selecciona el **bit del exterior** (sel = 1), y durante la **fase de desplazamiento** el bit del **biestable anterior** (sel = 0)

### Ejemplo 12: Conversión a serie de un número de 3 bits

Implementaremos un circuito que pase a **serie** un número de 3 bits. El montaje tiene **dos pulsadores**, uno para **cargar** y otro para **desplazar**, **tres interruptores** para introducir el dato en paralelo, **4 LEDs** para mostrar los **biestables de desplazamiento** y un **display de 7 segmentos** para mostrar en decimal el **dato cargado**, que se quiere enviar

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-28/Serie-06.png)

El funcionamiento es el siguiente: Primero se introduce el **dato en paralelo** en los **interruptores**. Al apretarse el **botón de captura** se carga el valor y se muestra en **decimal** en el **display** y en **binario** en los 3 **LEDs**. Con el **botón 2** se realiza un **desplazamiento de un bit** hacia la izquierda. El bit serie saliente se muestra en el **cuarto LED** (en la izquierda)

Construiremos el circuito por pasos. Empezamos por el **biestable D** que almacena el bit de **menor peso** (bit 0). Al apretar el **botón de load **se debe cargar con el valor que hay en el interruptor (switch 0). Al apretar el **botón de desplazamiento se carga** con 0

(Circuito 1)

(Diseño del circuito)

(Vídeo)


# Ejercicios propuestos (20 BitPoints)

(TODO)

Ej1: Apertura caja fuerte con código
Ej2: Mini calculadora que multiplica por 2
Ej3: Transmisión - recepció serie (completo)

Ver los detalles de los ejercicios y las **entregas** en el menú **Archivos/Ejemplos/2-Ejercicios** de la colección de este tutorial

**Resumen**:

* **Ejercicio 28.1** (Total **x Bitpoints**): 

* **Ejercicio 28.2** (Total **x Bitpoints**): 

* **Ejercicio 28.3** (Total **x Bitpoints**): 

* **Ejercicio 28.4** (**5 Bitpoints**). Ejercicio Libre. Premiar la creatividad. **Entregar** por redes sociales o github: Pantallazos, enlaces, vídeos, etc...

# Ejercicios entregados

## Primero

### Ejercicio 28.1
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 28.2
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 28.3
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 28.4
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()


## Segundo

### Ejercicio 28.1
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 28.2
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 28.3
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 28.4
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

## Tercero

### Ejercicio 28.1
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 28.2
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 28.3
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 28.4
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
Es el mismo switch que se ha usado en la propio 