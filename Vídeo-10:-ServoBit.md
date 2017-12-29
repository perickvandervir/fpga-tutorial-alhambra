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


## Robot gusano Larby

**Larby** es un [robot modular](http://www.iearobotics.com/wiki/index.php?title=Juan_Gonzalez:Tesis) tipo gusano formado por la unión de 2 [módulos REPYZ](http://www.iearobotics.com/wiki/index.php?title=M%C3%B3dulos_REPYZ)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-10/robots-servos-01.jpg)

* https://www.youtube.com/watch?v=6I5Z70eewrg

## TODO

* Ejemplos de uso de servos:

* Robots modulares (larby, modulos gz)
* Zowi
* Bettle

# Señal de control

## TODO
* Señal general PWM (20ms) (50Hz)

* Señal en posiciones 0, 45, 90, 75, 180

# Borrador

* Señales de control de servos: PWM
* Controlador ServoBit
* Ejemplo 1: Servo y pulsador
* Ejemplo 2: Servo y corazón
* Ejemplo 3: Retardando: tortuga
* Interruptor de periféricos


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
