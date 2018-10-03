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
  * [Biestables D encadenados (Conexión en serie)](#biestables-d-encadenados-conexi%C3%B3n-en-serie)
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

(TODO)

# Un Biestable D para unirlos a todos

(TODO)

# Ejercicios propuestos (20 BitPoints)

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