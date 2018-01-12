![]()

# Vídeo

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

Haz click en la imagen para ver el **vídeo en Youtube**

# Descripción


# Colección

**Academia-Jedi-HW-11.zip**: Colección para este tutorial. Descargar e instalar 

# Contenido

* [Introducción](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-11:-Puerta-AND.-Habilitando-circuitos#introducci%C3%B3n)
* [La puerta AND](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-11:-Puerta-AND.-Habilitando-circuitos#la-puerta-and)
* [Tabla de verdad](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-11:-Puerta-AND.-Habilitando-circuitos#tabla-de-verdad)
* [Ejemplo 1: Pulsadores y puerta AND](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-11:-Puerta-AND.-Habilitando-circuitos#ejemplo-1-pulsadores-y-puerta-and)

# Introducción

Vamos a aprender a manejar un elemento nuevo que nos permite **manipular bits**: la puerta **AND**. En realidad ya la conocemos, del juego del **circuit Scramble**. En el **nivel 1** había **3** puertas AND. Nos fijamos sólo en una: la que está conectada a los **dos pulsadores** de la izquierda

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-11/Circuit-scramble-N1-00.png)

Las puertas AND tiene **dos entradas** y **una salida**. Inicialmente, los botones están **sin pulsar**, por lo que por las **entradas** están a **0**. Y la salida también a **0**

Al **activar el pulsador**, una de las entradas se pone a **1**, pero la otra sigue estándo a **0**, por lo que la **salida** también está a **0**. No se activa

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-11/Circuit-scramble-N1-01.png)

Al **activar el segundo pulsador**, se introduce también un **1** por la segunda y **entrada** y ahora sí, **la puerta AND se abre** y sale un **1** por la **salida**. Decimos que **la puerta se ha activado**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-11/Circuit-scramble-N1-02.png)

En esta **animación** vemos lo que ocurre en **todos los casos posibles**: Ningúna entrada activada, sólo la de la izquierda, las dos dos y sólo la de la derecha

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-11/Circuit-scramble-anim.gif)

El **funcionamiento** es fácil de intuir: sólo cuando están **activas las dos entradas**, la **salida se activa**. De lo contrario permanecerá desactivada (0). O visto de otra manera: siempre que alguna entrada esté desactivada (0), la salida estará desactivada (0)

## La puerta AND

La **AND** es una de las tres **puertas lógicas básicas**, que nos permiten **manipular** y **combinar bits**. El **símbolo** usado para su representación en los circuitos digitales es este:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-11/puerta-and-01.png)

Aunque la palabra AND se omite. En los bloques que usamos en Icestudio la mantendremos para que sea más fácil reconocerla

La puerta AND tiene **dos entradas** y **una salida**. La manera de describir su funcionamiento es mostrando su **respuesta** a **todas las posibles entradas**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-11/puerta-and-02.png)

Cuando llega a un 1 por una entrada, decimos que **la entrada está activada**, y cuando sale un 1 decimos que **la puerta AND se activa**. Observando todos los casos, vemos que **la puerta AND se activa** cuando su **entrada superir está activada** Y su e**ntrada inferior también**. La operación que realiza es un "Y", y su interpretación es: "Activo la salida si esto está activado Y esto está activado"

# Tabla de verdad

El **funcionamiento** de las **puertas lógicas**, así como el de los **circuitos combinaciones** sencillos (que veremos más adelante), se describen mediante **tablas de verdad**. Son tablas en las que se pone cuál es la **salida del circuito** ante **todas las posibles entradas**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-11/tabla-verdad-01.png)

En una puerta AND con dos entradas, sólo hay **4 combinaciones posibles** de las entradas, por eso la tabla tiene **4 filas**. En la **izquierda** están las **entradas** y a la **derecha** la **salida**

# Ejemplo 1: Pulsadores y puerta AND

Para empezar a practicar con puertas And vamos a crear la versión **Hola mundo**: conectaremos los **dos pulsadores** de la Icezum Alhambra, **SW1** y **SW2**, a las **entradas** de una puerta **AND**, y su **salida** al **LED 0**

Colocamos **dos bloques de entrada** en la parte izquierda, y **un bloque salida** en la derecha, como ya sabemos hacer

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-11/ejemplo-1-and-01.png)

La puerta AND se encuentra en el menú **Puertas/and**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-11/ejemplo-1-and-02.png)

Seleccionamos las puerta AND y la **colocamos**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-11/ejemplo-1-and-03.png)

Ahora **ponemos los cables**. Ya tenemos nuestro hola mundo listo

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-11/ejemplo-1-and-04.png)

Lo **cargamos** en la placa para probarlo. Inicialmente, como están los dos pulsadores sin apretar, el **LED 0 estará apagado**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-11/ejemplo-1-and-05.png)

Si apretamos el **pulsador izquierdo**, el LED 0 seguirá estando **apagado**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-11/ejemplo-1-and-06.png)

y lo mismo si sólo apretamos el **pulsador derecho**: el LED 0 estará **apagado**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-11/ejemplo-1-and-07.png)

**Sólo** cuando apretamos el pulsador **izquierdo** **Y** el **derecho**, el LED se **enciende**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-11/ejemplo-1-and-08.png)


  -animación


# TODO  

-Ejemplo 2: Habilitando / Deshabilitando una señal  
  -Exp1: Partimos de circuito con corazon 4Hz y led.  Añadimos un pulsador para habilitar/deshabilitara
     (Animación)  
   -Funcionamiento de la habilitación (con animación)  
  -Exp2: Puertas not para cambiar estado inicial LED  
  -Exp3: comportamiento contrario (not antes de la AND)  

-Ejemplo 3: Modulación. Emisión periódica de ráfagas  

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
* [Printbot Beetle](https://github.com/bq/printbots/tree/master/Beetle)
* [Ultimate Gripper](https://github.com/bqlabs/mechatronics/tree/master/grippers/ultimate_gripper)
* [Pinza paralela](http://www.iearobotics.com/wiki/index.php?title=Freecad:_Pinza_mecanica)
* [Robot Educativo Zowi](https://github.com/JavierIH/zowi)
* [Qué es PWM y para qué sirve](https://www.rinconingenieril.es/que-es-pwm-y-para-que-sirve/). Entrada en el bloq de **Rincón Ingenieril**

# FAQs

* **¿Dónde puedo conseguir la placa Icezum Alhambra?**

Pueden conseguir una desde [Alhambrabits](https://alhambrabits.com/buy/)

* **¿Dónde puedo comprar material electrónico?**. Hay muchos sitios. Uno muy bueno es [Bricogeek](http://tienda.bricogeek.com/)

* **¿Cómo aprendo a manejar github?**

Hay mucha información en internet. En su momento hice este Tutorial: [Github y FreeCAD](http://www.iearobotics.com/wiki/index.php?title=Tutorial:_Github_y_Freecad) para enseñar a manejarlo. Los ejemplos están hechos con ficheros de FreeCAD, sin embargo, lo que se enseña es genérico. También vale para las entregas de los ejercicios del tutorial de Electrónica digital para makers

* **Los pulsadores de la Icezum Alhambra no me funcionan**

Eso es debido a que se han metido restos de flux y no hacen buen contacto. En el apartado [¡No me funcionan los pulsadores!](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-9:-Pulsadores-y-entradas#no-me-funcionan-los-pulsadores) del Tutorial 9 se indica cómo solucionarlo fácilmente

* **¿Dónde puedo encontrar más información sobre las señales PWM?**

Echa un vistazo a [este post de Rincón Ingenieril](https://www.rinconingenieril.es/que-es-pwm-y-para-que-sirve/) sobre el tema



