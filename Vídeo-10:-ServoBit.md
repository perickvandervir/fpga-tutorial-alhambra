![]()

# Vídeo

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

Haz click en la imagen para ver el **vídeo en Youtube**

# Descripción


# Colección

**Academia-Jedi-HW-10.zip**: Colección para este tutorial. Descargar e instalar 

# Contenido

* [Introducción a los servos](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-10:-ServoBit#introducci%C3%B3n-a-los-servos)
* [Robots y servos](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-10:-ServoBit#robots-y-servos)
  * [Garras robóticas](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-10:-ServoBit#garras-rob%C3%B3ticas)
    * [Printbot Beetle](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-10:-ServoBit#printbot-beetle)
    * [Ultimate gripper](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-10:-ServoBit#ultimate-gripper)
    * [Pinza paralela](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-10:-ServoBit#pinza-paralela)
  * [Robot Gusano Larby](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-10:-ServoBit#robot-gusano-larby)
  * [Zowi](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-10:-ServoBit#zowi)
* [Señal de control de los servos](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-10:-ServoBit#se%C3%B1al-de-control-de-los-servos)
* [Conectando servos a la Icezum Alhambra](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-10:-ServoBit#conectando-servos-a-la-icezum-alhambra)
  * [Conexion a pines de 3.3v](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-10:-ServoBit#conexi%C3%B3n-a-pines-de-33v)
  * [Conexión a pines macho de 5v con alimentación y masa](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-10:-ServoBit#conexi%C3%B3n-a-pines-machos-de-5v-con-alimentaci%C3%B3n-y-masa)
* [Controlador ServoBit](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-10:-ServoBit#controlador-servobit)
* [Ejemplo 1: moviendo un servo con el pulsador](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-10:-ServoBit#ejemplo-1-moviendo-un-servo-con-el-pulsador)
* [Ejemplo 2: Conectando dos servos](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-10:-ServoBit#ejemplo-2-conectando-dos-servos)

# Introducción a los servos

Los [Servos](https://es.wikipedia.org/wiki/Servomotor_de_modelismo) son **actuadores** que pueden estar de manera estable en una **posición** dentro de su rango, que típicamente es de **180 grados**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-10/servos-01.png)

Se usan muchísimo en la construcción de **robots educativos**, para abrir y cerrar **pinzas**, **orientar** sensores, o **mover articulaciones**. Están formados por tres partes: **cuerpo**, **cabeza** y **cable de conexión**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-10/servos-02.png)

El **cuerpo** es la parte más grande, que alberga en su interior el **motor**, la **electrónica** y los **engranajes**. La **cabeza** es la pieza que va atornillada al eje de salida, y que es la que gira con respecto al cuerpo. En inglés se llama **horn** (cuerno). El cable está formado por **tres hilos** de colores que terminan en un **conector hembra**

Hay servos de todos los tamaños y gustos. Nosotros utilizaremos tres de los más utilizados: El servo [Futaba 3003](http://www.iearobotics.com/wiki/index.php?title=Servos_Futaba_3003) o compatible, y los micro-servos **Tower-Pro SG90** y **Emax ES08A**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-10/servos-03.png)

Los **Futaba 3003** o compatibles tienen el tamaño "estándar". Son de los primeros servos que aparecieron, para aplicaciones de aeromodelismo. Los **micro-servos** son más pequeños

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-10/servos-04.png)

Cada modelo de servo incluye un **juego de cabezas** intercambiables. Se unen al eje mediante un **tornillo**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-10/servos-05.jpg)

El **cable de conexión** está formado por **3 hilos**, con un conector hembra negro al final. Los hilos son: **Masa** (GND), **alimentación** (+5v) y **señal de control**. Cada uno tiene un color diferente, y dependen del modelo de servo. El código típico, que tienen la mayoría de los servos se muestra en esta imagen:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-10/servos-06.png)

Para los microservos **Tower Pro** y **Emax**, el marrón es **GND**, el rojo la **alimentación** y el naranja la **señal de control**. En los servos **Futaba 3003** el negro es GND, el rojo Alimentacón y la señal de control es blanca 

# Robots y servos

Los servos se utilizan mucho en **robots educativos** y de **investigación**. Son perfectos para combinarlos con impresión 3D y construir robots

## Garras robóticas

Una aplicación muy sencilla y divertida es hacer diferentes **garras robóticas**, que se abran y cierren

### Printbot Beetle

Un tipo de garra muy sencilla es la que lleva el [printbot Beetle](https://github.com/bq/printbots/tree/master/Beetle), diseñado originalmente por **Jon Goitia**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-10/robots-servo-02.png)

Es una pinza tipo **insecto**, formada por 3 piezas impresas y un microservo **Emax ES08A**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-10/robots-servo-03.png)

El **dedo derecho** de la pinza está atornillado a la **cabeza** del microservo. A través de unos **dientes** transmite el movimiento al **dedo izquierdo** que está atornillado a una base que a su vez lo está al **cuerpo** del microservo

En esta **animación** se puede ver la garra en su dos posiciones extremas: abierta y cerrada

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-10/robots-servos-04.gif)

### Ultimate gripper

La [Ultimage gripper](https://github.com/bqlabs/mechatronics/tree/master/grippers/ultimate_gripper) es una garra diseñada por [Javier Isabel](https://github.com/JavierIH) para usarla en **robots humanoides**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-10/robots-servos-05.png)

Es un diseño **muy compacto**. Está formado por **3 piezas**: Dedo izquierdo, dedo derecho y base. El servo que usa es un **Futaba 3003** o compatible, y utiliza 3 **rodamientos tipo 603**

En esta **animación** se puede ver la garra en acción

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-10/robots-servos-06.gif)

### Pinza paralela

Esta es una pinza que sus dos dedos siempre permanen paralelos, ejerciendo la misma presión. La [versión original](http://www.iearobotics.com/wiki/index.php?title=Freecad:_Pinza_mecanica) la creé para mostrar el funcionamiento de este tipo de mecanismos. Posteriormente, **Javier Isabel** le añadió un microservo para abrir y cerrarla automáticamente 

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-10/robots-servos-07.png)

El diseño está creado con **FreeCAD**, y se han hecho diferentes diseños derivados, como por ejemplo [Este porta acreditaciones](http://diwo.bq.com/builds/pinza-robotica-porta-acreditaciones/). En ese enlace, además, se emplica el funcionamiento del mecanismo

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-10/robots-servos-08.gif)

Gracias a su **mecanismo del paralelogramo**, los dedos de agarre siempre permanen en paralelo, tanto si está abierta como cerrada

## Robot gusano Larby

**Larby** es un [robot modular](http://www.iearobotics.com/wiki/index.php?title=Juan_Gonzalez:Tesis) tipo gusano formado por la unión de 2 [módulos REPYZ](http://www.iearobotics.com/wiki/index.php?title=M%C3%B3dulos_REPYZ)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-10/robots-servos-01.jpg)

En este **vídeo** se puede ver su movimiento en acción, mediante un circuito que está metido en la **FPGA**

[![Click to see the youtube video](http://img.youtube.com/vi/6I5Z70eewrg/0.jpg)](https://www.youtube.com/watch?v=6I5Z70eewrg)

Es un ejemplo de [Una configuración mínima](http://www.iearobotics.com/wiki/index.php?title=MiniCube). Con sólo 2 módulos con conexión en vertical logramos generar movimiento. El módulo básico es el [REPYZ](http://www.iearobotics.com/wiki/index.php?title=M%C3%B3dulos_REPYZ), que tiene un **Futaba 3003** en su interior

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-10/robots-servos-09.jpg)

## Zowi

Los servos se utilizan mucho en robots educativos, para implementar sus articulaciones. Un ejemplo es el robot [Zowi](https://github.com/JavierIH/zowi), creado por **Javier Isabel**. Utiliza cuatro servos **Futaba 3003** para el movimiento de sus piernas

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-10/robot-servos-10.png)

Es un robot **humaniforme**, que aunque sólo tiene 4 servos, puede realizar una gran cantidad de movimientos diferentes. En esta [Lista de reproducción](https://www.youtube.com/watch?v=b2puPzjQ2Bo&list=PLmnz0JqIMEzUKrrcKhBNfWbb1Th0o9tET) se pueden ver muchos de los movimientos que implementé usando la [biblioteca de osciladores ardusnake](http://www.iearobotics.com/wiki/index.php?title=ArduSnake:_Arduino_Modular_Snake_Robots_Library). Esta biblioteca la creé a partir de todo lo desarrollado en mi [tesis doctoral](http://www.iearobotics.com/wiki/index.php?title=Juan_Gonzalez:Tesis)

[![Click to see the youtube video](http://img.youtube.com/vi/b2puPzjQ2Bo/0.jpg)](https://www.youtube.com/watch?v=b2puPzjQ2Bo&list=PLmnz0JqIMEzUKrrcKhBNfWbb1Th0o9tET)

# Señal de control de los servos

Para llevar la cabeza del servo a una **posición** determinada hay que enviar una **señal de control especial**. Se trata de un **pulso de 5v**, de anchura variable, que se envía periódicamente, cada **20ms** (frecuencia de 50Hz)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-10/servo-pwm-01.png)

El **ancho del pulso** es el que determina la **posición** a la que se moverá el servo. Los valores dependen del modelo de servo, pero típicamente un **pulso de 1ms** lleva el servo al **extremo** derecho y uno de **2ms** al izquierdo. Valores entre 1ms y 2ms lo posicional linealmente entre **0** y **180 grados**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-10/servo-pwm-02.png)

Los **valores exactos dependen del modelo de servo utilizado**. Lo importante es saber que el **ángulo** en el que se posiciona el servo es **directamente proporcional al tiempo del ancho del pulso**, y que este pulso se tiene que repetir periódicamente. Si se deja de repetir, el servo deja de ejercer fuerza y se puede mover con la mano a cualquier posición

# Conectando servos a la Icezum Alhambra

Los servos se pueden conectar directamente a los **pines macho de 5v**, con alimentación y masa, y también a los de **3.3v**

## Conexión a pines de 3.3v

Aunque la **señal de control** de los servos es de **5v**, funcionan perfectamente si se conectan a los pines de **3.3v** (GPx). Un ejemplo de conexionado de un servo al pin GP0 de 3.3v se muestra en este **esquema de Fritzing**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-10/servo-alhambra-01.png)

Se necesitan **3 cables macho-hembra**. La **señal de control** se conecta directamente al **pin de 3.3v** (GP0 en esta imagen). La señal de **5v** se lleva a cualquiera de los **pines machos de 5v**, de color rojo. Y lo mismo con la **señal GND**, que se conecta a cualquiera de los **pines macho de GND**, de color negro
Y esta es una foto de la **conexión real** a la Icezum Alhambra

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-10/servos-alhambra-02.jpg)

Las **ventajas** de conectar los servos a través de los pines de **3.3v** es que la señal de control **sale directamente de la FPGA**, sin pasar por ningún otro sitio. La desventaja es que el servo no se conecta directamente, sino que hay que hacerlo a través de **cables auxiliares**

## Conexión a pines machos de 5v con alimentación y masa

El **conector hembra del servo**, de tres hilos, lo conectamos a cualquiera de los **3 pines machos**, respectando la polaridad. En este ejemplo lo hemos conectado al **pin D13**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-10/servos-alhambra-03.png)

Y esta es la foto de la **conexión real**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-10/servos-alhambra-04.jpg)

con los **detalles** de la conexión del conector hembra:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-10/servos-alhambra-05.jpg)

La ventaja de esta conexión es que es **directa**: basta con **enchufar el servo directamente**, sin usar otros cables. Esto es muy cómodo. Sin embargo, la señal de control de 3.3v que sale de la FPGA pasa primero por un **conversor de nivel de 3.3v a 5v** antes de llegar al servo. Y estos elementos de conversión son **muy vulnerables al ruido de alimentación**, de forma que pueden producir **pulsos espúreos** al arrancar/frenar los servos, notándose efectos extraños transitorios. Esto dependerá del tipo de servo usado y es un efecto un tanto **aleatorio**. Si se observa que el servo tiembla ligeramente cuando debería estar fijo en una posición, posiblemente será debido al efecto de los conversores. En ese caso, lo mejor es conectarlo directamente a los pines de 3.3v (puede haber efectos provocados por otras causas. Al probar con los pines de 3.3v eliminamos una de las posibles fuentes de problemas)

# Controlador ServoBit

Los servos los podemos colocar en **cualquier posición** dentro de su rango de 180 grados. Sin embargo, vamos a empezar por lo más sencillo: haremos que los servos vayan sólo a **dos posiciones**, separadas un ángulo de **90 grados**. Usaremos el **controlador mínimo**: un bloque que tiene **una única entrada** y que según su valor se mueve el servo a una posición (0) o a otra (1). Es el componente que llamamos **ServoBit**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-10/ejemplo-1-servo-01.png)

Al recibir un bit a **0** por su entrada, se posiciona en la **derecha**. La posición absoluta depende de cómo hayamos colocado su cabeza. Al recibir un **1** se mueve 90 grados en sentido antihorario

Cada **modelo de servo** tiene unas **características** de la **señal de control** diferentes, por eso en la colección **Academia-Jedi-HW-10.zip** encontraremos tres controladores Servobits, uno para cada tipo de servo: **Futaba 3003**, **Emas ES08A** y **TowerPro SG-90**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-10/ejemplo-1-servo-02.png)

La **mayoría de los servos** con compatibles con estos. Más adelante aprenderemos a crear **nuestros propios controladores de servos**, para adaptarlos a los servos que tengamos. Pero de momento vamos a seguir aprendiendo cosas usando alguno de estos servos

# Ejemplo 1: Moviendo un servo con el pulsador

Empezamos por el ejemplo más **sencillo**: Un **servo** que se mueve de una posición a otra según cómo tengamos apretado el **pulsador SW1**. Utilizaremos un microservo **EMAX ES08A** conectado al **pin D0**

Este circuito tiene **una entrada** y **una salida**. Comenzamos colocándolas, como ya sabemos. Ponemos como etiquetas **PULSADOR** y **SERVO**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-10/ejemplo-1-servo-03.png)

Ahora colocamos el controlador ServoBit para el servo EMAX ES08A, que es el que usaremos. Se encuentra en el menú **Varios/Servos/EMAX-ES08A/ServoBit-90**. Asegurarse de que tenemos instalada y seleccionada la **colección del tutorial 10** (Academia-Jedi-HW-10.zip)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-10/ejemplo-1-servo-04.png)

**Ponemos** el bloque y lo **conectamos** a los bloques de entrada y salida anteriores

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-10/ejemplo-1-servo-05.png)

**Conectamos** el servo al pin **D0** y **cargamos** el circuito

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-10/ejemplo-1-servo-06.jpg)

El servo se pondrá en la **posición 0**. La cabeza no tiene porqué estar en la posición que se indica en la foto, ya que depende de la **orientación** con la que se haya colocado **inicialmente**

Al dejar el **pulsador apretado**, el servo se mueve 90 grados en sentido antihorario, colocándose en su **nueva posición**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-10/ejemplo-1-servo-07.jpg). 

Al **soltar el pulsador**, el servo vuelve a su **posición original**. En esta **animación** se muestra su funcionamiento

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-10/ejemplo-1-servo-08.gif)

El **circuito generado** es como el mostrado en siguiente diagrama:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-10/ejemplo-1-servo-09.png)

El **pulsador SW1** está conectado **físicamente** a un pin de la FPGA, como ya sabemos. Dentro de la FPGA está sintetizado nuestro circuito, que recibe los **valores del pulsador** como **entrada**, y genera de **salida** la **señal de control del Servo**, que físicamente se envía por una pista hasta el **conector D0**, donde está enchufado el **servo**

# Ejemplo 2: Conectando dos servos 

Conectaremos **dos microservos Emax-ES08A** y haremos algunos experimentos con ellos

## Experimento 1: Dos servos iguales en fase

# Ejemplo 3: Conectando tres servos

# Ejemplo 5: Movimiento automático (Corazón)

# Ejemplo 6: Movimiento retardado (Tortuga)

# Ejercicios propuestos (X BitPoints)

Ver los detalles de los ejercicios y las **entregas** en el menú **Archivos/Ejemplos/2-Ejercicios** de la colección de este tutorial

**Resumen**:

* **Ejercicio 1** (Total **x Bitpoints**): 

* **Ejercicio 2** (Total **x Bitpoints**): 

* **Ejercicio 3** (Total **x Bitpoints**): 

* **Ejercicio 4** (**2 Bitpoints**). Ejercicio Libre. Premiar la creatividad. **Entregar** por redes sociales o github: Pantallazos, enlaces, vídeos, etc...

# Ejercicios entregados

## Primero


## Segundo

## Tercero


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

# FAQs

* **¿Dónde puedo conseguir la placa Icezum Alhambra?**

Pueden conseguir una desde [Alhambrabits](https://alhambrabits.com/buy/)

* **¿Dónde puedo comprar material electrónico?**. Hay muchos sitios. Uno muy bueno es [Bricogeek](http://tienda.bricogeek.com/)

* **¿Cómo aprendo a manejar github?**

Hay mucha información en internet. En su momento hice este Tutorial: [Github y FreeCAD](http://www.iearobotics.com/wiki/index.php?title=Tutorial:_Github_y_Freecad) para enseñar a manejarlo. Los ejemplos están hechos con ficheros de FreeCAD, sin embargo, lo que se enseña es genérico. También vale para las entregas de los ejercicios del tutorial de Electrónica digital para makers

* **Los pulsadores de la Icezum Alhambra no me funcionan**

Eso es debido a que se han metido restos de flux y no hacen buen contacto. En el apartado [¡No me funcionan los pulsadores!](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-9:-Pulsadores-y-entradas#no-me-funcionan-los-pulsadores) del Tutorial 9 se indica cómo solucionarlo fácilmente
