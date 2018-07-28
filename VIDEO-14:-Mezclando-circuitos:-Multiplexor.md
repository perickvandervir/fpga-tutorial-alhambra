![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-14/Portada/Tut-14-portada.png)

# Vídeo

[![Click to see the youtube video](http://img.youtube.com/vi/VqJVGluqPE8/0.jpg)](https://www.youtube.com/watch?v=VqJVGluqPE8&list=PLmnz0JqIMEzXaeYVzf2TfTzRekPIVoljw&index=14)

Haz click en la imagen para ver el **vídeo en Youtube**

# Descripción

Los multiplexores nos permite **combinar circuitos** que usan las mismas salidas. Veremos el funcionamiento de dos tipos: los **multiplexores 2:1** y los **4:1**

# Colección

[Academia-Jedi-HW-14.zip](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-14/Collection/Academia-Jedi-HW-14.zip): Colección para este tutorial. Descargar e instalar 

# Contenido

* [Combinando circuitos](#combinando-circuitos)
* [Multiplexor 2 a 1](#multiplexor-21)
  * [Ejemplo 1: Selección manual: LED parpadeando a dos velocidades](#ejemplo-1-selecci%C3%B3n-manual-led-parpadeando-a-dos-velocidades)
  * [Ejemplo 2: Selección automática. Sirena](#ejemplo-2-selecci%C3%B3n-autom%C3%A1tica-sirena)
* [Multiplexor 4 a 1](#multiplexor-41)
  * [Ejemplo 3: LED en 4 modos](#ejemplo-3-led-en-4-modos)
  * [Ejemplo 4: Secuencia de 3 notas con un zumbador ](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/VIDEO-14:-Mezclando-circuitos:-Multiplexor#ejemplo-4-secuencia-de-3-notas-con-un-zumbador)
* [Ejercicios propuestos (14 Bitpoints)](#ejercicios-propuestos-14-bitpoints)
* [Ejercicios entregados](#ejercicios-entregados)
  * [Enea Kao](#enea-kao)
  * [Josep Montoliu](#josep-montoliu-klarojms)
  * [Jose López](#jose-l%C3%B3pez)
* [Autor](#autor)
* [Licencia](#licencia)
* [Enlaces](#enlaces)
* [Preguntas frecuentes](#preguntas-frecuentes)

# Combinando circuitos

Ya conocemos una forma de **combinar circuitos**: la [superposición](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-6:-Bombeando-bits#superposici%C3%B3n-de-circuitos). Cuando tenemos dos **circuitos independientes**, que funcionan correctamente de forma separada, los podemos meter en la misma FPGA y funcionarán los dos a la vez, aprovechando el **paralelismo** que hay en el hardware

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-14/composicion-01.png)

Pero... ¿Y si los circuitos **NO son independientes** y acceden por ejemplo al **mismo LED**? **¿Cómo los combinamos?**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-14/composicion-02.png)

Por separado funcionan correctamente, pero como acceden **al mismo LED0** no podemos aplicar la superposición directamente

Una forma de solucionarlo es mediante **multiplexación**. El acceso al LED0 no lo pueden hacer a la vez, sino que lo tendrán que hacer **por turnos**. El LED0 estará disponible **durante un tiempo** para el circuito 1 y otro tiempo para el circuito 2. Mediante una entrada especial, llamada **entrada de selección**, se indicará **cuál** de los dos circuitos es el que **puede acceder** al LED0

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-14/composicion-03.png)

Mientras el **bit de selección** esté a **0**, será el **circuito 1** el que enviará bits al LED0. Cuando el bit de selección se pone a **1**, es el **circuito 2** el que se conecta. En esta animación se muestra la idea

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-14/composicion-4.gif)

Este tipo de **combinación** de circuitos se llama **multiplexación**, y el elemento que permite hacerlo se llama **Multiplexor**

En general lo(cronograma corazones)s multiplexores tienen **N canales de entrada**, además de las **entradas de selección**,
 y **una salida**. Empezaremos por el **multiplexor más sencillo**: Multiplexor de 2 a 1

# Multiplexor 2:1

Un **multiplexor de 2 a 1** tiene **2 canales de entrada**, **una entrada de selección** y **una salida**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-14/mux-2-1-01.png)

Su funcionamiento está definido por esta **tabla de verdad simplificada**. Las **Xs** representan **cualquier bit**, que puede estar a 1 ó 0. Cuando por la **entrada de selección** hay un **0**, por la salida sale el **canal 0** (los bits verdes). Cuando la entrada de selección es **1**, lo que sale son los bits del **canal 1** (grises)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-14/mux-2-1-02.png)

## Ejemplo 1: Selección manual. LED parpadeando a dos velocidades

En este primer ejemplo tenemos **dos corazones**, de 1Hz y 4Hz, asociados a los **canales 0** y **1** respectivamente. Mediante un **interruptor externo** seleccionaremos **manualmente** qué canal accede al **LED externo**, haciéndolo **parpadear**. El resultado será un **LED que parpadea a dos velocidades**, según la posición del interruptor

Este es el **montaje físico**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-14/mux-2-1-04.jpg)

Para crear el **circuito en Icestudio** nos aseguramos de que tenemos la colección **Academia-Jedi-HW-14.zip** instalada y nos vamos al menú **Varios/Mux**. Elegimos el componente **Mux-2-1**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-14/mux-2-1-ej2-04.png)

Y nos aparece el **Multiplexor de 2 a 1**. Esta es la pinta que tiene en icestudio

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-14/mux-2-1-ej2-05.png)

En la izquierda están las **tres entradas**, denominadas i1 (canal1), i0 (canal0) y sel (selección). La salida, como en todos los componentes de icestudio, está a la derecha

También podemos elegir el otro modelo que hay: **mux-2-1-flip**. Es exactamente igual, pero con las **entradas cambiadas de orden**. El canal 0 está arriba y el canal 0 abajo. Pero por lo demás son exactamente iguales:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-14/mux-2-1-ej2-06.png)

**Creamos** este circuito:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-14/mux-2-1-03.png)

Lo **cargamos** en la placa para probarlo. En esta **animación** vemos su funcionamiento

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-14/mux-2-1-05.gif)

# Ejemplo 2: Selección automática. Sirena

Crearemos una **sirena** usando un único **zumbador**. Ahora el multiplexor 2:1 se **conmutará automáticamente** para seleccionar qué tono suena. Este es el **montaje**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-14/mux-2-1-ej2-01.jpg)

En las salidas **D13** y **D12** se han conectado **2 LEDs externos** para generar una **sirena luminosa**, y en el **D0** está conectado el **zumbador**

Este es el circuito en Icestudio. Por el **canal 0** del multiplexor se introduce la **nota alta**, y por el **canal 1** la nota **baja** (daría igual si se hace al revés). La **selección** del canal se hace **automáticamente**, utilizando un **corazón de 1Hz**. De esta forma durante **medio segundo** suena la **nota baja** y durante el otro medio la **alta**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-14/mux-2-1-ej2-02.jpg)

**Cargamos** el circuito y lo **probamos**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-14/mux-2-1-ej2-03.gif)

**Escucharemos** la sirena y veremos cómo se alternan los LEDs externos

# Multiplexor 4:1

Los multiplexores 4 a 1 tienen **4 canales de entrada** y **2 bits de selección**. El funcionamiento es el mismo que el de los multiplexores 2:1, pero ahora se selecciona entre los cuatro canales

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-14/mux-4-1-01.png)

La **tabla de verdad** simplificada se muestra a continuación. El valor de los **dos bits de selección** determinan cuál de los canales es el que se saca por la salida. Por cada uno de estos canales llegan bits genéricos, que pueden estar a 1 ó 0 (por eso lo representamos con una X)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-14/mux-4-1-02.png)

El **funcionamiento** se muestra gráficamente en esta **animación**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-14/mux-4-03.gif)

Se ha representado un ejemplo en el que se van seleccionando los **4 canales secuencialmente**, sin embargo se puede hacer en el **orden que se quiera** y asignar el **tiempo que se quiera** a cada canal

## Ejemplo 3: LED en 4 modos

Vamos a utilizar un **multiplexor 4 a 1** para seleccionar el **estado** que queremos para un **LED externo**: apagado, encendido, parpadeo lento y parpadeo rápido. Este modo se configura con **dos interruptores externos**. Este es el **montaje**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-14/ej3-01.jpg)

El **multiplexor 4:1** lo encontramos en el mismo menú que el Mux 2:1: **Varios/Mux**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-14/ej3-02.jpg)

Lo **colocamos**. Esta es la pinta que tiene:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-14/ej3-03.jpg)

Los 4 entradas superiores se corresponden con los canales 3,2,1 y 0. Las dos inferiores son los **dos bits de selección**. También tenemos la versión **mux-4-1-flip**, que es igual pero con las entradas ordenadas en orden inverso

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-14/ej3-04.jpg)

Conectamos las dos entradas de selección a los **pulsadores externos**, y la salida al **LED externo**. Por los canales de entrada conectamos un **bit a 0**, otro a **1**, un corazón a **1Hz** y otro a **4Hz**. Esto se corresponde con los 4 modos de funcionamiento que queremos para el LED. El **circuito** es el siguiente:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-14/ej3-05.jpg)

Inicialmente, cuando los dos interruptores están a cero, el **LED está apagado**. Al activar el interruptor de la derecha, el **LED se enciende**. Si activamos también el de la izquierda, el **LED parpadea rápido**. Al desconectar el de la derecha el **LED parpadea lent**o y finalmente al desconectar el de la izquierda, **se apaga**. **Cargamos** el circuito y vemos su funcionamiento

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-14/mux-4-04.gif)

## Ejemplo 4: Secuencia de 3 notas con un zumbador

Como último ejemplo usaremos un multiplexor 4:1 para **tocas las notas** DO-RE-MI (y un silencio) **consecutivamente**, con un zumbador. Usaremos dos **LEDs externos** para mostrar el canal que está seleccionado. El **montaje** es el siguiente:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-14/mux-4-1-ej4-01.jpg)

Por los canales 0,1,2 y 3 del multiplexor introduciremos, respectivamente, un cero (silencio), y las notas DO, RE y MI. Por su salida conectamos el zumbador. La **selección se hace automáticamente** mediante dos corazones de 1 y 2Hz, lo que le asigna un tiempo de **250ms** a cada nota (ahora veremos por qué). Este es el **circuito**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-14/mux-4-1-ej4-02.jpg)

El **corazón de 1Hz** está conectado a la entrada de selección **s1**. Esto significa que cada **medio segundo** (500ms) habrá un cambio en esa entrada. El **corazón de 2Hz** se conecta a la entrada s0, y en este caso habrá **un cambio cada 250ms**. Esa información la representamos en el siguiente dibujo

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-14/mux-4-1-ej4-03.jpg)

Inicialmente los dos corazones están a 0, por lo que **s1** y **s0** valen **cero**, y en el multiplexor se selecciona el **canal 0**. Al cabo de 250ms, cambia **s0** a **1**, pero **s1** todavía sigue en **0**, por lo que se selecciona el **canal 1**. Al transcurrir otros 250ms, **s0** cambia a **0** nuevamente, pero ahora **s1** se pone a **1**, seleccionándose el **canal 2**. Y por último, al pasar los siguientes 250ms, **s0** se pone nuevamente a **1** y **s1** continúa con **1**. El **canal 3** se selecciona. Todo este ciclo ha durado 1 segundo, y se vuelve a repetir

**Cargamos** el circuito en la placa y lo **probamos**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-14/mux-4-05.gif)

# Ejercicios propuestos (14 BitPoints)

Ver los **detalles** de los ejercicios y las **entregas** en el menú **Archivos/Ejemplos/2-Ejercicios** de la colección de este tutorial

**Resumen**:

* **Ejercicio 1** (Total **3 Bitpoints**): Limpiaparabrisas a dos velocidades. Usar un servo para simular un limpiaparabrisas de un coche, que se mueva a dos velocidades: **lenta** y **rápida**, determinadas por un **interruptor externo**. En el modo lento el servo permanecerá **2 segundos** en cada posición, y en el 
modo rápido **medio segundo** (Freq. de 1Hz)

* **Ejercicio 2** (Total **3 Bitpoints**): Sirena configurable. Sirena que funciona en **dos modos**, según la posición de un **interruptor externo**, usando un **único zumbador**. Además, tiene un **pulsador externo**, que al apretarlo debe sonar la sirena, y al soltarlo se apaga. En el **modo 1** se emiten alternativamente tonos de **1Khz** y **2Khz**, cada uno durante medio segundo.  En el **modo 2** se emiten alternativamente las notas **DO** y **Mi**, con duraciones de **250ms**  cada una.

* **Ejercicio 3** (Total **5 Bitpoints**): Franky en modo automático y manual. Este es un ejercicio de **COMPLEJIDAD MEDIA**. Hay que entender bien los detalles del enunciado para implementarlo, que se encuentran en los ejercicios de esta colección. Aquí se puede ver un **vídeo de Franky** funcionando en los dos modos, **automático** y **manual**:

[![Click to see the youtube video](http://img.youtube.com/vi/SWdSmQsTVTk/0.jpg)](https://www.youtube.com/watch?v=SWdSmQsTVTk)

* **Ejercicio 4** (**3 Bitpoints**). Ejercicio Libre. Premiar la creatividad. **Entregar** por redes sociales o github: Pantallazos, enlaces, vídeos, etc...

# Ejercicios entregados

## Enea Kao

### Ejercicio 1

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-14/Eneakao/Esquema-Ejercicio-14-1.png)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/0yVk5d7FiQE/0.jpg)](https://www.youtube.com/watch?v=0yVk5d7FiQE)

### Ejercicio 2
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-14/Eneakao/Esquema-Ejercicio-14-2v.png)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/5csxhzMXWbQ/0.jpg)](https://www.youtube.com/watch?v=5csxhzMXWbQ)

### Ejercicio 3

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-14/Eneakao/Esquema-Ejercicio-14-3.png)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/k1kAvtP2B9U/0.jpg)](https://www.youtube.com/watch?v=k1kAvtP2B9U)

### Ejercicio 4 (libre)

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-14/Eneakao/Esquema-Ejercicio-14-2.png)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/jIUf3Rh-9Pk/0.jpg)](https://www.youtube.com/watch?v=jIUf3Rh-9Pk)

## Josep Montoliu (Klarojms)

### Ejercicio 1
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-14/klarojms/Ejercicio%201-1.png)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/VbclTqKp1UQ/0.jpg)](https://www.youtube.com/watch?v=VbclTqKp1UQ)

### Ejercicio 2
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-14/klarojms/Ejercicio%202-1.png)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/l_D_-tqJ_X0/0.jpg)](https://www.youtube.com/watch?v=l_D_-tqJ_X0)

### Ejercicio 3
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-14/klarojms/Ejercicio%203-1.png)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/ScS-UQOjS7I/0.jpg)](https://www.youtube.com/watch?v=ScS-UQOjS7I)

### Ejercicio 4
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-14/klarojms/Ejercicio%204-4.png)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/1HuM0mBosG4/0.jpg)](https://www.youtube.com/watch?v=1HuM0mBosG4)

## Jose López

### Ejercicio 1
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-14/Jose%20Lopez/ejercicio_14-1.jpg)

* [Vídeo en Twitter](https://twitter.com/joselopez_ga/status/972170855668207616)

### Ejercicio 2
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-14/Jose%20Lopez/ejercicio_14-2.jpg)

* [Vídeo en Twitter](https://twitter.com/joselopez_ga/status/972172137762115586)

### Ejercicio 3
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-14/Jose%20Lopez/ejercicio_14-3.jpg)

* [Vídeo en Twitter](https://twitter.com/joselopez_ga/status/972172914400342016)

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


