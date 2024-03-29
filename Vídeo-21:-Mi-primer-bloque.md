![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/Portada/Tut-21-portada.png)

# Vídeo

[![Click to see the youtube video](http://img.youtube.com/vi/xRx9KC5I07w/0.jpg)](https://www.youtube.com/watch?v=xRx9KC5I07w&index=21&list=PLmnz0JqIMEzXaeYVzf2TfTzRekPIVoljw)

Haz click en la imagen para ver el **vídeo en Youtube**

# Descripción

Los circuitos que hemos creado utilizan bloques. Aprenderemos a crear **nuestros propios bloques**, utilizando los que ya conocemos. Esto nos permitirá ocultar la **complejidad** y así crear circuitos más potentes, usando **diseño jerárquico**

# Colección

[Academia-Jedi-HW-21.zip](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/Collection/Academia-Jedi-HW-21.zip): Colección para este tutorial. Descargar e instalar 

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
  * [Puertos de 1 bit](#puertos-de-1-bit)
    * [Ejemplo: Puerta AND de 3 entradas](#ejemplo-puerta-and-de-3-entradas)
    * [Ejemplo: Detector del número 2](#ejemplo-detector-del-n%C3%BAmero-2)
  * [Puertos de varios bits](#puertos-de-varios-bits)
* [Bloques con entradas de reloj](#bloques-con-entradas-de-reloj)
  * [Ejemplo: Corazón de 1Hz con entrada de enable](#ejemplo-coraz%C3%B3n-de-1hz-con-entrada-de-enable)
* [Bloques con parámetros](#bloques-con-par%C3%A1metros)
  * [Ejemplo: Corazón paramétrico con enable](#ejemplo-coraz%C3%B3n-param%C3%A9trico-con-enable)
  * [Ejemplo: Detector paramétrico de números de dos bits](#ejemplo-detector-param%C3%A9trico-de-n%C3%BAmeros-de-2-bits)
* [Creando iconos con Inkscape](#creando-iconos-con-inkscape)
  * [Repositorio de iconos para icestudio](#repositorio-de-iconos-para-icestudio)
  * [Comparte tus iconos :-)](#comparte-tus-iconos--)
* [Ejercicios propuestos (20 Bitpoints)](#ejercicios-propuestos-20-bitpoints)
* [Ejercicios entregados](#ejercicios-entregados)
  * [Andrés (Avarez)](#andr%C3%A9s-avarez)
  * [Jose López](#jose-l%C3%B3pez)
  * [Federico Coca (fgcoca)](#federico-coca-fgcoca)
* [Autor](#autor)
* [Licencia](#licencia)
* [Enlaces](#enlaces)
* [Preguntas frecuentes](#preguntas-frecuentes)

# Introducción

En el [tutorial 18](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-18:-Bloques-con-par%C3%A1metros) vimos que existen dos **técnicas** para hacer **circuitos complejos**: la **parametrización** y la **composición**. Nos vamos a centrar en esta última. Aprenderemos a construir **nuestros propios bloques** a partir de otros bloques que ya conocemos. 

## Puertos

Las entradas y las salidas de los **bloques** las denominamos **puertos**.  Los **puertos de entrada** son los puntos donde **entra** la información al bloque. Los **puertos de salida** son los puntos donde la información **sale** del bloque. En Icestudio, los puertos de entrada se colocan siempre en la izquierda del bloque, y los de salida en la derecha. El **bloque** que representa una **puerta AND** tiene 2 puertos de entrada y uno de salida

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/intro-01.png)

Los puertos tienen un **nombre** y un **tamaño** en bits. El nombre es **opcional** cuando se trata de **puertos de un bit**, como en el ejemplo de la puerta AND, pero se pone siempre cuando son de más de un bit (buses). Además de los puertos, los bloques de icestudio tienen **parámetros**, en su **parte superior**. También tienen un nombre, que es opcional 

Este **bloque comecocos** es un **ejemplo** que tiene dos **parámetros de entrada**, uno con nombre, **p1**, y otro sin nombre. Tiene **3 puertos de entrada**, uno de 1 bit, sin nombre, otro de 1 bit (a),y uno de 8 bits (i). Tiene también **3 puertos de salida**, de un bit, sin nombre y con nombre (b), y de 4 bits (o)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/intro-02.png)

## Pines

Los **pines** son los **puntos físicos** por donde **entra la información** a nuestro circuito en la FPGA, y por donde se **envían las respuestas** de salida. Son **puertos** que están **asociados a una pata de la FPGA**

Los **pines** son de **1 bit** y se **conectan** a los **puertos de 1 bit** de otros bloques mediante **cables**. Pueden tener un **nombre** opcionalmente. En icestudio, los **pines de entrada** se ponen en la izquierda (su puerto está en la derecha) y los **pines de salida** se colocan a la derecha (su puerto está en la izquierda). Como ya vimos en el [tutorial 20](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-20:-Buses-y-n%C3%BAmeros), varios pines se pueden **agrupar** formando un **bloque**, que se conecta a otros bloques mediante un **bus**

En este **ejemplo** se ha colocado el bloque **comecocos** anterior, y se han conectado sus puertos a pines, usando cables y buses

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

Además de algunos **emojis**, se han incluido todos los **rangos de la Academia Jedi** disponibles hasta ahora. Están accesibles todos desde el menú **Archivo/Ejemplos/1-Ejemplos/02-Pegatinas-Academia-Jedi**

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

Los **puertos de 1 bits** son los que más hemos usado hasta ahora. El **nombre** asociado a cada puerto de 1 bit es **opcional**. Aprenderemos mediante **ejemplos**: Primero haremos una **puerta AND de 3 entradas** y luego un **detector del número 2** (Comparador de un número de 2 bits con el número 2)

### Ejemplo: Puerta AND de 3 entradas

Empezamos **definiendo** cómo será nuestro **bloque**. Tendrá en total **4 puertos**: 3 de entrada y uno de salida. No asignaremos nombres a los puertos. El **icono** que usaremos será el siguiente:

![](https://github.com/FPGAwars/Icestudio-block-icons/raw/master/Logic_gates/and3.svg?sanitize=true)

Que se puede **descargar** desde aquí: [and3.svg](https://github.com/FPGAwars/Icestudio-block-icons/raw/master/Logic_gates/and3.svg)

Empezamos con su **implementación**. Creamos un circuito nuevo. Primero colocaremos los **puertos de entrada**. Nos vamos a **Básico/Entradas**, igual que cuando colocamos un pin de entrada. En la venta que aparece **desmarcamos** la opción **FPGA pin** y pinchamos en **OK**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/and-01.png)

Nos aparece un **bloque verde**, que representa un **puerto**. Lo colocamos

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/and-02.png)

Añadimos **dos puertos de entrada más**, bien repitiendo el proceso anterior o bien copiando y pengando el puerto colocado

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/and-03.png)

El **puerto de salida** se coloca de forma similar, pinchando en **Básico/Salidas** y **desmarcando** la opción **Pin FPGA**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/and-04.png)

Lo **colocamos** en la parte de la derecha

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/and-05.png)

La **colocación de los puertos** se puede ver en esta **animación**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/and-7.gif)

La **puerta AND de tres entradas** se puede **implementar** de muchas maneras. Es un **circuito combinacional** de 3 entradas y una salida, definido por una tabla de verdad en la que la **salida** se pone a **1** solo en el caso en que las **tres entradas estén a uno**. En el resto de casos la salida es **0**.

Una implementación sería utilizando **tablas de verdad**. Otra posible implementación es usando las **puertas AND de dos entradas** que ya conocemos. Usaremos esta última para el ejemplo. El circuito que creamos es el siguiente:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/and-06.png)

Ahora editamos la información del bloque en **Editar/Información del proyecto**. Le ponemos de nombre **AND-3**, la versión (por ejemplo 0.1), una descripción, nombre del autor (nuestro nombre, por ejemplo) y seleccionamos como **icono** el fichero **and3.svg** que hemos descargado antes

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/and-08.png)

Pulsamos **OK** y **guardamos** el fichero como **and3.ice**. Ya tenemos nuestro nuevo bloque listo para probar

### Probando la puerta AND

Creamos un **documento nuevo**. Colocamos la **puerta AND de 3 entradas** recién creada con la opción de **Archivo/Añadir como bloque**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/and-09.png)

Para probarla colocaremos **3 pines de entrada**, en los que conectaremos **3 interruptores externos**, y un **pin de salida** conectado a un **LED externo**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/and-10.png)

El **montaje** para probarlo es este:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/and-12.jpg)

**Cargamos** y **probamos**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/and-13.gif)

Al activar los **tres pulsadores** se enciende el LED, en el resto de casos está apagado (en la animación no se muestran todos los casos)

### Ejemplo: Detector del número 2

Como segundo ejemplo haremos un **circuito combinacional** que tiene **2 puertos de entrada**, y **uno de salida**. Los dos puertos de entrada tienen asignados los nombres **i0** e **i1**. Se trata de un circuito que detecta si el número entrante es el **2** (en binario 10). La **entrada i1** se corresponde con la de mayor peso y la **i0 con la de menor**. Para distinguirlas es necesario asignarles nombres

Vamos a hacer el bloque de **otra manera**. Empezamos por crear un **circuito de pruebas**, con el detector implementado mediante una **puerta AND** y **una NOT**. Usamos **pines normales** (bloques amarillos). A los pines de entrada le damos los **nombres i1** e **i0**. Al de salida no le ponemos ninguna etiqueta

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/detector2-01.png)

Hacemos el **montaje**, **cargamos** y lo **probamos**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/detector2-0.gif)

El interruptor de la **izquierda** es el **más significativo**. Sólo cuando está activado y el de la derecha no lo está, es cuando se está introduciendo el **número 2** (10) y por tanto se **enciende el LED**. En el resto de casos el LED está apagado

Una vez comprobado que el circuito funciona, vamos a **convertirlo** en un **bloque**. Hacemos **doble click** en el **marco de los pines** para editarlos. Y **deshabilitamos** la opción **FPGA pin** para convertirlos en **puertos**. Empezamos por el **i1**, por ejemplo

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/detector2-02.png)

Pinchamos el **OK** y se **actualiza** la entrada de pin a **puerto**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/detector2-03.png)

Hacemos lo mismo con el **resto de pines**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/detector2-04.png)

En esta **animación** vemos el proceso:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/detector2-05.gif)

Como **icono** para el bloque usaremos este:

![](https://github.com/FPGAwars/icestudio-block-icons/raw/master/Comparations/is_2.svg?sanitize=true)

que podemos descargar desde aquí: [is_2.svg](https://github.com/FPGAwars/icestudio-block-icons/raw/master/Comparations/is_2.svg)

Ahora introducimos la **información** del bloque desde **Editar/Información del proyecto**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/detector2-05.png)

y pinchamos en **OK**. **Guardamos** el bloque como **detector-2.ice**. Creamos un **circuito nuevo** y colocamos el **bloque detector** recién creado, pinchando en la opción **Archivo/Añadir como bloque**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/detector2-06.png)

Ahora lo podemos usar en nuestros circuitos. Para probarlo, simplemente **conectaremos** sus entradas y salidas a **pines**, igual que cuando lo creamos

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/detector2-07.png)

Si nos **metemos** dentro del bloque, veremos la implementación que hemos hecho previamente

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/detector2-08.gif)

## Puertos de varios bits

Para aprender a usar **puertos de varios bits**, y no sólo de 1, **modificaremos** el bloque anterior para que su entrada sea un **puerto de 2 bits** en vez de 2 entradas de 1 bit separadas. La manera de trabajar es **exactamente igual**. Sólo hay que tener en cuenta que los puertos de más de 1 bits **siempre** tienen que tener un **nombre** (NO es opcional, es obligatorio). En el caso de los puertos de 1 bit, el nombre es opcional

Creamos primero el circuito usando **pines**, para poder **sintetizarlo** y **comprobarlo** en el montaje que tenemos:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/detector-2-bus-1.png)

Es el mismo detector del ejemplo anterior pero al que se le ha añadido un **separador de bus**. Ponemos la **misma información** en el proyecto, y el mismo icono (Editar/Información del proyecto). Cambiamos los **pines por puertos**, y lo **guardamos** como **detector2-bus.ice**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/detector-2-bus-2.png)

Ahora creamos otro circuito para **probar** el nuevo bloque, conectando sus dos puertos a pines

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/detector-2-bus-3.png)

En esta **animación** vemos el bloque en su interior

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/detector-2-bus-4.gif)

# Bloques con entradas de reloj

Los bloques tienen una **entrada especial**, llamada **entrada de reloj**. Más adelante veremos para qué sirve, y crearemos circuitos secuenciales, que tienen la capacidad de almacenar información en su interior. Pero de momento aprenderemos a **hacer bloques** con una **entrada de reloj**, aunque no sepamos para qué sirve

Como **ejemplo** usaremos el circuito que hace **parpadear un LED** a la frecuencia de **1Hz**, que ya conocemos muy bien. En la izquierda tiene una **entrada de reloj**, que está marcada con el **símbolo >**.  Está conectada a un pin de entrada especial: el **reloj del sistema**, que en icestudio se denota por un **cuadrado amarillo pequeño**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/corazon-ena-01.png)

## Ejemplo: Corazón de 1Hz con entrada de enable

Vamos a crearnos **nuestro propio bloque corazón**, de frecuencia 1Hz, que disponga de una **entrada de enable**. Cuando esta entrada esté activada, el corazón bombeará bits normalmente. Cuando esté a 0, su salida estará a 0, y no se bombearán bits

Empezamos haciendo su implementación, usando pines para poder probar el circuito. Lo implementamos a partir de un corazón de 1Hz y una puerta AND para realizar la habilitación. Este bloque tiene en total **dos puertos de entrada**, uno para su **entrada de reloj** y otra para la **de enable**, y un **puerto de salida**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/corazon-enable-01.png)

En el **esquema de montaje** colocamos un **pulsador** y un **LED externos**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/corazon-enable-02.jpg)

Lo **cargamos** y lo **probamos**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/corazon-enable-03.gif)

Cada vez que apretamos el pulsador, el **LED** se pone a **parpadear**

Para convertirlo en **bloque**, empezamos colocando una **entrada sin nombre**, **desactivamos** la opción de **FPGA pin** y **activamos** la opción de **mostrar reloj**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/corazon-enable-04.png)

Pinchamos el botón de **OK** y colocamos el bloque. Observamos que tiene el **símbolo >**, que indica que es un **puerto especial de entrada de reloj**. Tiramos un **cable** a la entrada de reloj del bloque del corazón

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/corazon-enable-06.png)

Y **convertimos** el resto de pines a **puertos**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/corazon-enable-08.png)

En esta **animación** se muestra con más detalle el proceo para **crear** el puerto de **entrada del reloj**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/corazon-enable-07.gif)

El **icono** lo descargamos de este enlace: [Heart_1Hz.svg](https://github.com/FPGAwars/Icestudio-block-icons/raw/master/Hearts/Heart_1Hz.svg). Editamos la información del bloque:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/corazon-enable-09.png)

Lo **guardamos** como **corazon-1hz-enable.ice**. Creamos un circuito en blanco e **importamos el corazón**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/corazon-enable-10.png)

Vemos cómo la **entrada de reloj** nos aparece conectada automáticamente al **pin de reloj del sistema**. Conectamos el resto de pines para realizar **pruebas**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/corazon-enable-11.png)

# Bloques con parámetros

Además de los puertos, los bloques tienen **parámetros de entrada**. Para crearlos, simplemente basta con usar otros **bloques paramétricos** y colocar los **contenedores** (contante o Memory) para establecer su valor

Haremos dos ejemplos: Un **corazón con entrada de enable**, igual que el del apartado anterior, pero con la **frecuencia en HZ paramétrizada**. El otro será un **detector paramétrico de números de dos bits**. En apartados anteriores hicimo uno que detectaba el número 2 exclusivamente. Ahora haremos uno que detecte el número de 2 bits que se introduzca como **parámetro**

## Ejemplo: Corazón paramétrico con enable

Partimos del **mismo ejemplo** que hemos hecho antes, para hacer nuestro propio corazón con entrada de enable, pero cambiamos el corazón de frecuencia fija por uno **paramétrico**, y le asignamos un valor por defecto de la frecuencia, de 1Hz, por ejemplo. Usamos **pines** para **probar** el circuito y comprobar que **funciona correctamente**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/block-param-01.png)

Ahora lo **convertimos a bloque** como ya sabemos: **convertimos los pines en puertos** y añadimos el puerto del reloj

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/block-param-02.png)

El **parámetro** se deja tal cual. Aparecerá como parámetro en el bloque. Como no le hemos asignado ningún nombre, simplemente nos aparecerá una línea en la parte superior del bloque, sin ningún nombre. Guardamos el bloque como **corazon-enable.ice**. Descargamos este icono: [Heart_Hz.svg](https://github.com/FPGAwars/icestudio-block-icons/raw/master/Hearts/Heart_Hz.svg). **Editamos** la información del bloque

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/block-param-03.png)

En un circuito nuevo **importamos el bloque** (Archivo/Añadir como bloque). Nos aparece el corazón, con su entrada de enable, el reloj del sistema conectado al puerto del reloj y **la entrada del parámetro** en la parte superior

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/block-param-04.png)

Le **asignamos un valor al parámetro**, por ejemplo 2, y conectamos la entrada y la salida a dos pines para **probar** el bloque

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/block-param-05.png)

¡Ya hemos hecho nuestro primer bloque paramétrico!

## Ejemplo: Detector paramétrico de números de 2 bits

En uno de los ejemplos anteriores hicimos un detector del número 2. Ahora lo **generalizaremos** para que sea un **detector paramétrico**, y que el **número k** a detectar sea un parámetro. Para su implementación utilizaremos el [comparador de números de dos bits](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-19:-Circuitos-combinacionales#ejemplo-6-comparador-de-n%C3%BAmeros-de-2-bits) que hicimos en el [tutorial 19](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-19:-Circuitos-combinacionales).

El **circuito completo**, usando **pines**, es el siguiente

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/block-param-06.png)

Para los **dos bits superiores** del comparador introducimos la **constante** que queremos detectar, que por defecto está puesto el 3. Por los **2 bits inferiores** introducimos el **número a detectar**, que proviene de los **interruptores externos**. Lo Cargamos para probarlo

Ahora vamos a convertirlo en bloque. Vemos que tenemos **2 parámetros**: el valor de la **contante k**, que es el número a detectar, y la **tabla de verdad** del comparador. Esta última no queremos sacarla hacia fuera. No queremos que se tenga acceso a ella desde el exterior. Es decir, queremos convertirla en un **parámetro interno**, sólo visible en la **implementación del bloque**, pero no accesible desde el exterior

Hacemos **doble click** en la tabla, para editarla, y **marcamos** la casilla que pone **parámetro local**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/block-param-07.png)

Aparece un **candado cerrado** en su esquina superior derecha, indicando que es un **parámetro local**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/block-param-08.png)

Ahora **cambiamos** los **pines** por **puertos**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/block-param-09.png)

Usaremos este **icono**: [is_k.svg](https://github.com/FPGAwars/icestudio-block-icons/raw/master/Comparations/is_k.svg). Editamos la **información del bloque**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/block-param-10.png)

Creamos un **circuito en blanco** y añadimos el **bloque nuevo**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/block-param-11.png)

Vemos cómo solo tiene **un parámetro de entrada** en la parte superior. Le damos un valor y conectamos la entrada y la salida a pines para probar el bloque

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/block-param-12.png)

Cambiando el valor del parámetro realizamos comparaciones con diferentes números
# Creando iconos con Inkscape

Hasta ahora hemos usado **iconos SVG** ya c
reados, para nuestros bloques. Vamos a aprender a **crear** los nuestros propios. Para ello usaremos el programa **libre** y **multiplataforma** [Inkscape](https://inkscape.org)

Una vez **instalado**, lo arancamos, y nos aparecerá una ventana como esta

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/iconos-01.png)

La apariencia exacta depende del sistema operativo, el tamaño de la ventana y el idioma. Los iconos pueden estar en otras posiciones, así como los menúes

Vamos a crear **nuestro primero icono**. Simplemente haremos un **círculo rojo**. Pinchamos en el icono el círculo en la parte de la derecha. Nos situamos en cualquier parte del lienzo de dibujo. Pulsamos el botón izquierdo y arrastramos el ratón hasta que tengamos el círculo. El tamaño no es importante, porque al tratarse de un **dibujo vectorial**, se verá perfectamente en cualquier tamaño. Con el círculo seleccionado, pinchamos en la barra inferior de colores, para establecer el relleno

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/iconos-05.png)

El **paso clave es ajustar el tamaño de la página** para que se ajuste a nuestro icono. Si no lo hacemos, se usará el tamaño de la página por defecto, que es un din A4, y nuestro icono se verá muy pequeño

Nos vamos a **Archivo/Propiedades del documento**.   Desplegamos la opción de **Ajustar página a contenido** y pinchamos en el botón de **Ajustar página a dibujo o selección**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/iconos-03.png)

Veremos cómo la paǵina se **ajusta** a nuestro círculo rojo

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/iconos-04.png)

En esta **animación** se muestra el proceso completo

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/icono-02.gif)

Ahora **grabamos** el icono como **mi-icono.svg**, desde **Archivo/Guardar**

Creamos un **bloque pegatina** para probarlo, que ya lo sabemos hacer. Lo importamos en un documento nuevo de Icestudio:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/iconos-06.png)

Ahora ya sólo es cuestión de **aprender a manejar el inkscape**, para aprender a dibujar con él, y bien crear nuestros iconos  desde cero o bien modificar los creados por otros. En este ejemplo sólo hemos puesto un círculo rojo, pero podemos hacer lo mismo con otras **figuras geométricas**: rectángulos, estrellas, polígonos..., ***añadir trazos**, importar **imágenes** png, jpg..., colocar **texto**, etc.

## Repositorio de iconos para Icestudio

Todos los **iconos SVG** utilizados en los bloques de muchas colecciones, incluidos los de estos tutoriales, están publicados en este **repositorio de github**:  [Icestudio block icons](https://github.com/FPGAwars/icestudio-block-icons/wiki)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/repos-1.png)

En la wiki hay un **índice** donde se muestran algunos de los iconos, pero en el repositorio hay muchísimos más, **agrupados por categorías**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/repos-2.png)

Todos los iconos están hecho con el [Inkscape](https://inkscape.org), y tienen una **licencia libre** para que cualquiera los pueda usar y modificar. Las **contribuciones** son muy bienvenidas. Anímate y añade tus contribuciones (pull requests) al repositorio

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/repos-3.png)

Además, puedes encontrar otros **iconos SVG libres** en estos repositorios:

* [OpenClipart](https://openclipart.org/)
* [Wikicommons](https://commons.wikimedia.org/wiki/Category:SVG_icons)

## ¡Comparte tus iconos! :-)

Si has creado iconos nuevos para tus bloques o diseños derivados, **compártelos** con el resto de la comunidad, publícándolos con una **licencia libre** (Por ejemplo [CC-BY-SA](https://creativecommons.org/licenses/by-sa/3.0/es/)) en el repositorio que quieras.

Cualquier **contribución** al [repositorio de iconos de Icestudio](https://github.com/FPGAwars/icestudio-block-icons/wiki) será muy bienvenida. Estas contribuciones te servirán como **ejercicio libre**, y también para obtener **bitpoints adicionales** (5 bitpoints por logo) hasta completar los bitpoints que podrías tener como máximo hasta el último tutorial que hayas hecho. Simplemente envía el pull-request.

La **tabla de bitpoints** que podrías tener según los tutoriales completados es:

| Tutorial |  Tope de Bitpoints acumulados |
|----------|--------------------|
| Tutorial 1 | 4                |
| Tutorial 2 | 10               |
| Tutorial 3 | 21               |
| Tutorial 4 | 31               |
| Tutorial 5 | 40               |
| Tutorial 6 | 51               |
| Tutorial 7 | 62               |
| Tutorial 8 | 80               |
| Tutorial 9 | 94               |
| Tutorial 10 | 110             |
| Tutorial 11 | 124             |
| Tutorial 12 | 140             |
| Tutorial 13 | 158             |
| Tutorial 14 | 172             |
| Tutorial 15 | 195             |
| Tutorial 16 | 220             |
| Tutorial 17 | 240             |
| Tutorial 18 | 260             |
| Tutorial 19 | 280             |
| Tutorial 20 | 300             |
| Tutorial 21 | 320             |

Así, por ejemplo, puedes estar por el tutorial 20, pero tener menos de 300 bitpoints, porque hay ejercicios de tutoriales anteriores que no has entregado, o porque no has hecho todos los ejercicios libres. Bien. Si compartes tus logos SVG puedes recuperar esos bitpoints

# Ejercicios propuestos (20 BitPoints)

Ver los detalles de los ejercicios y las **entregas** en el menú **Archivos/Ejemplos/2-Ejercicios** de la colección de este tutorial

**Resumen**:

* **Ejercicio 21.1** (Total **5 Bitpoints**): **Bloque pegatina con tu avatar**

Crea un bloque pegatina (sin puertos) con tu avatar, logo, foto, etc. Puedes usar imágenes de cualquier tamaño, sin embargo es mejor que las reduzcas para que el bloque ocupe menos espacio

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/Ejercicios-1.png)

* **Ejercicio 21.2** (Total **5 Bitpoints**): **Puerta AND del circuit Scramble**

Crear un **bloque** que implemente una **puerta AND** usando el icono del **Circuit Scramble**.  
El icono está disponible en este enlace: [AND-cs.svg](https://github.com/FPGAwars/icestudio-block-icons/raw/master/Circuit-scramble/AND-cs.svg)  

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/Ejercicios-2.png)

Hacer un **circuito de prueba**, con este nuevo bloque, usando **dos interruptores externos** para introducir bit por sus entradas y un **LED externo** conectado a la salida

* **Ejercicio 21.3** (Total **5 Bitpoints**): **Bloque Franky**
Diseñar un bloque para controlar a Franky. Tendrá **2 puertos de entrada** de un bit (además del de reloj). Uno hará que Franky dispare por sus ojos,  cuando se ponga a 1, y no dispare mientras esté a 0. El disparo es un parpadeo de los ojos a una frecuencia definida por el usuario mediante un parámetro. Por** defecto** será de **10Hz**. La otra entrada hará que Franky mire hacia un lado (1) o hacia el otro (0). Tendrá como salidas un **puerto de 2 bits** para los **LEDs de los ojos**, y uno de **un bit** para el **control del servo** del cuello. Tendrá un **parámetro** para especificar la frecuencia del parpadeo de los ojos en el disparo

El **icono** está disponible en este enlace: [Robot-face-1.svg](https://github.com/FPGAwars/icestudio-block-icons/raw/master/Robots/Robot-face-1.svg)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-21/Ejercicios-3.png)

Hacer un **circuito de prueba** del bloque, conectando la entrada de disparo a un pulsador y la del cuello a un interruptor

* **Ejercicio 21.4** (**5 Bitpoints**). Ejercicio Libre. Premiar la creatividad. **Entregar** por redes sociales o github: Pantallazos, enlaces, vídeos, etc...

# Ejercicios entregados

## Andrés (Avarez)

### Ejercicio 1
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-21/avarez/Ejercicio.21.1.png)

### Ejercicio 2
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-21/avarez/Ejercicio.21.2.and.bloque.png)

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-21/avarez/Ejercicio.21.2.png)


### Ejercicio 3
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-21/avarez/Ejercicio.21.3.png)

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-21/avarez/Ejercicio.21.3.franky.block.png)

* [Vídeo en Twitter](https://twitter.com/avarez_/status/1012994168275324930)

### Ejercicio 4
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-21/avarez/Ejercicio.21.4.png)

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-21/avarez/Ejercicio.21.4.conversor.bloque.png)

## Jose López

### Ejercicio 1

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-21/Jose%20Lopez/ejercicio_21-1.jpg)

### Ejercicio 2

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-21/Jose%20Lopez/ejercicio_21-2b.jpg)

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-21/Jose%20Lopez/ejercicio_21-2a.jpg)

### Ejercicio 3

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-21/Jose%20Lopez/ejercicio_21-3b.jpg)

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-21/Jose%20Lopez/ejercicio_21-3a.jpg)

* [Vídeo en Twitter](https://twitter.com/joselopez_ga/status/1013827294820028416)

## Federico Coca (fgcoca)

### Ejercicio 1
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-21/fgcoca/Ejercicio-1/Ejercicio21_1%20%E2%94%80%20P.png)

### Ejercicio 2
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-21/fgcoca/Ejercicio-2/Ejercicio21_2%20%E2%94%80%20P.png)

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-21/fgcoca/Ejercicio-2/2-Input-AND-gate-cs-Block%20%E2%94%80%20P.png)

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-21/fgcoca/Ejercicio-2/Project%20information%E2%94%80%20P.png)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/G0bL9ZzIVA8/0.jpg)](https://www.youtube.com/watch?v=G0bL9ZzIVA8)

### Ejercicio 3

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-21/fgcoca/Ejercicio-3/Ejercicio21_3%20%E2%94%80%20P.png)

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-21/fgcoca/Ejercicio-3/Franky-Block%20%E2%94%80%20P.png)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/U6-rn01fvjs/0.jpg)](https://www.youtube.com/watch?v=U6-rn01fvjs)

### Ejercicio 4
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-21/fgcoca/Circuit-scramble/AND-cs.svg?sanitize=true)

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-21/fgcoca/Circuit-scramble/OR-cs.svg?sanitize=true)

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-21/fgcoca/Circuit-scramble/XOR-cs.svg?sanitize=true)

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-21/fgcoca/Circuit-scramble/SWITCH-cs.svg?sanitize=true)

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-21/fgcoca/Circuit-scramble/INVERTER-cs.svg?sanitize=true)

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



