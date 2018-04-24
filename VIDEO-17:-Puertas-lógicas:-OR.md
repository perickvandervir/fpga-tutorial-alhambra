
![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-17/Portada/Tut-17-portada.png)

# Vídeo

[![Click to see the youtube video](http://img.youtube.com/vi/cm2mNR9b9Jc/0.jpg)](https://www.youtube.com/watch?v=cm2mNR9b9Jc&index=17&list=PLmnz0JqIMEzXaeYVzf2TfTzRekPIVoljw)

Haz click en la imagen para ver el **vídeo en Youtube**

# Descripción
La **puerta lógica OR** nos permite hacer **manipulaciones** de bits. Aprenderemos su funcionamiento y la utilizaremos para **combinar** señales.  Con esto ya conocemos las **tres puertas lógicas básicas**: AND, OR y NOT, que nos permiten crear cualquier otra **función lógica**, por muy complicada que sea

# Colección

[Academia-Jedi-HW-17.zip](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-17/Collection/Academia-Jedi-HW-17.zip): Colección para este tutorial. Descargar e instalar 

# Contenido

* [Introducción](#introducci%C3%B3n)
* [La puerta OR](#la-puerta-or)
* [Tabla de verdad](#tabla-de-verdad)
* [Ejemplo 1: Probando la OR con pulsadores](#ejemplo-1-probando-la-or-con-pulsadores)
* [Ejemplo 2: Alarma disparada manualmente o por presencia](#ejemplo-2-alarma-disparada-manualmente-o-por-presencia)
* [Ejemplo 3: Cerradura con doble clave](#ejemplo-3-cerradura-con-doble-clave)
* [Resumen de las puertas lógicas AND, OR y NOT](#resumen-puertas-l%C3%B3gicas-and-or-not)
* [Ejercicios propuestos (20 Bitpoints)](#ejercicios-propuestos-20-bitpoints)
* [Ejercicios entregados](#ejercicios-entregados)
  * [Federico Coca](#federico-coca-fgcoca)
* [Autor](#autor)
* [Licencia](#licencia)
* [Enlaces](#enlaces)
* [Preguntas frecuentes](#preguntas-frecuentes)

# Introducción

Vamos a aprender a manejar una nueva puerta lógica: la puerta **OR**. En realidad ya la conocemos, del juego del **circuit Scramble**. En el **nivel 2** había **2** puertas OR, y una AND. Nos fijamos sólo en una: la que está conectada a los **dos pulsadores** de la izquierda

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-17/Circuit-scramble-N2-1.png)

Las puertas OR tiene **dos entradas** y **una salida**. Inicialmente, los botones están **sin pulsar**, por lo que por las **entradas** están a **0**. Y la salida también a **0**

Al **activar el pulsador**, una de las entradas se pone a **1**, pero aunque la otra sigue estándo a **0**,  la **salida** se activa, y se pone a **1**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-17/Circuit-scramble-N2-2.png)

Con el caso contrario ocurre lo mismo. Si lo que se pone a 1 es su entrada de la derecha, pero se mantiene a 0 la de la izquierda, la puera también se activa

Y también si las **dos entradas** están a **1**: la puerta OR se activa

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-17/Circuit-scramble-N2-3.png)

En esta animación se resumen los **4 casos posibles**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-17/Circuit-scramble-N2-4.gif)

El **funcionamiento** es fácil de intuir: La puerta OR se **activa** si **alguna de sus entradas lo está** (o ambas). O visto de otra manera diferente: La puerta OR sólo está **desactivada** (a 0) cuando sus **entradas están desactivadas**. En el resto de casos está activa

# La puerta OR

La **OR** es una de las tres **puertas lógicas básicas**, que nos permiten **manipular** y **combinar bits**. El **símbolo** usado para su representación en los circuitos digitales es este:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-17/OR-1.png)

Como **regla nemotécnica** para diferenciar la puerta OR de la AND, cuando no llevan la palabra escrita, hay que fijarse en la **parte curvada** por la que llegan las entradas. Es como si representase un segmento de una  letra O grande :-)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-17/OR-2.png)

La puerta OR tiene **dos entradas** y **una salida**. La manera de describir su funcionamiento es mostrando su **respuesta** a **todas las posibles entradas**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-17/OR-3.png)

Observando todos los casos, vemos que **la puerta OR  está a 0** sólo cuando sus **dos entradas están desactivadas**. En el resto de casos siempre está a **1** 

# Tabla de verdad

Como la puerta OR tiene **2 entradas**, en total hay 4 casos diferentes y la tabla de verdad tiene **4 filas**, igual que la de la AND

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-17/tabla-verdad-01.png)

# Ejemplo 1: Probando la OR con pulsadores

Haremos un ejemplo **hola mundo** para comprobar cómo funciona la puerta OR. El **montaje** que usaremos será el siguiente. Colocaremos dos pulsadores externos. Cada uno de ellos con su LED de testigo para saber cuándo está pulsado. Y un tercer **LED externo** (a la derecha) que es el resultado de aplicar la **puerta OR** a estos pulsadores:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-17/Ejemplo-1-1.jpg)

La **puerta OR** la colocamos desde el **menú Puertas/or**, con la colección **Academia-Jedi-HW-17.zip** instalada

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-17/Ejemplo-1-2.gif)

El **circuito de ejemplo** lo podemos crear desde cero o bien cargarlo desde el menú **Archivo/ejemplos/1-Ejemplos/1-OR-Pulsadores**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-17/Ejemplo-1-3.jpg)

Lo **cargamos** en la placa y lo probamos. En esta **animación** podemos ver su funcionamiento

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-17/Ejemplo-1-4.gif)

En cuanto alguno de los dos botones,izquierdo o derecho, está pulsado, se activa la salida de la puerta OR que está conectada al **LED verde**

# Ejemplo 2: Alarma disparada manualmente o por presencia

Como segundo ejemplo vamos a hacer una **alarma de dos tonos**, como la que ya conocemos y hemos hecho en los ejercicios de otros tutoriales pasados, que se **active automáticamente** mediante un **sensor de IR**. La novedad está ahora en que vamos a añadir una **activación manual** mediante un **pulsador**. De esta forma, la alarma se activará bien porque detecte con los sensores IR, **O** bien porque se apriete el pulsador (u ocurran ambas cosas simultáneamente)

El **circuito en icestudio** es el siguiente:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-17/Ejemplo-2-1.png)

La parte superior derecha es la **alarma**, que se activa mediante una **puerta AND** de **habilitación** que deja pasar los tonos hacia el zumbador. Esa señal de activación proviene del pulsador y del sensor de IR **combinadas** a través de una **puerta OR**, de forma que la alarma se activa cuando se ponga a 1 alguna de ellas (o ambas). Igual que en el ejemplo 1, tenemos puestos los **LEDs testigos**, para visualizar el estado de las entradas y de la salida de la puerta OR

El **montaje** es el siguiente:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-17/Ejemplo-2-2.jpg)

Lo **cargamos** en la placa y lo probamos. En este **Vídeo de youtube** se puede ver en funcionamiento:

[![Click to see the youtube video](http://img.youtube.com/vi/3EIxx9mqdwg/0.jpg)](https://www.youtube.com/watch?v=3EIxx9mqdwg)

# Ejemplo 3: Cerradura con doble clave

Este es un ejemplo similar al que ya hicimos en el [Tutorial 12](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-12:-Interruptores-y-pulsadores-externos#ejemplo-3-apertura-de-una-cerradura-con-clave). Pero ahora la **cerradura** se abre con **dos claves diferentes**, que en este ejemplo serán los **códigos 000** y **111**. Cuando introducimos a través de los **3 interruptores** cualquiera de estos dos códigos, el servo se moverá, simulando que la caja fuerte se ha abierto

No pondremos un pulsador de apertura. Se **abrirá automáticamente** en cuanto se detecte alguno de los **códigos correctos**. El montaje es el siguiente:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-17/Ejemplo-3-1.jpg)

Se han colocado los **tres interruptores** en la parte izquierda, y a continuación **3 LEDs externos** que muestran su estado. El LED del extremo de la derecha es el que indica si el código es correcto (encendido) o no (apagado). El **circuito en Icestudio** es:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-17/Ejemplo-3-2.jpg)

Las **dos puertas AND** de la parte superior son las encargadas de detectar el **código 111**. Las **3 NOT y las 2 AND** inferiores detectan el **código 000**. Esta dos señales pasan a través de la **OR** y van directas al controlador del servo para abrirlo o cerrarlo (así como al LED verde que indica código correcto)

En este **vídeo en youtube** se muestra el ejemplo en funcionamiento:

[![Click to see the youtube video](http://img.youtube.com/vi/XYZt74OJDrY/0.jpg)](https://www.youtube.com/watch?v=XYZt74OJDrY)

# Resumen puertas lógicas: AND, OR, NOT

Ya conocemos las puertas lógicas **AND**, **OR** y **NOT**. Sólo con ellas podemos implementar **cualquier función lógica**. O lo que es lo mismo, usando **combinaciones** de sólo estas **tres puertas lógicas** podemos construir **cualquier circuito combinacional**

Existen más puertas lógicas, pero **las podemos construir a partir de estas tres**. También existen otros conjuntos de puertas que nos permiten obtener cualquier circuito combinacional. Lo veremos más adelante.

Aquí dejamos un **resumen** de las puertas lógicas **AND**, **OR** y **NOT**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-17/tablas-verdad-and-not-or.png)

# Ejercicios propuestos (20 BitPoints)

Ver los detalles de los ejercicios y las **entregas** en el menú **Archivos/Ejemplos/2-Ejercicios** de la colección de este tutorial

**Resumen**:

* **Ejercicio 17.1** (Total **3 Bitpoints**): Barrera en modo automática y manual

Diseñar el circuito digital para controlar una **barrera de acceso** que se levantará **automáticamente** cuando detecte la presencia de un coche, y se bajará cuando no lo haya. Además, tiene un **modo manual** para poder subirla mediante un **interruptor**. La barrera sólo baja si no hay coche detectado y no está activada manualmente

* **Ejercicio 17.2** (Total **5 Bitpoints**): Caja fuerte con dos códigos de apertura

Diseñar un circuito digital para que se abra una **caja fuerte** cuando se introduce el código **101** ó el **010** en tres interruptores externos. Al abrirse se moverá un servo a una posición, y cuando está cerrada se moverá a la contraria

* **Ejercicio 17.3** (Total **7 Bitpoints**): Franky en modo defensa, con disparo manual

Diseñar un circuito digital para que franky funcione en modo "defensa". Estará irando de lado a lado con un periodo de **4 segundos** (2 segundos en cada lado).  En uno de los lados disparará automáticamente una **ráfaga** por sus ojos, que parpadearán a una frecuencia de **10Hz**. Además, durante el disparo, sonarán **pitidos  de 1Khz**, con una **cadenacia de 10Hz** (pi-pi-pi-pi...). Adicionalmente se colocará  
un **pulsador** para **disparo manual**. Al pulsarlo realizará los mismos disparos  comentados anteriormente (señal luminosa en los ojos y pitidos de 1Khz con  cadencia de 10Hz)

* **Ejercicio 17.4** (**5 Bitpoints**). Ejercicio Libre. Premiar la creatividad. **Entregar** por redes sociales o github: Pantallazos, enlaces, vídeos, etc...

# Ejercicios entregados

## Federico Coca (fgcoca)

### Ejercicio 1
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-17/fgcoca/Ejercicio-1/-Ejercicio17_1%20%E2%94%80%20P1.png)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/yEYe2gz--sI/0.jpg)](https://www.youtube.com/watch?v=yEYe2gz--sI)

### Ejercicio 2
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-17/fgcoca/Ejercicio-2/Ejercicio17_2%20%E2%94%80%20P2.png)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/EyTUJuAnP0o/0.jpg)](https://www.youtube.com/watch?v=EyTUJuAnP0o)

### Ejercicio 3
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-17/fgcoca/Ejercicio-3/Ejercicio17_3%20%E2%94%80%20P3.png)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/9eZmwUxKaHM/0.jpg)](https://www.youtube.com/watch?v=9eZmwUxKaHM)

### Ejercicio 4
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-17/fgcoca/Ejercicio-4/Ejercicio17_4%20%E2%94%80%20P4.png)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)](https://www.youtube.com/watch?v=hByYWTzvSgY)


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



