![]()

# Vídeo

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

Haz click en la imagen para ver el **vídeo en Youtube**

# Descripción


# Colección

**Academia-Jedi-HW-27.zip**: Colección para este tutorial. Descargar e instalar 

# Contenido

* [Contadores](#contadores)
* [Contando tics](#contando-tics)
  * [Ejemplo 1: Contando las pulsaciones de un botón](#ejemplo-1-contando-las-pulsaciones-de-un-bot%C3%B3n)
  * [Ejemplo 2: Inicializando el contador](#ejemplo-2-inicializando-el-contador)
  * [Ejemplo 3: Contando en decimal](#ejemplo-3-contando-en-decimal)
  * [Ejemplo 4: Notificando el overflow](#ejemplo-4-notificando-el-overflow)
  * [Ejemplo 5: Cambiando el módulo del contador](#ejemplo-5-cambiando-el-m%C3%B3dulo-del-contador)
  * [Ejemplo 6: Contador de 0 a 9](#ejemplo-6-contador-de-0-a-9)
* [Encadenando contadores](#encadenando-contadores)
  * [Ejemplo 7: Dos contadores de 2-bits encadenados](#ejemplo-7-dos-contadores-de-2-bits-encadenados)
  * [Ejemplo 8: Contador hexadecimal de 4 bits, encadenando dos de 2-bits](#ejemplo-8-contador-hexadecimal-de-4-bits-encadenando-dos-de-2-bits)
* Ejercicios propuestos (X Bitpoints)
* [Ejercicios entregados](#ejercicios-entregados)
* [Autor](#autor)
* [Licencia](#licencia)
* [Enlaces](#enlaces)
* [Preguntas frecuentes](#preguntas-frecuentes)

# Contadores

Los **contadores** son unos componentes **esenciales**, que se utilizan muchísimo. Con ellos hacemos otros elementos, como **temporizadores**, **unidades de PWM**, **controladores**... y también nos permiten **direccionar memorias** o **recorrer tablas**, entre otras muchas cosas

Los contadores **cuentan tics**. Existen de muchos tipos. Los que nosotros utilizaremos en este tutorial son **contadores ascendentes**, que parten desde **cero** y suman **una unidad** a la cuenta cada vez que llega un tic. Este es el **bloque** que utilizaremos

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/counter-01.png)

Por la entrada **cnt**, llegan los **tics** que queremos contar. La cuenta actual sale por el **bus** de la derecha, de **N** bits. Por la **salida ov** se emite un tic para indicar un **evento de desbordamiento**: el contador ha llegado a la **cuenta máxima** y comienza desde cero. Con la **entrada rst** ponemos el contador otra vez a 0. 

Como **parámetro** se introduce el **módulo del contador**: la cuenta máxima, que una vez alcanzada hace que vuelva a comenzar desde cero (provocando un overflow). Si no se indica ninguno, se toma el **su valor máximo** (2 elevado al número de bits del contador)

En esta **animación** se mustra el funcionamiento de un **contador de 2 bits**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/counter-02.gif)

# Contando tics

Los **contadores** cuentan los **tics** que reciben por su *entrada cnt**. Nos familiarizaremos con ellos usando como ejemplo el contador más sencillo: uno de **2 bits**, como el de la animación anterior. Realiza la cuenta 0,1,2,3 y en el cuarto tic vuelve a comenzar desde 0

## Ejemplo 1: Contando las pulsaciones de un botón

Comenzamos con un ejemplo de **contar** las veces que **apretamos un pulsador**, y mostramos la cuenta en **2 LEDs** externos. La entrada de **reset** la dejamos a 0. El **circuito** es el siguiente:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/counter-03.png)

Y el **montaje** se muestra en esta foto. El LED **amarillo** es el de menor peso (LED 0), y el **rojo** el de mayor (LED 1)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/counter-04.png)

Lo **cargamos** y lo **probamos**. ¡Nuestro primer contador está funcionando!. Efectivamente, al apretarse la cuarta vez, el contador vuelve a 0

[![Click to see the youtube video](http://img.youtube.com/vi/3W57NzJkwHo/0.jpg)](https://www.youtube.com/watch?v=3W57NzJkwHo)

## Ejemplo 2: Inicializando el contador

El contador **comienza a contar** desde **0**. Es el valor que tiene al alimentar el circuito. A partir de ahí, su valor dependerá de los **tics** que se hayan recibido por su **entrada cnt**. Si en un momento determinado queremos que vuelva a su valor inicial de 0, hay que poner a **1** su **entrada rst**

Este ejemplo es igual que el anterior, pero hemos conectado la entrada **rst** al **pulsador SW1**. De esta forma, cuando se **apriete**, enviará un 1 y el contador se **inicializará**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/counter-05.png)

Lo **cargamos** y lo **probamos**. En cuanto se aprieta el **reset**, la cuenta se pone a **0** y los LEDs se apagan

[![Click to see the youtube video](http://img.youtube.com/vi/SdsyM3bqprc/0.jpg)](https://www.youtube.com/watch?v=SdsyM3bqprc)

## Ejemplo 3: Contando en decimal

Si conectamos un **decodificador** para **display de 7 segmentos** a la salida del contador, veremos la cuenta en **dígitos decimales**, lo cual es mucho más fácil de leer :-) Usamos el **DisplayBit2**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/counter-06.png)

El **montaje** es el mismo de los ejemplos anteriores, pero añadiendo el **display de 7 segmentos**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/counter-07.png)

Lo **cargamos** y lo **probamos**. Ahora se ven los **dígitos 0**, **1**, **2** y **3** al **apretar** el pulsador sucesivamente.  También vemos la **cuenta en binario** en los LEDs inferiores. Al apretar el **reset** vuelve a **0**.

[![Click to see the youtube video](http://img.youtube.com/vi/3HFkcehVeyM/0.jpg)](https://www.youtube.com/watch?v=3HFkcehVeyM)

### Ejemplo 4: Notificando el overflow

Cada vez que el **contador da la vuelta** y comienza de desde **cero**, se emite el **evento de overflow**, que es un **tic**. Lo podemos capturar con un **biestable RS** y notificarlo en un **LED**. Este es el **circuito**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/counter-08.png)

Se ha añadido un **pulsador** para **borrar la notificación**. El **LED rojo** se usa para mostrar la **notifición**. El resto del **montaje** es **igual** que el del ejemplo 3

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/counter-09.png)

Lo **cargamos** y lo **probamos**. El desbordamiento se produce cuando el contador vale 3 y se aprieta el pulsador. En ese momento se **activa el LED** y el contador pasa a valer **0**. O lo que es lo mismo, el LED se enciende cuando se ha **pulsado 4 veces** el botón, partiendo del estado de reposo (0)

[![Click to see the youtube video](http://img.youtube.com/vi/AQFVeJZapBg/0.jpg)](https://www.youtube.com/watch?v=AQFVeJZapBg)

### Ejemplo 5: Cambiando el módulo del contador

El contador que hemos usado en todos los ejemplos es de **2 bits**. Esto significa que **sólo puede representar 4 números** (2 elevado a 2): 0, 1, 2 y 3. Al recibir el cuarto tic vuelve a comenzar desde cero. Se trata de lo que llamamos un contador **módulo 4**: sólo puede contar como máximo 4 tics (y vuelve a empezar)

El **módulo del contador** lo podemos **cambiar** con el **parámetro** superior. En este ejemplo se muestra el mismo circuito del ejemplo 4, pero se ha cambiado el módulo para que sea 3. Es un **contador módulo 3**. Por ello ahora sólo cuenta 3 tics, y vuelve a comenzar. La cuenta que hace es: 0,1 y 2.

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/counter-10.png)

Lo **cargamos** y lo **probamos**. Comprobamos que ahora efectivamente el contador llega hasta 2 y con la siguiente pulsación vuelve a 0 y se activa la **notificación de desbordamiento**

[![Click to see the youtube video](http://img.youtube.com/vi/Bf8JTTj89E8/0.jpg)](https://www.youtube.com/watch?v=Bf8JTTj89E8)

## Ejemplo 6: Contador de 0 a 9
 
Ya conocemos todos los secretos de los contadores. Ahora los aplicaremos para hacer más ejemplos. ¿Cómo podemos hacer un contador que cuente en **decimal**, desde el **0** hasta el **9** y vuelva a empezar?

Para representar los números del 0 al 9 (10 en total), necesitamos usar un **contador de 4 bits**. Como queremos que la cuenta sea del **0** al **9**, el contador será **módulo 10**. Partimos del ejemplo anterior y cambiamos el **decodificador del 7 segmentos**, el contador y el módulo:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/counter-11.png)

Lo **cargamos** y lo **probamos**. Ahora cuenta desde el **0** hasta el **9**. Y al apretar el pulsador por **décima vez** vuelve a 0 y se activa la **notificación de desbordamiento**

[![Click to see the youtube video](http://img.youtube.com/vi/_5SDIPNTLAo/0.jpg)](https://www.youtube.com/watch?v=_5SDIPNTLAo)

# Encadenando contadores

Los **contadores** los podemos considerar también como **componentes generadores de tics**, que los emiten por su salida de **overflow** (ov). Esto permite conectar la salida de overflow de un **contador fuente** a la entrada **cnt** del **contador destino**. Cada vez que el **contador fuente** se desborde, el **contador destino** se incrementa

En esta **animación** se muestra un ejemplo de **dos contadores** de 2 bits **encadenados**. El **contador fuente** se va incrementando cada vez que llegan tics (no se muestran en la animación). Al desbordarse **emite un tic** que incrementa el **contador destino**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/encadenamiento-01.gif)

A su vez, el **contador destino** emite otro **tic de overflow** al llegar a 4. Esto permite **encadenarlo** con otro **elemento**

## Ejemplo 7: Dos contadores de 2-bits encadenados

En este ejemplo **encadenamos** dos **contadores** de **2-bits**, igual que en la animación anterior. El **contador 1** muestra su cuenta en **binario**, en dos LEDs mientras que el **contador 2** lo hace en un **display de 7 segmentos**. Cada vez que el contador 1 cuenta 4 pulsaciones de botón, se incrementa el contador 2

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/encadenamiento-02.png)

En el montaje se incluyen los **dos LEDs** para mostrar la **cuenta binaria** del **contador 1**, el **pulsador** para emitir tics, y el **display de 7 segmentos** para mostrar la cuenta del **contador 2**, en decimal

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/encadenamiento-03.png)

Lo **cargamos** y lo **probamos**. En este **vídeo de youtube** se muestra su funcionamiento:

[![Click to see the youtube video](http://img.youtube.com/vi/f75ZNZluRVk/0.jpg)](https://www.youtube.com/watch?v=f75ZNZluRVk)

## Ejemplo 8: Contador hexadecimal de 4 bits, encadenando dos de 2 bits

El **encadenamiento** de contadores lo podemos usar para crear un **contador de mayor número de bits**. Como ejemplo, vamos a crear un **contador hexadecimal**, de **4 bits**, a partir de **dos contadores** de 2 bits

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/encadenamiento-04.png)

La **salida ov** del **contador 1** la unimos a la **entrada cnt** del **contador 2**. Concatenamos las salidas de ambos contadores, siendo la del **contador 1** la de **menor peso**. Estos **4 bits** los llevamos al **decodificador de 7 segmentos hexadecimal**. La salida del contador 1, además, la mostramos en dos LEDs

Lo **cargamos** y lo **probamos**:

(vídeo)

Se podría haber hecho lo mismo usando directamente un **contador de 4 bits**. Sin embargo, es útil usar la concatenación para construir otros contadores que no estén disponibles, así como usar la **señal de overflow** del contador de menor peso para activar alarmas, señales o comunicarse con otros circuitos

## Ejemplo 9: Contando pulsaciones triples (triple clicks)

(TODO)

# Contando objetos

* Vueltas del spinner

# Cuentas automáticas

* Segundero
* Minutero

# Recorriendo tablas

* Secuencia en los LEDs
* Texto en el 7-segmentos
* Animación en 7-segmentos
* Gravedad??




(TODO)

# Ejercicios propuestos (X BitPoints)

Ver los detalles de los ejercicios y las **entregas** en el menú **Archivos/Ejemplos/2-Ejercicios** de la colección de este tutorial

**Resumen**:

* **Ejercicio 27.1** (Total **x Bitpoints**): 

* **Ejercicio 27.2** (Total **x Bitpoints**): 

* **Ejercicio 27.3** (Total **x Bitpoints**): 

* **Ejercicio 27.4** (**5 Bitpoints**). Ejercicio Libre. Premiar la creatividad. **Entregar** por redes sociales o github: Pantallazos, enlaces, vídeos, etc...

# Ejercicios entregados

## Primero

### Ejercicio 27.1
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 27.2
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 27.3
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 27.4
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()


## Segundo

### Ejercicio 27.1
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 27.2
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 27.3
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 27.4
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

## Tercero

### Ejercicio 27.1
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 27.2
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 27.3
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 27.4
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