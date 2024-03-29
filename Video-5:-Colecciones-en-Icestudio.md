![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-05/portada-tut05.png)

# Vídeo

[![Click to see the youtube video](http://img.youtube.com/vi/BK0U7Hm-HII/0.jpg)](https://www.youtube.com/watch?v=BK0U7Hm-HII&list=PLmnz0JqIMEzXaeYVzf2TfTzRekPIVoljw&index=5)

Haz click en la imagen para ver el **vídeo en Youtube**

# Descripción

Las  **colecciones** contienen **bloques** y **ejemplos**. Aprenderemos a instalarlas y usarlas. Haremos el circuito "hola mundo" que ya conocemos pero con una colección nueva, y lo documentaremos usando el **bloque información**

# Colección

[Academia-Jedi-HW-05.zip](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/Contenido/Tutorial-05/Academia-Jedi-HW-05.zip): Colección para este tutorial. Descargar e instalar (Lo haremos en el tutorial)

# Contenido

* [Icestudio 0.3.1](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-5:-Colecciones-en-Icestudio#icestudio-031)
* [Colecciones](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-5:-Colecciones-en-Icestudio#colecciones)
  * [La colección por defecto](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-5:-Colecciones-en-Icestudio#la-colecci%C3%B3n-por-defecto)
  * [La colección de la Academia Jedi de Hardware](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-5:-Colecciones-en-Icestudio#la-colecci%C3%B3n-de-la-academia-jedi-de-hardware)
    * [Instalación](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-5:-Colecciones-en-Icestudio#instalaci%C3%B3n)
    * [Seleccionando la colección activa](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-5:-Colecciones-en-Icestudio#seleccionando-la-colecci%C3%B3n-activa)
* [Usando la colección de la academia Jedi](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-5:-Colecciones-en-Icestudio#usando-la-colecci%C3%B3n-de-la-academia-jedi)
  * [Haciendo (otra vez) el circuito Hola Mundo](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-5:-Colecciones-en-Icestudio#haciendo-otra-vez-el-circuito-hola-mundo)
  * [Poniendo comentarios](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-5:-Colecciones-en-Icestudio#poniendo-comentarios)
  * [Texto enriquecido con HTML](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-5:-Colecciones-en-Icestudio#texto-enriquecido-con-html)
  * [Referenciando imágenes de internet](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-5:-Colecciones-en-Icestudio#referenciando-im%C3%A1genes-de-internet)
* [Ejercicios propuestos](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-5:-Colecciones-en-Icestudio#ejercicios-propuestos-9-bitpoints)
* [Ejercicios entregados](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-5:-Colecciones-en-Icestudio#ejercicios-entregados)
  * [Jesús Rodríguez Conde (Chuxman)](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-5:-Colecciones-en-Icestudio#jes%C3%BAs-rodr%C3%ADguez-conde-chuxman)
  * [Ximo Catalá](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-5:-Colecciones-en-Icestudio#ximo-catal%C3%A1)
  * [J.Carlos Obregón (Carlobre)](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-5:-Colecciones-en-Icestudio#jcarlos-obreg%C3%B3n-carlobre)
* [Autor](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-5:-Colecciones-en-Icestudio#autor)
* [Licencia](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-5:-Colecciones-en-Icestudio#licencia)
* [Créditos y agradecimientos](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-5:-Colecciones-en-Icestudio#cr%C3%A9ditos-y-agradecimientos)
* [Enlaces](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-5:-Colecciones-en-Icestudio#enlaces)
* [FAQs](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-5:-Colecciones-en-Icestudio#faqs)

# Icestudio 0.3.1

**Jesús Arroyo** acaba de liberar la [versión 0.3.1 de Icestudio](https://github.com/FPGAwars/icestudio/releases/tag/0.3.1), que será la que usemos a partir de ahora. En los tutoriales anteriores estábamos usando la 0.3.1-rc

Una vez instalada, podemos comprobar que es la versión correcta mirando en el **menú Ayuda**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-05/icestudio-0-3-1.png)

# Colecciones

Icestudio es la herramienta para crear **circuitos digitales**. Los **componentes** usados y los **ejemplos** están por separados. No forman parte del propio Icestudio, sino que se encuentran en lo que llamamos una **colección**

## La colección por defecto

Nada más instalar Icestudio, se nos añade la **colección por defecto** (default), que contiene unos pocos componentes y algunos ejemplos. De momento sólo hemos visto los componentes del menú **Bit**. Las tres opciones situadas en la parte más derecha de la barra superior pertenecen a esta colección por defecto: **Bit**, **Lógica** y **Setup**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-05/coleccion-default-01.png)

Y también los **ejemplos** del menú **Archivo**. Cuando cambiamos a una colección nueva, estas dos partes: los componentes y los ejemplos se actualizarán

Desde el menú **Seleccionar/Colección** podemos cambiar a cualquiera de las otras colecciones que tengamos instaladas. 

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-05/coleccion-default-02.png)

Inicialmente sólo tenemos instalada la **colección por decto**. Para obtener más información sobre ella, nos vamos al menú **Ver/Información de la colección**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-05/coleccion-default-03.png)

y se nos abre una ventana con toda la **información**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-05/coleccion-default-04.png)

Si bajamos a la parte inferior podemos ver los autores, las traducciones, etc.

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-05/coleccion-default-05.png)

## La colección de la Academia Jedi de Hardware

A partir de ahora usaremos **una colección para cada tutorial**. En ella estarán los **componentes usados** en el tutorial, los **ejemplos** mostrados, las **soluciones a los ejercicios** del tutorial anterior y los **ejercicios propuestos**

### Instalación

**Descargamos** el fichero .zip con la colección: [Academia-Jedi-HW-05.zip](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/Contenido/Tutorial-05/Academia-Jedi-HW-05.zip). **NO lo descomprimimos**. Pinchamos en el menú **Herramientas/Colecciones/Añadir**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-05/coleccion-Jedi-01.png)

Se nos abre otra ventana para **seleccionar** el fichero descargado, con la colección

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-05/coleccion-Jedi-02.png)

Pinchamos en abrir y nos aparece una nueva ventana para dar un **nombre a la colección**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-05/coleccion-Jedi-03.png)

Dejamos el que está y le damos al **ok**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-05/coleccion-Jedi-04.png)

Nos aparecerá una **notificación** verde en la esquina inferior derecha indicando que la colección **Academia-Jedi-HW-05 se ha añadido**

### Seleccionando la colección activa

El siguiente paso es seleccionar la colección activa, desde el menú **Seleccionar/Colección**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-05/coleccion-Jedi-05.png)

Además de la colección por defecto, nos aparecerá la que acabamos de instalar: **Academia-Jedi-HW-05**. Pinchamos en ella

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-05/coleccion-Jedi-06.png)

Nos aparece una **notificación** indicando que hemos seleccionado la **nueva colección** y las opciones del menú de la parte superior derecha se actualizan a los de la nueva colección. Ahora sólo tenemos la entrada **Bit**, ya que se trata de una coleción muy sencilla. El menú **Básico** es común a todas las colección. Siempre estará ahí

**Podemos cambiar de una colección a otra simpre que queramos**. El funcioamiento es similar a los **escenarios** de FreeCAD. Según la colección seleccionada tendremos unos bloques u otros, así como los ejemplos

# Usando la colección de la Academia Jedi

Vemos dos cosas que han cambiado al instalar esta colección. Por un lado el **menú superior** y por otro lado el de **ejemplos**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-05/coleccion-Jedi-07.png)

Nos vamos al **menú Bit** y vemos que similar al que tenemos en la colección por defecto: Tiene las opciones de **1** y **0**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-05/coleccion-Jedi-08.png)

Ponemos un **bloque de cada** para ver cómo son

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-05/coleccion-Jedi-09.png)

Son bits constantes, iguales que los de la colección default, pero con el dibujo cambiado. **¡Tienn patas!** Yo me imagino a los bits como unos bichos pequeños con patas, que se mueven por lo cables, como si fueran [lemmings](https://en.wikipedia.org/wiki/Lemmings_(video_game)) :-)

## Haciendo (otra vez) el circuito "Hola mundo"

Para **practicar** con la nueva colección instalada haremos el circuito **Hola mundo** para encender un LED, que es el único que conocemos por ahora. Colocamos un bit a 1 y una salida. Le asignamos la **etiqueta LED** y seleccionamos el **LED1**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-05/coleccion-Jedi-10.png)

## Poniendo comentarios

A nuestros circuitos podemos añadir comentarios colocando un **bloque de información**. Nos vamos al menú **Básico/Información**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-05/coleccion-Jedi-11.png)

Nos aparece un **bloque gris**, con el cursos encima. Lo movemos hasta la posición donde queremos poner los comentarios y hacemos **click**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-05/coleccion-Jedi-12.png)

El **tamaño** del bloque se cambia pinchando en su **esquina inferior derecha** y **arrastrándola** a la nueva posición

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-05/coleccion-Jedi-13.png)

Hacemos **click** en su interior y **escribimos** los comentarios

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-05/coleccion-Jedi-14.png)

Es un bloque que podemos **editar** y cambiar en cualquier momento.

## Texto enriquecido con HTML

En los bloques de información podemos incluir **código HTML** para resaltar textos e incluso mostrar **imágenes** de internet

 Vamos a poner otro comentario debajo del circuito. Colocamos **otro bloque de información**, igual que antes

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-05/coleccion-Jedi-15.png)

Escribimos otro texto, pero ahora colocando el **texto a resaltar** entre los comandos **\<B>** y **<\/B>** que es la forma de poner un texto en **negrita** en **HTML**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-05/coleccion-Jedi-16.png)

Hacemos **doble click** en el marco gris del bloque y se nos abre una ventana

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-05/coleccion-Jedi-17.png)

**Marcamos** la casilla que pone **Sólo lectura** y le damos al **OK**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-05/coleccion-Jedi-18.png)

Nos aparece una **notificación** indicando que el bloque se ha modificado y podemos ver el **texto renderizado**. El borde del bloque ha desaparecido. 

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-05/coleccion-Jedi-19.png)

Este bloque lo podemos **mover**  pinchando con el botón izquierdo y arrastrándolo, pero **NO lo podemos modificar**. Si queremos editarlo, hay que hacer **doble click** y desmarcar la casilla de **Sólo lectura**

## Referenciando imágenes de internet

Para incluir imágenes que están en internet, creamos un **bloque nuevo de información** y usamos el comando HTML **img** para incluir la imagen. Probar con este ejemplo:

```html
<img src="https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/intro-16.jpg" WIDTH=200>
</img>
```

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-05/coleccion-Jedi-20.png)

Ahora lo ponemos en modo **sólo lectura** para que se renderice. Si tenemos **conexión a internet** nos aparecerá esto:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-05/coleccion-Jedi-21.png)

# Ejercicios propuestos (9 BitPoints)

* **Ejercicio 1** (Total **3 Bitpoints**): Hacer un circuito digital que encienda uno o varios LEDs de la Icezum Alhambra usando la colección **Academia-Jedi-HW-05**. Debe contener un **bloque comentario** explicando lo que hace el circuito, así como vuestro nombre o nick en **Negrita**. 
**Entregar** por redes sociales, con mención a **@obijuan_cube**
  * 1 pantallazo del circuito (1 bitpoint)
  * 1 Foto de la Icezum Alhambra con el circuito cargado (1 bitpoint)
  * Entrega adicional por Github (1 bitpoint) 

* **Ejercicio 2** (Total **2 Bitpoints**): Instalar la colección utilizada en el [curso de FPGAs que
se dió en el centro Don Bosco](https://github.com/Obijuan/Curso-Electronica-Digital-para-makers-con-FPGAs-Libres/wiki), en Errentería. Seleccionar 4 ó 5 componetes al azar, y colocarlos (no hace falta 
crear un circuito ni tirar cables). **Entregar** por redes sociales, con mención a **@obijuan_cube**:
  * 1 Pantallazo (1 bitpoint)
  * Entrega adicional por Github (1 bitpoint)

* **Ejercicio 3** (Total *2 Bitpoint*): Instalar la colección utilizada en el [Taller del 
Makespace Madrid](https://github.com/FPGAwars/workshops/wiki/2017_07_08:-Makespace-Madrid). Seleccionar 4 ó 5 componetes al azar, y colocarlos (no hace falta 
crear un circuito ni tirar cables). **Entregar** por redes sociales, con menció a **@obijuan_cube**:
  * 1 pantallazo. Desplagar el menu Seleccionar/Colección
    para que se vean las colecciones que están instaladas (1 bitpoint)
  * Entrega adicional por Github (1 bitpoint)

* **Ejercicio 4** (**2 Bitpoints**). Ejercicio Libre. Premiar la creatividad. **Entregar** por redes sociales o github: Pantallazos, enlaces, vídeos, etc...

# Ejercicios entregados

## Jesús Rodríguez Conde (Chuxman)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-05/entregas/Jesus-rodriguez-conde-ej2.jpg)

## Ximo Catalá

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-5/ximocat/Ejercicio05_11.jpg)

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-5/ximocat/Ejercicio05_12.jpg)

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-5/ximocat/Ejercicio05_2.jpg)

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-5/ximocat/Ejercicio05_3.jpg)

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-5/ximocat/Ejercicio05_4_libre.jpg)

## J.Carlos Obregón (Carlobre)

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-5/Carlobre/Ejercicio%205.1.1.png)

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-5/Carlobre/Ejercicio%205.1.2.jpg)

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-5/Carlobre/Ejercicio%205.2.png)

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-5/Carlobre/Ejercicio%205.3.png)


# Autor

* [Juan González-Gómez](https://github.com/Obijuan) (Obijuan)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/logos-urjc-gsyc-peloto-jderobot.png)

# Licencia

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/attribution-share-alike-creative-commons-license.png)

# Créditos y agradecimientos

* A [Jesús Arroyo](https://github.com/Jesus89) por la liberación de la versión 0.3.1 de [Icestudio](https://github.com/FPGAwars/icestudio) ¡Muchas gracias!
* A **Salvador Tropea**, del INTI en Argentina, por descubrirnos que en los bloques de informació de icestudio se podrían usar comandos HTML para resaltar texto y poner imágenes. ¡Muchas gracias!

# Enlaces

* [Icestudio 0.3.1](https://github.com/FPGAwars/icestudio/releases/tag/0.3.1)
* [Repositorio con las colecciones de la Academia Jedi de Hardware](https://github.com/Obijuan/Academia-Jedi-Hw)
* [Curso de Electrónica digital para makers, con FPGAs libres](https://github.com/Obijuan/Curso-Electronica-Digital-para-makers-con-FPGAs-Libres/wiki), dando en el Centro Integrado de Formación profesional de Don Bosco
* [Taller de electrónica digital para Makers, con FPGAs Libres](https://github.com/FPGAwars/workshops/wiki/2017_07_08:-Makespace-Madrid), dado en el Makespace Madrid

# FAQs

* **¿Dónde puedo conseguir la placa Icezum Alhambra?**

Pueden conseguir una desde [Alhambrabits](https://alhambrabits.com/buy/)

* **¿Cómo aprendo a manejar github?**

Hay mucha información en internet. En su momento hice este Tutorial: [Github y FreeCAD](http://www.iearobotics.com/wiki/index.php?title=Tutorial:_Github_y_Freecad) para enseñar a manejarlo. Los ejemplos están hechos con ficheros de FreeCAD, sin embargo, lo que se enseña es genérico. También vale para las entregas de los ejercicios del tutorial de Electrónica digital para makers


