![]()

# Vídeo

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

Haz click en la imagen para ver el **vídeo en Youtube**

# Descripción


# Colección

**Academia-Jedi-HW-16.zip**: Colección para este tutorial. Descargar e instalar 

# Contenido

* [Introducción](#introducci%C3%B3n)
* [Sensores IR](#sensores-ir)
* [Modelos de sensores](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/VIDEO-16:-Sensores-de-Infrarrojos-(IR)#modelos-de-sensores)
* [Practicando con el sensor octopus IR](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/VIDEO-16:-Sensores-de-Infrarrojos-(IR)#practicando-con-el-sensor-octopus-ir)
   * [Conexión a la Icezum Alhambra](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/VIDEO-16:-Sensores-de-Infrarrojos-(IR)#conexi%C3%B3n-a-la-icezum-alhambra)
  * [Ejemplo 1: Encendiendo un LED al detectar presencia](#ejemplo-1-encendiendo-un-led-al-detectar-presencia)
  * [Ejemplo 2: Emitiendo pitidos al detectar objetos](#ejemplo-2-emitiendo-pitidos-al-detectar-objetos)
* Ejercicios propuestos (X Bitpoints)
* [Ejercicios entregados](#ejercicios-entregados)
* [Autor](#autor)
* [Licencia](#licencia)
* [Enlaces](#enlaces)
* [Preguntas frecuentes](#preguntas-frecuentes)

# Introducción

En este tutorial practicaremos con un sensor nuevo: el **sensor de IR digital**, de corto alcance, que nos permitirá **detectar objetos** a corta distncia, así como **distinguir** el color **negro** del **blanco** en una superficie plana. Así es como nos queda el **mapa de periféricos** que hemos tratado hasta ahora

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/perifericos-vistos.png)


# Sensores IR
Los **sensores de infrarrojos** (IR) que usaremos nos permiten detectar la **presencia** de un objeto que está **delante** de ellos, a un centímetro aproximadamente. Constan de un **emisor** y un **receptor**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/sensor-ir-01.png)

El emisor es un **LED infrarrojo**. Es un LED de los que ya conocemos, pero en vez de emitir luz visible, la emite en el **espectro infrarrojo**, que no nuestros ojos no pueden ver. El emisor está **constantemente emitiendo**, cuando el sensor está alimentado. Esto lo podemos observar mirando el sensor a través de la **cámara** de nuestro **teléfono móvil**: se puede a preciar un **color azulado/violeta**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/sensor-ir-02.png)

El receptor es un **fototransistor**, que se activa cuando recibe luz infrarroja. La **detección de objetos** se hace por **reflexión**. La luz infrarroja que está constantemente generando el emisor se **refleja** en el objeto y llega al **receptor**, que nos devuelve un **1** (objeto detectado). Si por el contrario no hay objeto, la luz infrarroja se pierde y **no** regresa al receptor. En este caso el sensor nos devuelve un **0** (Objeto no detectado)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/sensor-ir-03.png)

Estos sensores también se pueden utilizar para distinguir el **blanco** del **negro** en una superficie plana, y construir así robots que puedan por ejemplo **seguir un camino negro**. Cuando el sensor está sobre blanco, la luz del emisor se **refleja completamente**, devolviéndo un **1**. Cuando esta sobre la parte **negra**, **no hay reflexión**. El negro absorbe la luz, y no la refleja, por lo que no llega nada al receptor y devuelve un **0**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/sensor-ir-04.png)

# Modelos de sensores

Los **sensores de IR** que utilizaremos en este tutorial son **digitales**. Devuelven **0** ó **1** dependiendo de si detectan el objeto o no. Cualquier de estos valdría: (y si buscas por internet encontrarás todavía más)

| Foto  | Nombre | Descripción |
|-------|--------|-------------|
| ![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/sensor-modelo-1.png)      | [Octopus Hunt sensor](http://www.elecfreaks.com/estore/octopus-hunt-sensor.html) | Este es el modelo que estoy usando en el tutorial. Está fabricado por [Elecfreaks](http://www.elecfreaks.com/). Es el que se encuentra en los kits de robótica de BQ |
| ![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/sensor-modelo-2.jpg) | [Módulo sigue líneas mblock](https://www.makeblock.es/productos/modulo_sigue_lineas/)   |  Es el sensor del kit del [robot mbot](https://makeblock.es/productos/robot_educativo_mbot/). Incluye **2 sensores IR** en la misma placa. Hay que soldarle pines para conectar a la Icezum Alhambra  |
| ![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/sensor-modelo-3.jpg) | [TCRT5000-ir](https://www.iberobotics.com/producto/modulo-sensor-siguelineas-tcrt5000-ir/)    |  Compatible con la Icezum Alhambra. Permite también lectura analógica. Distribuido por [Iberobotics](https://www.iberobotics.com/)    |
| ![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/sensor-modelo-4.png) | [TCRT5000-IR-estrecho](https://www.iberobotics.com/producto/modulo-sensor-siguelineas-tcrt5000-ir-2/)  | Modelo estrecho. Compatible con Icezum Alhambra. Distribuido por [Iberobotics](https://www.iberobotics.com/)  |
| ![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/sensor-modelo-5.jpg) | [Sensor QTR-8RC](http://tienda.bricogeek.com/componentes/257-array-de-sensores-infrarojos-qtr-8rc-digital.html)  | Tira de **8 sensores IR**. Se puede partir en dos grupos de 2 y 6 sensores. Hay que soldarle los pines. Distribuido por [BricoGeek](http://tienda.bricogeek.com/)   |
| ![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/sensor-modelo-6.jpg)  | [Sensores IR del kit Beduino](http://www.logix5.com/roboticaeducativa/producto/beduino/) | Kit distribuido por [Logix5](http://www.logix5.com/roboticaeducativa/) |

# Practicando con el sensor Octopus IR

El sensor que usaremos para las pruebas es el [Octopus IR](http://www.elecfreaks.com/estore/octopus-hunt-sensor.html)

## Conexión a la Icezum Alhambra

La conexión del sensor a la placa Icezum Alhambra se hace igual que los sensores que hemos visto hasta ahora: mediante un **cable de tres hilos** (señal, 5v y masa)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/octopus-ir-1.jpg)

Por un lado se conecta al sensor, y por el otro a cualquiera de los **pines de datos** con alimentación de la placa (**D0** - **D13**). En esta foto está conectado a D13:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/octopus-ir-2.jpg)

¡Y ya está listo! Ahora funciona exactmente igual que un pulsador externo

## Ejemplo 1: Encendiendo un LED al detectar presencia

Vamos a probar el sensor. El circuito más sencillo posible que nos permite probarlo es el mismo que en el caso del pulsador: un **cable** que vaya directo desde el **sensor IR** a un **LED externo**. De esta forma, cuando el sensor detecte un objeto, devolverá un **1** que hará que se encienda en LED. Cuando no detecta objeto, devolverá **0** y el LED estará apagado

El **montaje** es el mostrado en la siguiente foto. El sensor está conectado a la entrada **D13**, y el LED a la salida **D12**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/Ejemplo-1-2.jpg)

El circuito en Icestudio es el siguiente. Está accesible también desde la colección **Academia-Jedi-HW-16.zip**, en el menú **Archivo/Ejemplos/1-Ejemplos/1-Senosr-IR-LED**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/Ejemplo-1-1.png)

Lo cargamos en la placa para probar. Al pasar un objeto, a una distancia de **1 cm** aproximadamete, vemos que se enciende el LED

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/Ejemplo-1-anim.gif)

# Ejemplo 2: Emitiendo pitidos al detectar objetos

Ampliamos el montaje anterior añadiendo un **zumbador** conectado a la salida **D11**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/Ejemplo-2-1.jpg)

Haremos que pite al detectar un objeto, además de encenderse el LED. El circuito en Icestudio ya lo sabemos hacer. Sería así:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/Ejemplo-2-2.jpg)

Se ha añadido un **corazón de 2Khz**, para **emitir un pitido** a esa frecuencia. Va modulado por la señal procedente del sensir IR. Cuando no hay objeto, por el sensor llega un 0 que deshabilita la señal de 2Khz, por lo que al zumbador sólo le entra una señal con todo ceros, y no suena. Al detectarse un objeto, la señal de corazón llega al zumbador y pita

Cargamos el circuito y lo probamos. Funcionará igual que en el ejemplo 1, pero ahora además **sonará un pitido** que se mantendrá mientras tengamos el objeto delante del sensor

En este **Vídeo de youtube** se puede ver un ejemplo de funcionamiento

[![Click to see the youtube video](http://img.youtube.com/vi/rdhIZm3kZ_c/0.jpg)](https://www.youtube.com/watch?v=rdhIZm3kZ_c)

Este ejemplo es muy sencillo, pero muy divertido. Suena como los **escáneres** que hay en las **cajas de los supermercados**. De hecho, cuando mi hija Alicia de 8 años vió este ejemplo por primera vez, exclamó: "¡Papi! Vamos a jugar a los supermercados" :-)

# Ejemplo 3: Pitidos con spinner

TODO

(Mismo montaje con spinner añadido)

(Vídeo en youtube)

# Comportamientos reactivos con el Icebot

TODO

# Ejemplo 4: El patito y su mamá

TODO

# Ejercicios propuestos (X BitPoints)

Ver los detalles de los ejercicios y las **entregas** en el menú **Archivos/Ejemplos/2-Ejercicios** de la colección de este tutorial

**Resumen**:

* **Ejercicio 1** (Total **x Bitpoints**): 

Alarma

* **Ejercicio 2** (Total **x Bitpoints**): 

Barrera automática

* **Ejercicio 3** (Total **x Bitpoints**): 

Icebot siguiente mama y sonando alarma al andar

* **Ejercicio 4** (**3 Bitpoints**). Ejercicio Libre. Premiar la creatividad. **Entregar** por redes sociales o github: Pantallazos, enlaces, vídeos, etc...

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



