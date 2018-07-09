> ![]()

(En construcción...)

# Vídeo

(En construcción...)

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

Haz click en la imagen para ver el **vídeo en Youtube**

# Descripción

TODO

# Colección

**Academia-Jedi-HW-22.zip**: Colección para este tutorial. Descargar e instalar 

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
    * [Ejemplo 4: Parpadeo simultáno de dos LEDs](#ejemplo-4-parpadeo-simult%C3%A1neo-de-dos-leds)
* Ejercicios propuestos (X Bitpoints)
* [Ejercicios entregados](#ejercicios-entregados)
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

Partiendo del ejemplo anterior, si ahora queremos que los **LEDs parpadeen de otra forma**, por ejemplo simultáneamente, sólo hay que cambiar los valores de la tabla de verdad, manteniendo la misma estructura del circuito

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-22/Ejemplo4-01.png)

Colocamos los números de salida **0** (00) y **3** (11), por lo que los dos LEDs estarán siempre en el **mismo estado**. Lo **cargamos** y lo **probamos** en la placa:

(Animación)

Además, 


TODO
* 1x2: Secuencia: LEDs parpadeando a la vez: Ejemplo de modificación de tabla
* 1x2: Icebot: Adelante-Stop
* 1x4: Secuencia LEDs. Dos secuencias en paralelo
* 1x8: Secuencia LEDs. Dos sencuencias multiplexadas

# Circuitos combinacionales con 2 entradas y varias salidas

TODO

* 2x2: Icemove4
* 2x4: Icemove8

# Circuitos combinacionales con 3 entradas y varias salidas

TODO

Ej. Decodificador de 3 a 8

# Generación automática de tablas: IceFactory

TODO

# Ejercicios propuestos (X BitPoints)

Ver los detalles de los ejercicios y las **entregas** en el menú **Archivos/Ejemplos/2-Ejercicios** de la colección de este tutorial

**Resumen**:

* **Ejercicio 22.1** (Total **x Bitpoints**): 

* **Ejercicio 22.2** (Total **x Bitpoints**): 

* **Ejercicio 22.3** (Total **x Bitpoints**): 

* **Ejercicio 22.4** (**5 Bitpoints**). Ejercicio Libre. Premiar la creatividad. **Entregar** por redes sociales o github: Pantallazos, enlaces, vídeos, etc...

# Ejercicios entregados

## Primero

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




