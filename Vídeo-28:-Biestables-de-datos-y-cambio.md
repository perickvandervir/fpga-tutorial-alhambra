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

## Encadenamiento de biestables de cambio

(TODO)

# Biestables de Datos

(Bloque corazón con enable)  
(Pulsador cambio)  
(Conversor evento -- tic)  

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