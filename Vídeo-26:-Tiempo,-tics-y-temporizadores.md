![]()

# Vídeo

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

Haz click en la imagen para ver el **vídeo en Youtube**

# Descripción


# Colección

**Academia-Jedi-HW-26.zip**: Colección para este tutorial. Descargar e instalar 

# Contenido

* [Reloj del sistema](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-26:-Tiempo,-tics-y-temporizadores#reloj-del-sistema)
  * [Evento: Flanco de subida del sistema](#evento-flanco-de-subida-del-sistema)
* [Pulsos](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-26:-Tiempo,-tics-y-temporizadores#pulsos)
* Ejercicios propuestos (X Bitpoints)
* [Ejercicios entregados](#ejercicios-entregados)
* [Autor](#autor)
* [Licencia](#licencia)
* [Enlaces](#enlaces)
* [Preguntas frecuentes](#preguntas-frecuentes)

# Introducción

(TODO)

# Reloj del sistema

  Los **circuitos digitales** funcionan a ritmo de un **reloj**, conocido como **reloj del sistema**. Es el que define la **velocidad máxima** a la que ocurren las cosas dentro del circuito. También nos permite **medir el tiempo**. 

En la **Icezum Alhambra** el reloj del sistema es de **12Mhz**. Se encuentra situado **fuera de la FPGA** y la señal de reloj se introduce en ella por uno de sus pines, denominado **CLK**, al que tenemos acceso desde **Icestudio**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Reloj-sistema-01.png)

En icestudio, todos los componentes que tienen una entrada de reloj, **se conectan automáticamente** a este reloj del sistema. Esto se indica mediante un **cuadrado amarillo** conectado a su entrada de reloj

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Reloj-sistema-02.png)

Pero el **reloj del sistema** es un **pin** más de entrada de nuestra **FPGA**, y **lo podemos usar** como cualquier otro. También lo podemos **conectar manualmente** a las entradas de reloj de los componentes. Estos dos circuitos, que hacen parpadear un LED a 1Hz, son **equivalentes**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Reloj-sistema-03.png)

Esta es la manera de hacer la **conexión manual**. Se coloca una entrada genérica, se conecta al pin de reloj, y se selecciona la **etiqueta CLK**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Reloj-sistema-04.gif)

El reloj del sistema para nosotros es como un **corazón**, que **bombea bits** muy rápidamente. Saca unos y ceros alternativamente, a una frecuencia de **12Mhz**. O lo que es lo mismo, el **tiempo** entre dos unos consecutivos es de **83.3ns**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Reloj-sistema-05.png)

**¡Esto es muy rápido!** Cada segundo, este super corazón... **¡bombea 12 millones de 1s!**. Si hacemos un circuito capaz de realizar una operación cada vez que llega un 1 del sistema, en un segundo realizaría **12 millones de estas operaciones**. Y si colocamos **dos** de estos circuitos **en paralelo**, haríamos **24 millones de operaciones por segundo**

Si cada vez que llega un 1, pintásemos una marca en una carreta y avanzásemos 1 milímetro, ¡¡en un segundo habríamos pintado más de 12 Kilómetros de carretera!!

## Evento: flanco de subida del sistema

La señal de reloj del sistema, o en general cualquier otra señal de reloj, la representamos mediante **señales cuadradas**. Las líneas inferiores representan los ceros y las superiores los unos. El tiempo se incrementa hacia la derecha. En este ejemplo lo primero que aparece es un **1**, luego un **0**, luego 1, etc... (de izquierda a derecha)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Reloj-sistema-06.png)

El **cambio de 0 a 1** es un **evento**, conocido con el nombre de **flanco de subida**. Es el evento que usaremos como **referencia** (también podríamos usar el flanco de bajada). Se representa colocando una **flecha** en la línea de transición entre el 0 y el 1, que **apunta hacia arriba**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Reloj-sistema-07.png)

Esto nos permite **definir mejor los tiempos**. Así, el **periodo** del reloj del sistema será el **tiempo que transcurre** entre **dos flancos de subida consecutivos**. Utilizaremos una **flecha hacia arriba**, con patas, para representar estos eventos. Se llama **Flanky** 😃

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Reloj-sistema-08.png)

El **reloj del sistema** lo podemos ver, por tanto, como un **corazón** que produce **eventos de flanco de subida** de forma periódica, con **periodo T** de **83.3ns**. Vamos, que bombea Flankys 😃

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Reloj-sistema-09.png)
Para **medir tiempo** basta con **contar estos eventos**. Cada vez que llega uno, sabemos que **ha transcurrido** un tiempo igual a **83.3ns**. El funcionamiento es similar al segundero de un reloj analógico, que avanza un ángulo cada segundo, pero con unidades de tiempo más pequeñas

# Pulsos

Cuando una señal está en **reposo** (a cero), se **activa** durante un tiempo (W) y vuelve al **reposo**, decimos que se ha producido **un pulso**. Al **tiempo** que permanece a **activo** (a 1) lo denominamos **anchura del pulso**, y solemos usar la **letra W** para denominarlo

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Pulso-01.png)

Esta **propiedad** de partir del **estado inicial**, y **volver** a él, es muy importante. Por ello, la mayoría de las veces **usaremos pulsos** para comunicar los **eventos** que ocurren en nuestro circuito

El pulso también lo podemos ver como la **llegada de un flanco de subida**, y al cabo de un tiempo W, un **flanco de bajada**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Pulso-02.png)

(TODO)

# Ejercicios propuestos (X BitPoints)

Ver los detalles de los ejercicios y las **entregas** en el menú **Archivos/Ejemplos/2-Ejercicios** de la colección de este tutorial

**Resumen**:

* **Ejercicio 26.1** (Total **x Bitpoints**): 

* **Ejercicio 26.2** (Total **x Bitpoints**): 

* **Ejercicio 26.3** (Total **x Bitpoints**): 

* **Ejercicio 26.4** (**5 Bitpoints**). Ejercicio Libre. Premiar la creatividad. **Entregar** por redes sociales o github: Pantallazos, enlaces, vídeos, etc...

# Ejercicios entregados

## Primero

### Ejercicio 26.1
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 26.2
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 26.3
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 26.4
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()


## Segundo

### Ejercicio 26.1
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 26.2
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 26.3
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 26.4
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

## Tercero

### Ejercicio 26.1
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 26.2
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 26.3
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 26.4
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
