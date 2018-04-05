![]()

# Vídeo

(TODO)

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

Haz click en la imagen para ver el **vídeo en Youtube**

# Descripción

(TODO)

# Colección

**Academia-Jedi-HW-15.zip**: Colección para este tutorial. Descargar e instalar 

# Contenido

* [Introducción](#introducci%C3%B3n)
* [El servo SM-4303R](#el-servo-springrc-sm-s4303r)
  * [Accesorios impresos en 3D](#accesorios-impresos-en-3d)
  * [El controlador MotorBit](#el-controlador-motorbit)
  * [Ejemplo 1: Control con dos pulsadores](#ejemplo-1-control-con-dos-pulsadores)
  * [Calibrando el servo](#calibrando-el-servo)
  * [Ejemplo 2: Moviendo dos servos](#ejemplo-2-moviendo-dos-servos)
* [El robot ICEbot](#el-robot-icebot)
  * [Construyendo el icebot v0.1](#construyendo-el-icebot-01)
  * [Movimientos del robot](#movimientos-del-robot)
  * [Tabla de verdad de movimientos](#tabla-de-verdad-de-movimientos)
  * [Ejemplo 3: Adelante](#ejemplo-3-adelante)
* Ejercicios propuestos (X Bitpoints)
* [Ejercicios entregados](#ejercicios-entregados)
* [Autor](#autor)
* [Licencia](#licencia)
* [Enlaces](#enlaces)
* [Preguntas frecuentes](#preguntas-frecuentes)




# Introducción

Los servos que hemos usado hasta ahora nos permiten **fijar el ángulo de salida** de su eje. Esto se denomina **control por posición**. Estos servos, además, tienen un **tope mecánico** que impide que giren más de **180 grados**

Exiten otro tipo de servos, conocidos como **servos de rotación contínua**. Se **controlan por velocidad** en vez de por posición, y **NO tienen topes mecánicos**, por lo que pueden girar continuamente. 

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-15/servos-rotc-01.png)

En realidad, funcionan como **motores de corriente continua**, con la ventaja de que **la etapa de potencia está dentro del servo** y su interfaz electrónica es igual que la de los servos tradicionales. Son muy útiles para construir tu **primer robot móvil**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-15/servo-rotc-02.gif)

Típicamente los servos de rotación contínua los obtenemos **trucando** los servos normales: quitando los topes y cambiando el potenciómetro por una resistencia fija, o fijando la posición del propio potenciómetro. En esta página puedes ver las [diferentes formas de trucar un servo Futaba 3003](https://www.diarioelectronicohoy.com/blog/trucar-un-servo-futaba-s3003). El caso 2 es el más interesante para la construcción de robots móviles

Los **servos trucados** se han utilizado muchísimo para construir pequeños **robots móviles** con fines educativos. Uno de los primeros en España fue el [Microbot Tritt](http://www.iearobotics.com/proyectos/tritt/tritt.html) (Año 1996)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-15/tritt.jpg)

El [Skybot](http://www.iearobotics.com/wiki/index.php?title=Skybot) (2004) tenía una estructura diferente, hecha a partir de piezas cortadas por láser, y también usaba **Servos Trucados**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-15/Skybot-v1.0-foto1.jpg)

El primer **printbot** móvil (Robot imprimible) fue el [Miniskybot](http://www.iearobotics.com/wiki/index.php?title=Mini-Skybot_v1.0) (2010), que heredó los **servos trucados** del Skybot

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-15/Miniskybot-v1.0-red-r1.jpg)

El trucaje de servos se ha estdo usando durante muchos años. Sin embargo, ya existen a la venta servos trucados, como por ejemplo el **SpringRC SM-S430R** que es el que usaremos en este tutorial

# El servo SpringRC SM-S4303R

Usaremos el **servo de rotación continua** SpringRC SM-S430R. Lo puedes conseguir en muchas tiendas por internet, como por ejemplo en **Bricogeek**: [Servo SM-4303R Bricogeek](http://tienda.bricogeek.com/motores/118-servomotor-de-rotacion-continua-sm-s4303r.html). Esto NO es un enlace patrocinado. Lo pongo aquí porque Bricogeek funciona muy bien, sin más

Como el resto de servos, viene con **diferentes cabezas** que se **atornillas** al eje de giro

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-15/SM-S4303R-2.jpg)

Le colocamos la **cabeza** que queramos. En este tutorial yo le pondré la que tiene **4 brazos**, que es la que usaremos para el colocar las ruedas del **Icebot**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-15/servos-rotc-03.png)

Estos servos son los que se utilizan en muchos de los **printbots libres**, como el [Renacuajo](https://github.com/bq/printbots/tree/master/Renacuajo), [Beetle](https://github.com/bq/printbots/tree/master/Beetle) o el [Evolution](https://github.com/bq/printbots/tree/master/Evolution)


| ![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-15/beetle-image-1-v1_2.png)  | ![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-15/renacuajo-0.png)  | 
|---|----|
| **Beetle**  | **Renacuajo**   |

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-15/Evolution.jpg)   

El **modelo 3D** del servo SM-S4303R, hecho con **FreeCAD 0.16**, junto a todas sus cabezas, está disponible en la [Biblioteca de piezas de FreeCAD](https://github.com/FreeCAD/FreeCAD-library/tree/master/Electrical%20Parts/Servos/SpringRC-SM-S4303R)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-15/servos-rotc-04.png)

## Accesorios impresos en 3D

Para trabajar con los servos SM-S4303R desde nuestro **panel de corcho***, tenemos estas piezas **imprimibles en 3D**. En este tutorial usaremos 2 servos, por lo que es útil **imprimir 2 soportes**, de cualquiera de las dos versiones

|  Pieza   |  Descripción  |
|----------|---------------|
|  ![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-15/servo-support-2.jpg)        |    [Soporte para servo SM-4303R en vertical](https://github.com/Obijuan/3D-parts/wiki/Soporte-para-servo-SM-4303R.-Vertical). Soporte pequeño para colocar el servo en el cocho en posición vertical           |
| ![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-15/servo-support-1.jpg)         |  [Soporte para servo SM-S4303R. Inclinado](https://github.com/Obijuan/3D-parts/wiki/Soporte-para-servo-SM-S4303R.-Inclinado)  Colocación del servo SM-S4303R en posición inclinada           |

## El controlador MotorBit

Los servos de rotación continua, a todos los efectos, se comportan como **motores de corriente continua** clásicos. Empezaremos por el **controlador** más simple posible: **MotorBit**. Nos permite llevar el motor a **3 estados**: giro en **sentido horario**, giro en **sentido antihorario** y **parado**. Cuando se mueve, siempre lo hará a su **máxima velocidad**. No podemos establecer otra

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-15/Motorbit-1.png)

Necesitamos por tanto usar **2 bits de control**. En el controlador **Motorbit**, uno de los bits controla si el motor está **activo** o no (*On/off*) y el otro el **sentido de giro** (*horario/antihorario*)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-15/Motorbit-2.png)

El **funcionamiento** del controlador MotorBit se detalla en la siguiente **tabla de verdad**. Cuando el **bit de encendido/apagado** (on) está a **0**, el motor se encuentra **parado**, con independencia del valor que tenga el bit de dirección. Cuando el **bit de on** está a **1**, el motor estará **girando**, y su sentido de movimiento dependerá el del valor del **bit de dirección**: Cuando está a **1** gira en **sentido horario**, y cuando está a **0**, lo hace en el **antihorario**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-15/Motorbit-3.png)

## Ejemplo 1: Control con dos pulsadores

Empezaremos por el **circuito más sencillo**: un controlador **MotorBit** cuya salida está conectada a un servo (D0) y sus entradas a **dos pulsadores** (D13 y D11) que nos permiten cambiar los bits de control **manualmente**. Esto nos servirá para experimentar y comprobar cómo funciona. Los pulsadores están conectados a dos **LEDs externos** para ver visualmente el estado de los **bits de control**

El **montaje** es el siguiente

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-15/Ejemplo-1-01.jpg)

El servo se puede alimentar directamente desde el USB del ordenador, pero para evitar los **picos de arranque** he conectado una **pila de 9v**

Para crear el **circuito de ejemplo**, instalamos la colección **Academia-Jedi-HW-15.zip** y seleccionamos el **componente MotorBit**, que se encuentra en **Varios/Motor/SM-S4303R/Motorbit**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-15/Ejemplo-1-02.jpg)

Lo **colocamos**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-15/Ejemplo-1-03.jpg)

Establecemos las conexiones y construimos el siguiente circuito. También lo podemos cargar directamente desde **Archivos/Ejemplos/1-Ejemplo/1-Motor-pulsadores**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-15/Ejemplo-1-04.jpg)

Lo **cargamos** en la placa para probarlo. Lo podemos ver en funcionamiento en este **vídeo de Youtube**:

[![Click to see the youtube video](http://img.youtube.com/vi/0p4b_wM1U7Y/0.jpg)](https://www.youtube.com/watch?v=0p4b_wM1U7Y)

## Calibrando el servo

Al probar el servo con el ejemplo 1, podría ocurrir que cuando el bit de *on* está a 0, y por tanto el motor debería estar parado, se **mueva ligeramente** en un sentido u otro. Para corregirlo, y lograr que está totalmente **parado**, los servos SM-S4303R disponen de un **potenciómetro para calibrar esta posición de reposo**. Se encuentra situado en la cara del servo que está encima del cable

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-15/calibracion-1.png)

Con un **destornillador de estrella**, y con el servo conectado al **ejemplo 1** (pero sin apretar ningún pulsador), giramos ligeramente este potenciómetro hasta que el servo se quede **totalmente parado**. Ya lo tendremos **calibrado**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-15/calibracion-2.jpg)

## Ejemplo 2: Moviendo dos servos

En este segundo ejemplo moveremos **dos servos en direcciones contrarias**. Con un **interruptor** seleccionamos el sentido de la marcha, y con el **pulsador** haremos que se muevan (El interruptor simula una palanca de cambio, de dos marchas, adelante y atrás, y el pulsador el acelerador). Es el paso previo para tener todo listo para construir nuestro primer robot

El **montaje** es el siguiente:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-15/Ejemplo-2-01.jpg)

Y el **circuito** de prueba este:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-15/Ejemplo-2-02.jpg)

Se han colocados **dos controaldores MotorBit**, uno para cada servo. Para conseguir que giren en **direcciones opuestas** usamos una **puerta NOT** entre las entradas de dirección de ambos controladores. El pulsador está conectado directamente a los bits de *on* de ambos controladores. De esta forma, al apretarlo comienzan a moverse los motores

En este **vídeo en youtube** se puede ver su funcionamiento

[![Click to see the youtube video](http://img.youtube.com/vi/s4ifZ0weQHI/0.jpg)](https://www.youtube.com/watch?v=s4ifZ0weQHI)


# El robot ICEbot

Usando **dos servos de rotación continua** ya podemos construir **nuestro primer robot móvil**: el [Icebot 0.1](https://github.com/Obijuan/icebot)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-15/icebot-0_1-01.jpg)

Es un robot de **tipo diferencial**, en el que cada motor acciona una **rueda** de forma **independiente**: un servo para la rueda **derecha** y otro para la **izquierda**

## Construyendo el Icebot 0.1

[Las instrucciones para montar el icebot así como el listado de material lo puedes encontrar en este enlace](https://github.com/Obijuan/icebot/wiki#instrucciones-de-montaje)

En esta foto se resumen todos los **materiales necesarios** para construir la versión **0.1** del icebot

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-15/icebot-materials.jpg)

Y en esta otra se puede ver un **despiece**, para hacer una idea de dónde va cada pieza

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-15/icebot-0_1-03.png)

## Movimientos del robot

Al ser un robot de **tipo diferencial**, las dos ruedas son **independientes**, cada una controlada por un servo. Cada rueda puede estar en **tres estados**: parada, girando en sentido horario o girando en sentido antihorario. Combinando estos estados de las ruedas, conseguirmos un total de **8 movimientos** diferentes para el robot,  que son 9 si contamos el **estado de reposo**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-15/icebot-04.png)

En los movimientos **tipo arco**, sólo hay una rueda moviéndose, mientras que la otra está **parada**. Lo que se consigue es un giro cuyo **centro** es la rueda que está parada

Vamos a fijarnos en el **movimiento de avance**. Ambas ruedas, derecha e izquierda, se están movimiento

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-15/icebot-05.png)

Si nos fijamos en la **rotación de las ruedas**, la rueda izquierda está girando en **sentido antihorario** y la derecha ... en **¡sentido horario!** Las ruedas están rotando en **sentidos opuestos**. Esto es debido a que los servos están colocados en **simetría de espejo**. Si tomamos los servos en la posición en la que están rotando y los giramos para ponerlos en posición vertical, podemos apreciar que realmente los motores giran en sentidos contrarios

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-15/icebot-06.png)

En **1** el icebot está avanzando, con las dos ruedas rotando. En **2** hemos dejado sólo los servos con las ruedas, que continúan rotando. Y en **3** se han girado los servos 90 grados para ponerlos en **posición vertical**, mientras continuaban girando. Podemos ver cómo el **derecho gira en sentido horario** y el **izquierdo en antihorario**

## Tabla de verdad de movimientos

En la siguiente **tabla de verdad** se resumen todos los movimientos posibles y los valores de los bits del **controlador MotorBit** para conseguirlos

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-15/icebot-07.png)

## Ejemplo 3: Adelante

## Ejemplo 4: Adelante - Stop

# Ejercicios propuestos (23 BitPoints)

Ver los detalles de los ejercicios y las **entregas** en el menú **Archivos/Ejemplos/2-Ejercicios** de la colección de este tutorial

**Resumen**:

* **Ejercicio 1** (Total **3 Bitpoints**): 

(TODO): Movimiento del motor 1 en 4 estados: parado - adelante - parado - stop

* **Ejercicio 2** (Total **5 Bitpoints**): 

(TODO): Movimiento alterno de los motores 1 y 2 en los 4 estados (añadimos seleccion manual automático?)

* **Ejercicio 3** (Total **10 Bitpoints**): 

(TODO): montar el icebot. Secuencia Adelante - Derecha, de forma automática

* **Ejercicio 4** (**5 Bitpoints**). Ejercicio Libre. Premiar la creatividad. **Entregar** por redes sociales o github: Pantallazos, enlaces, vídeos, etc...

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
* [Trucaje de un servo Futaba 3003](https://www.diarioelectronicohoy.com/blog/trucar-un-servo-futaba-s3003)
* [Servo de rotación continua SM-4303R](http://tienda.bricogeek.com/motores/118-servomotor-de-rotacion-continua-sm-s4303r.html) (en Bricogeek)

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

Es un servo muy usado y muy estándar. Si buscar por internet encontrarás muchos sitios donde los vendes, a diferentes precios. Aquí en España se puede conseguir muy fácilmente a través de BricoGeek: [Servo SM-4303R Bricogeek](http://tienda.bricogeek.com/motores/118-servomotor-de-rotacion-continua-sm-s4303r.html)

* **Parece ser que los servos Futaba 3003 se pueden trucar para convertirlos en rotación continua. ¿Conoces algún tutorial sobre como hacerlo?**

El Futaba 3003 es uno de los servos que típicamente se han trucado para construir robots móviles con ellos. Robots como [Tritt](http://www.iearobotics.com/proyectos/tritt/tritt.html), [El Skybot](http://www.iearobotics.com/wiki/index.php?title=Skybot) o el [Miniskybot](http://www.iearobotics.com/wiki/index.php?title=Mini-Skybot) los utilizan. Existen muchísimos tutoriales para hacerlo. En esta página puedes encontrar [todas las formas de trucarlos](https://www.diarioelectronicohoy.com/blog/trucar-un-servo-futaba-s3003). El que recomendamos es el caso 2


