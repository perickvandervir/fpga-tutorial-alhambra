![]()

En construcción...

# Vídeo

En construcción...

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

Haz click en la imagen para ver el **vídeo en Youtube**

# Descripción

TODO

# Colección

**Academia-Jedi-HW-21.zip**: Colección para este tutorial. Descargar e instalar 

# Contenido

* [Introducción](#introducci%C3%B3n)
  * [Puertos](#puertos)
  * [Pines](#pines)
  * [Diseño jerárquico](#dise%C3%B1o-jer%C3%A1rquico)
* [Bloques sin puertos](#bloques-sin-puertos)
  * [Pegatinas](#pegatinas)
  * [Bloque1.ice: Creando un bloque de texto](#bloque1ice-creando-un-bloque-de-s%C3%B3lo-texto)
  * [Bloque2.ice: Añadiendo más información](#bloque2ice-a%C3%B1adiendo-m%C3%A1s-informaci%C3%B3n)
  * [Bloque3.ice: Añadiendo iconos](#bloque3ice-a%C3%B1adiendo-iconos)
* [Bloques con puertos](#bloques-con-puertos)
* Ejercicios propuestos (X Bitpoints)
* [Ejercicios entregados](#ejercicios-entregados)
* [Autor](#autor)
* [Licencia](#licencia)
* [Enlaces](#enlaces)
* [Preguntas frecuentes](#preguntas-frecuentes)

# Introducción

En el [tutorial 18](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-18:-Bloques-con-par%C3%A1metros) vimos que existen dos **técnicas** para hacer **circuitos complejos**: la **parametrización** y la **composición**. Nos vamos a centrar en esta última. Aprenderemos a construir **nuestros propios bloques** a partir de otros bloques que ya conocemos. 

## Puertos

Las entradas y las salidas de los **bloques** las denominamos **puertos**.  Los **puertos de entrada** son los puntos donde **entra** la información al bloque. Los **puertos de salida** son los puntos donde la información **sale** del bloque. En Icestudio, los puertos de entrada se colocan siempre en la izquierda del bloque, y los de salida en la derecha. El **bloque** que representa una **puerta AND** tiene 2 puertos de entrada y uno de salida

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/intro-01.png)

Los puertos tienen un **nombre** y un **tamaño** en bits. El nombre es **opcional** cuando se trata de **puertos de un bit**, como en el ejemplo de la puerta AND, pero se pone siempre cuando son de más de coun bits (buses). Además de los puertos, los bloques de icestudio tienen **parámetros**, en su **parte superior**. También tienen un nombre, que es opcional 

Este **bloque comecocos** es un **ejemplo** que tiene dos **parámetros de entrada**, uno con nombre, **p1**, y otro sin nombre. Tiene **3 puertos de entrada**, uno de 1 bit, sin nombre, otro de 1 bit (a),y uno de 8 bits (i). Tiene también **3 puertos de salida**, de un bit, sin nombre y con nombre (b), y de 4 bits (o)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/intro-02.png)

## Pines

Los **pines** son los **puntos físicos** por donde **entra la información** a nuestro circuito en la FPGA, y por donde se **envían las respuestas** de salida. Son **puertos** que están **asociados a una pata de la FPGA**

Los **pines** son de **1 bit** y se **conectan** a los **puertos de 1 bit** de otros bloques mediante **cables**. Pueden tener un **nombre** opcionalmente. En icestudio, los **pines de entrada** se ponen en la izquierda (su puerto está en la derecha) y los **pines de salida** se colocan a la derecha (su puerto está en la izquierda). Como ya vimos en el [tutorial 20](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-20:-Buses-y-n%C3%BAmeros), varios pines se pueden **agrupar** formando un **bloque**, que se conecta a otros bloques mediante un **bus**

En este **ejemlo** se ha colocado el bloque **comecocos** anterior, y se han conectado sus puertos a pines, usando cables y buses

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/intro-03.png)

Este circuito se **sintetiza en la FPGA**. Si pudiésemos ver la FPGA por dentro, veríamos algo similar a esto, donde los **puertos del comecocos** están conectados a **pines físicos de la FPGA**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/intro-04.png)

## Diseño jerárquico

**Combinando** los bloques existentes, y **asignando** valores a sus **parámetros**, construimos **nuevos bloques**, creando una **jerarquía**. Vamos a echar un vistazo al **bloque constante 255**, que representa al número 255. Tiene un **único puerto de salida**, de 8 bits

Si hacemos **doble click** en este bloque para ver cómo está hecho, veremos que está formado por un **bloque constante genérico**, al que se le pasa como **parámetro** el valor **255**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/intro-05.gif)

Cuando hablamos de **bloque** a secas, nos referiremos a la **apariencia del bloque**, visto desde fuera: su icono, puertos y parámetros. Y por otra parte tenemos la **implementación del bloque**, que es su interior. Cómo está **construido**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/intro-06.png)

En la **implementación** del bloque de la constante 255, vemos que el puerto de salida de 8 bits queda definido mediante un **bloque verde**, que tiene el nombre del puerto en su interior. Es la forma de **definir los puertos** en los bloques, y lo veremos en las siguientes secciones

Este es otro **ejemplo**, en el que se ha creado una **puerta AND de 3 entradas** a partir de dos puertas AND de dos entradas

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/intro-07.png)

La puerta tiene en total **4 puertos**, 3 de entrada y uno de salida, que no tienen nombres. Por eso, en su **implementación**, se han colocado **4 bloques verdes**, que **definen** sus **puertos**

# Bloques sin puertos

Como ya vimos en el [tutorial 5](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-5:-Colecciones-en-Icestudio), existen **bloques sin puertos**. Su misión es la **documentación**, o la estética. Cuando estos bloques tienen una imagen asociada los llamamos **pegatinas** (stickers)

## Pegatinas

Los **bloques pegatinas** (stickers) nos permiten añadir **información visual** a nuestros circuitos, así como incluir **documentación** en su interior. En la colección de la **Academia-Jedi-HW-21** se han incluido algunas pegatinas, que están accesibles desde el menú **Varios/Pegatinas**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/intro-08.gif)

Además de algunos **emojis**, se han incluido todos los **rangos de la Academia Jedi** disponibles hasta ahora. Están accesibles todos desde el ejemplo accesible desde el menú **Archivo/Ejemplos/1-Ejemplos/02-Pegatinas-Academia-Jedi**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/pegatinas-02.png)

No tienen ninguna utilidad, pero mola añadirlos a nuestros circuitos para mostrar nuestro rango :-)  También se han añadido, a modo de ejemplos, pegatinas del **mundial de Rusia 2018**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/pegatinas-01.png)

## Bloque1.ice: Creando un bloque de sólo Texto

Vamos a crear nuestro primer bloque. Sólo contendrá el texto: **Bloque 1**. Los **pasos** a seguir son los siguientes:

* **Arrancamos Icestudio**. El circuito lo dejaremos en blanco (no tiene nada), simplemente queremos crear un bloque sin puertos, que sólo tenga su nombre

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/bloque1-1.png)

* **Pinchamos** en la opción del menú **Editar/Información del proyecto**. 

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/bloque1-2.png)

* Nos aparece una **ventana nueva**, con información para el bloque. De momento sólo escribiremos la cadena **Bloque1** en la casilla **Nombre** (pero podemos poner el nombre que queramos, es sólo un ejemplo). Y pinchamos en **OK**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/blob/master/wiki/Tutorial-21/bloque1-3.png)

* Aparecerá una **notificación** verde, en la parte inferior derecha indicando que la **información del proyecto se ha actualizado**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/bloque1-4.png)

* **Grabamos** el bloque en el **fichero bloque1.ice** (por ejemplo). Pinchamos en **Archivo/Guardar como**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/bloque1-5.png)

* Se nos abre una ventana donde debemos **introducir el nombre del fichero** y el **directorio** en el que queremos grabarlo. Por ejemplo, lo llamamo **bloque1.ice** y lo guardamos en el **Escritorio**. La **apariencia** de esta ventana depende del **sistema operativo empleado**. Este pantallazo se corresponde con Ubuntu 16.04

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/bloque1-6.png)

* **Pulsamos** el botón de guardar. Nos aparecerá otra **notificación** indicando que se ha guardado el proyecto

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/bloque1-7.png)

El **nuevo bloque** ya está creado y almacenado en el **fichero bloque1.ice**, que hemos guardado en el escritorio. El proceso completo se resumen en esta **animación**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/bloque1-8.gif)

Ahora vamos a colocar el **bloque nuevo** en un **circuito nuevo**. En la ventana actual de Icestudio tenemos la implementación del bloque 1. 

* **Abrimos** una nueva para crear el nuevo Circuito. Pinchamos en **Archivo/Nuevo** y nos aparece una ventana en blanco

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/bloque1-10.png)

* Para **colocar** el bloque creado, pinchamos en **Archivo/Añadir como bloque**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/bloque1-11.png)

* **Seleccionamos** el fichero **bloque1.ice** y le damos al **OK**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/bloque1-12.png)

* **Colocamos** el bloque1

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/bloque1-13.png)

Si hacemos **doble click** en el bloque, veremos su **interior**. En este ejemplo no tiene nada dentro. En la esquina superior izquierda vemos su nombre: Bloque1. Y en la inferior izquierda la jerarquía: **proyecto actual/Bloque1**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/bloque1-14.png)

El proceso completo de **colocación** del **nuevo bloque** creado se resume en esta **animación**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/bloque1-9.gif)

## Bloque2.ice: Añadiendo más información

Ahora vamos a crear el **bloque2** a partir del **bloque1** añadiendo **más información**. En vez de ser un bloque en blanco añadiremos comentarios usando **bloques de información**

Nos vamos a la ventana donde estamos editando el **bloque1.ice** y ponemos **comentarios** y algunas **pegatinas**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/bloque2-1.png)

**Editamos** la información del bloque en **Editar/Información del proyecto**. Cambiamos el nombre por Bloque2 y añadimos un texto en el **campo descripción**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/bloque2-2.png)

Todos los campos son **opcionales**. Podemos añadir información sobre el **autor**, la **versión**, el **icono** del bloque, etc. En este ejemplo sólo hemos rellenado el **nombre**, para que aparezca en el bloque, y la **descripción**, que aparecerá cuando pongamos el puntero **encima del bloque**, durante unos segundos

Pulsamos **OK** y guardamos el bloque como **bloque2.ice**.  Nos vamos a la otra ventana, donde habíamos colocado el bloque1, y colocamos el nuevo bloque, con la opción que ya conocemos de **Archivo/Añadir como bloque**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/bloque2-3.png)

Si dejamos el **cursor del ratón** unos segundos **sobre el Bloque2**, veremos que aparece el texto que hemos introducido en la **descripción**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/bloque2-4.png)

Y si nos **metemos en su interior** (haciendo doble click) vemos los comentarios y pegatinas que hemos colocado, aunque **NO** podemos editarlos desde ahí

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/bloque2-5.png)

En esta **animación** se resume el proceso:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/bloque2-6.gif)

## Bloque3.ice: Añadiendo iconos

Crearemos un nuevo bloque, **bloque3.ice**, a partir del anterior, añadiendo un **icono**.  Las imágenes que se usan para los bloques tienen que estar en [formato SVG](https://es.wikipedia.org/wiki/Gr%C3%A1ficos_vectoriales_escalables). Es un formato **vectorial**, **abierto** y **estandarizado**. Los ficheros SVG se pueden visualizar desde el **navegador**, y se pueden editar con bastantes herramientas, como por ejemplo el programa [Inkscape](https://inkscape.org/), que es **software libre**

Para este **ejemplo** utilizaremos el **fichero SVG** de una **estrella de 5 puntas**: [star-5p.svg](https://github.com/FPGAwars/icestudio-block-icons/raw/master/Stars/star-5p.svg)

![](https://github.com/FPGAwars/icestudio-block-icons/raw/master/Stars/star-5p.svg?sanitize=true)

Seguimos los siguientes pasos:

* **Descargamos** el **icono SVG** de la estrella: [star-5p.svg](https://github.com/FPGAwars/icestudio-block-icons/raw/master/Stars/star-5p.svg)

* **Editamos** el bloque2 y cambiamos sus comentarios. Ahora es el **bloque3**. Ponemos otras pegatinas

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/bloque3-1.png)

* Abrimos la ventana con la **información del proyecto**, cambiamos el nombre y la descripción. Aprovechamos para completar el resto de campos: **Versión** y **Autor** (son opcionales)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/bloque3-2.png)

* En la parte inferior pinchamos en el botón que dice **Abrir SVG**. Se nos abre un navegador de archivos y **seleccionamos el fichero SVG** que hemos bajado antes: star-5p.svg. Pinchamos en **Abrir**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/bloque3-3.png)

* En la información del proyecto nos aparece el **icono** que hemos seleccionado, en la parte inferior. **¡Ya lo tenemos listo!**. Pinchamos en **OK**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/bloque3-4.png)

* Guardamos el bloque como **bloque3.ice**, con la opción **Archivo/Guardar como**

* Cambiamos a la ventana donde estamos colocando los bloques de ejemplo y añadimos el nuevo, con **Archivo/Añadir como bloque**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/bloque3-5.png)

Vemos que ahora **se ha sustituido el nombre del bloque por su icono**. No aparece el nombre, como en el caso de los bloques anteriores, pero sí la imagen que hemos añadido. Si nos situamos **encima del bloque** aparecerá la **nueva descripción**

Si nos metemos **dentro del bloque3**, veremos su nuevo contenido. Ahora, en la **esquina superior izquierda**, además del nombre aparece su **versión**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/bloque3-6.png)

En esta **animación** se resume el proceso:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/bloque3-7.gif)

# Bloques con puertos

Aprenderemos a **crear bloques con puertos**, para poder introducir información en ellos y sacar sus respuestas. Comezaremos por los **puertos de 1 bit**

## Puertos de 1 bit

TODO

## Puertos de varios bits

TODO

# Bloques con parámetros

TODO

# Creando iconos con Inkscape

TODO


# Ejercicios propuestos (X BitPoints)

Ver los detalles de los ejercicios y las **entregas** en el menú **Archivos/Ejemplos/2-Ejercicios** de la colección de este tutorial

**Resumen**:

* **Ejercicio 1** (Total **x Bitpoints**): 

* **Ejercicio 2** (Total **x Bitpoints**): 

* **Ejercicio 3** (Total **x Bitpoints**): 

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

* **Ya tengo varios PCBprints impresos (de los LEDs y los pulsadores. ¿Dónde podría conseguir los cables que usas para conectarlos directamente a la Icezum Alhambra?**

  Son cables hembra-hembra de tres hilos. Como son los mismos que se usan para la conexión de servos, los puedes encontrar en tiendas donde vendan cualquier tipo de servo. Por ejemplo:  
  * En **Pololu**:  https://www.pololu.com/product/779
  * En **hobby king**: https://hobbyking.com/en_us/10cm-female-to-female-servo-lead-jr-26awg-10pcs-set.html?___store=en_us  

  También se pueden usar cables hembra-hembra aislados. A partir de ellos es muy fácil trenzarlos y hacerte tu propio cable de 3 pines:

  * **Adafruit**:  https://www.adafruit.com/product/266
  * En **Bricogeek**: http://tienda.bricogeek.com/cables/585-set-de-cables-h-h-10-unid.html 
  * En **Iberobotics**: Aquí también tienen los hembra-hembra: https://www.iberobotics.com/comprar/electronica-componentes/cables-y-conectores/ Es otra tienda española que está en Santander



