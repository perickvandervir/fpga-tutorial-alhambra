![]()

# Vídeo

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

Haz click en la imagen para ver el **vídeo en Youtube**

# Descripción

(TODO)

# Colección

**Academia-Jedi-HW-25.zip**: Colección para este tutorial. Descargar e instalar 

# Contenido

* [Introducción](#introducci%C3%B3n)
* [Eventos y notificaciones](#eventos-y-notificaciones)
  * [Ejemplo 1: Encender un LED con pulsador, sin biestable](#ejemplo-1-encender-un-led-con-pulsador-sin-biestable)
* [Biestables con Set y Reset](#biestables-con-set-y-reset)
  * [Ejemplo 2: Notificación de botón apretado](#ejemplo-2-notificaci%C3%B3n-de-bot%C3%B3n-apretado)
  * [Banderas (Flags)](#banderas-flags)
* Ejercicios propuestos (X Bitpoints)
* [Ejercicios entregados](#ejercicios-entregados)
* [Autor](#autor)
* [Licencia](#licencia)
* [Créditos y agradecimientos](#cr%C3%A9ditos-y-agradecimientos)
* [Enlaces](#enlaces)
* [Preguntas frecuentes](#preguntas-frecuentes)

# Introducción

Los **circuitos digitales** realizan tres operaciones con bits: **transporte**, **manipulación** y **almacenamiento**. Los **cables** se encargan del **transporte** y los **circuitos combinacionales** de su **manipulación**. Nos falta por aprender **cómo almacenar bits**. Esto lo realizan los **biestables**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/intro-01.png)

Un biestable es el **elemento mínimo** que permite **almacenar un bit**. Almacenar los bits es **muy importante**, porque nos permite **recordar** lo que ha ocurrido en el **pasado**. Y así **tomar decisiones** sobre lo que hacer en el presente y el futuro.

Y es precisamente por esta **capacidad de recordad** que utilizaremos **este símbolo** para **representar un biestable** en Icestudio:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/intro-02.png)

Los biestables son los que guardan las **notificaciones** de lo que ocurre en nuestro circuito. Como un biestable sólo puede **almacenar 1 bit**, se usará para **registrar** sólo **1 notificación**

Aprenderemos a **manejar biestables** usando la **intuición**, y haciendo **muchos ejemplos** de su uso. La mejor manera de aprender es **practicar**. ¡Vamos a ello!

# Eventos y notificaciones

En nuestros circuitos ocurren **eventos**: pulsación de un botón, detección de un objeto por parte de un sensor IR, que dos números sean iguales, que haya transcurrido cierto tiempo, que una operación se ha terminado de realizar... 

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/intro-03.png)

Definimos **evento** como un **cambio en una señal**. Así por ejemplo, al cambiar el estado de un **pulsador** de NO estar apretado a pulsarse, aparece un **cambio de 0 a 1** en su señal. Este cambio es un **evento**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/intro-04.png)

Hay dos tipos de cambio, **de 0 a 1**, también llamado **flanco de subida**, y de **1 a 0**, denominado **flanco de bajada**. Cuando soltamos el pulsador se genera otro evento, pero esta vez el cambio de la señal es de 1 a 0 (flanco de bajada)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/intro-05.png)

Hasta ahora, los **eventos** los hemos **mostrado en LEDs**, y en otros **periféricos de salida**, como los servos. Sólo hemos visualizado el **presente**. Con los biestables podemos **registrar los eventos**, para **recordarlos**

### Ejemplo 1: Encender un LED con pulsador, sin biestable

Retomaremos el circuito "Hola mundo" para **encender un LED** al apretar **un pulsador**, del [Tutorial 9](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-9:-Pulsadores-y-entradas). 

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/intro-06.png)

Lo **cargamos** y lo **probamos**

[![Click to see the youtube video](http://img.youtube.com/vi/8UH14Mup2JU/0.jpg)](https://www.youtube.com/watch?v=8UH14Mup2JU)

Funciona como esperábamos: es un circuito muy sencillo y muy conocido. Pero vamos a fijarnos en **lo que está ocurriendo**: en el **LED** se está reflejando **lo que ocurre en el presente**, en este momento. Mirando el LED sabemos el estado del pulsador. Pero **no sabemos nada** de lo que ha ocurrido en el **pasado**. Necesitamos usar **biestables** para ello

# Biestables con Set y Reset

Los **biestables** nos permiten **registrar** los eventos y **notificarlos**. Para recordar cosas lo primero que hacemos es **registrarlas**. Es la **operación SET** de los biestables. Los móviles nos lo marcan con las **notificaciones** que vemos en la parte superior: al mirarlas sabemos que hay mensajes pendientes, que sucedieron en el pasado, y que todavía no han sido leidos

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/Biestable-RS-01.png)

La segunda operación es la de **borrado de las notificaciones**. En el caso de la lectura de mensajes en el móvil, las notificaciones desaparecen una vez que los hemos leído. Es la **operión RESET** de los biestables

Así, nuestro biestable es un circuito con **dos entradas**: Set y Reset. Una para **registrar el evento**, y la otra para **borrarlo**. Y tienen **una salida**: nos indica la **notificación**. Si está a **0** es que **no ha ocurrido el evento**. Si está a **1** es que hay **una notificación pendiente**

## Ejemplo 2: Notificación de botón apretado

Vamos a hacer un circuito para **registrar** y **notificar** el evento de **botón apretado**. Conectamos el pulsador a la **entrada SET** del biestable y la su **salida** a un **LED**: de esta forma veremos en el LED el estado del biestable: Si está **encendido** es que el **pulsador ha sido apretado** en el pasado. Si está apagado es que no se ha pulsado desde la última vez que lo borramos

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/Biestable-RS-02.png)

Es necesario conectar la **entrada de RESET** para **borrar la notificación pendiente** y volver al estado inicial. Esto lo hacemos conectándola al **pulsador interno SW1**

**Cargamos** el circuito y lo **probamos**:

[![Click to see the youtube video](http://img.youtube.com/vi/Qadxbefl4k8/0.jpg)](https://www.youtube.com/watch?v=Qadxbefl4k8)

En cuanto se **aprieta el pulsador**, el biestable **registra el evento** y se pone su **salida** a **1**. Aunque soltemos el pulsador, la notificación seguirá estando: recuerda que el **botón se ha apretado**. Como sólo tiene **memoria de 1 bit**, sólo puede recordar **un evento**, por lo que no puede distinguir si el pulsador ha sido apretado una o varias veces. Con el otro pulsador **borramos la notificación**

## Banderas (Flags)

Los **biestables con Set y Reset**, como el que hemos usado en el **ejemplo 2**, funcionan como **banderas** o **indicadores** (Conocidos como *flags* en inglés).  Es una técnica que se usa también en **programación**, donde se definen **variables** que permiten registrar la ocurrencia de un evento. Según el valor de estos flags, el programa hace una acción u otra

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/Biestable-RS-03.png)

Con la **entrada SET** ponemos la **bandera** a **1**, para señalar que ha ocurrido el evento. Con **RESET** la ponemos a **cero**. Es un comportamiento muy sencillo, pero **muy potente**, y nos permitirá hacer muchísimas cosas, como veremos en los **ejemplos de aplicación**

# Ejemplos de aplicación

(TODO)

## Ejemplo 3: Detector de presencia

(TODO)

## Ejemplo 4: Sistema automático de subida y bajada de barrera

(TODO)

## Ejemplo 5: Caja fuerte con apertura con código

(TODO)

## Ejemplo 6: Alarma persistente

(TODO)

# Ejercicios propuestos (X BitPoints)

Ver los detalles de los ejercicios y las **entregas** en el menú **Archivos/Ejemplos/2-Ejercicios** de la colección de este tutorial

**Resumen**:

* **Ejercicio 25.1** (Total **x Bitpoints**): 

* **Ejercicio 25.2** (Total **x Bitpoints**): 

* **Ejercicio 25.3** (Total **x Bitpoints**): 

* **Ejercicio 25.4** (**5 Bitpoints**). Ejercicio Libre. Premiar la creatividad. **Entregar** por redes sociales o github: Pantallazos, enlaces, vídeos, etc...

# Ejercicios entregados

## Primero

### Ejercicio 25.1
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 25.2
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 25.3
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 25.4
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()


## Segundo

### Ejercicio 25.1
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 25.2
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 25.3
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 25.4
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

## Tercero

### Ejercicio 25.1
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 25.2
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 25.3
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 25.4
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()


# Autor

* [Juan González-Gómez](https://github.com/Obijuan) (Obijuan)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/logos-urjc-gsyc-peloto-jderobot.png)

# Licencia

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/attribution-share-alike-creative-commons-license.png)

# Créditos y agradecimientos

* Icon used on image [intro-01.png](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/intro-01.png) made by [Freepik](https://www.flaticon.es/autores/freepik) from [www.flaticon.com](https://www.flaticon.es/icono-gratis/carretilla-elevadora_3736)





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



