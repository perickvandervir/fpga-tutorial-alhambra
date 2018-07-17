![]()

(En construcción...)
# Vídeo

(En construcción...)

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

Haz click en la imagen para ver el **vídeo en Youtube**

# Descripción

TODO

# Colección

**Academia-Jedi-HW-23.zip**: Colección para este tutorial. Descargar e instalar 

# Contenido

* [Introducción](#introducci%C3%B3n)
* [Carpeta de datos de Icestudio](#carpeta-de-datos-de-icestudio)
  * [GNU/Linux](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-23:-Mi-primera-colecci%C3%B3n#gnulinux)
  * [Windows 10](#windows-10)
  * [Mac](#mac)
* [Colecciones](#colecciones)
  * [Ejemplo 1: Duplicando una colección](#ejemplo-1-duplicando-una-colecci%C3%B3n)
  * [Estructura de las colecciones](#estructura-de-las-colecciones)
* Ejercicios propuestos (X Bitpoints)
* [Ejercicios entregados](#ejercicios-entregados)
* [Autor](#autor)
* [Licencia](#licencia)
* [Enlaces](#enlaces)
* [Preguntas frecuentes](#preguntas-frecuentes)

# Introducción

Las **colecciones de Icestudio** nos permiten **organizar** los bloques y los ejemplos. Con ellas podemos estructurar lo que queremos enseñar, mostrando sólo lo que es relevante. Un ejemplo de uso son estos tutoriales, donde hay una colección por cada vídeo, en la que se añaden los nuevos **bloques** que se verán, los **ejemplos** de uso, los **ejercicios propuestos** y las **soluciones** a los ejercicios del tutorial anterior

Las colecciones están pensadas para que cada uno las **adapte** a lo que necesita. Por ejemplo se podrían crear colecciones para cada **proyecto**, o colecciones donde se recopilan los problemas de tal libro de electrónica digital, o bibliotecas de componentes...

Pero lo más importante es que **las colecciones se pueden compartir**. De esta forma, entre todos, podemos **reutilizar** el trabajo de los demás, **aprender**, **mejorarlo** y contribuir al incremento del **patrimonio tecnológico de la humanidad**

# Carpeta de datos de Icestudio

Cuando se instala **Icestudio**, se crea una **carpeta de datos**, dentro de nuestra **carpeta de usuario**, donde se almacenan las **preferencias**, las **colecciones** instaladas, el entorno de **python** y las **herramientas** necesarias para sintetizar los circuitos (Toolchain)

La ruta exacta depende del **sistema operativo** que estemos usando. Dentro de ella encontrarmos tres carpetas: **apio**, **collections**, **venv**, y el fichero de configuración **profile.json**

## GNU/Linux

 En el caso las máquinas **GNU/Linux**, la carpeta de datos está en nuestro **home**, con el nombre **.icestudio**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/Icestudio-data-01.png)

**¡Importante!** En Linux los directorio que empiezan con un punto están **ocultos** por defecto (no se ven). Para poder veerlos hay que activar la opción **Mostrar ficheros ocultos** en el navegador de archivos, o pulsar directamente  **Control-H**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/Icestudio-data-02.gif)

Una forma **muy cómoda** de acceder es añadiendo un **marcador**. Así sólo tenemos que pinchar en la carpeta **.icestudio** que aparece en la **barra de la izquierda**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/Icestudio-data-03.gif)

## Windows 10

En las máquinas Windows 10 podemos encontrar el directorio de datos de Icestudio dentro de nuestra **carpeta de usuario**, en la carpeta **.icestudio**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/Icestudio-data-04.png)

Se llega a ella pinchando en la **flechita** que apunta hacia abajo. Ahí seleccionamos el nombre de nuestro usuario

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/Icestudio-data-05.png)

Y también se puede llegar a través de la **ruta completa**:  Equipos - OS(C:) - usuarios - obijuan - .icestudio

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/Icestudio-data-06.png)

## Mac

TODO

# Colecciones

Las **colecciones instaladas** se encuentran en la **carpeta de colecciones**, que tiene el nombre **collections**. A partir de ahora la estructura de los directorio no depende del Sistema operativo, por lo que usaré pantallazos del que uso yo: **GNU/Linux/Ubuntu 18.04**

Partiremos de un Icestudio que sólo tenga instalada **una colección**: la correspondiente a este tutorial: **Academia-Jedi-HW-23**. Desde el menú **Seleccionar/Colección** lo comprobamos

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/collection-01.png)

Si ahora nos **metemos** en la carpeta collections, veremos que hay **una carpeta** con el nombre de la colección instalada: **Academia-Jedi-HW-23**. Cada vez que **instalamos** una colección en icestudio, se descomprimirá en este directorio. Así, dentro de collections existirá **una carpeta por cada colección instalada**. Como ahora sólo tenemos instalada una sola colección, sólo aparece una carpeta

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/collection-02.png)

## Ejemplo 1: Duplicando una colección

Vamos a crear **nuestra primera colección** duplicando la que ya tenemos instalada. Nos vamos a la carpeta de colecciones de icestudio y **duplicamos** la carpeta de la colección instalada (usando copy & paste por ejemplo). Luego le **cambiamos** el nombre a **test-1**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/collection-03.png)

En esta **animación** se muestra el proceso

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/collection-04.gif)

Ahora nos vamos a la ventana de **Icestudio** y pinchamos en la opción **Herramientas/Colecciones/Reload**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/collection-05.png)

Volvemos a ver las colecciones que tenemos **instaladas**, yendo a la opción **Seleccionar/Colección**. Ahí nos aparecerá la **nueva colección test-1**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/collection-06.png)

Cualquier **cambio** que hagamos dentro de la carpeta de colecciones (collections) se ***reflejará** en Icestudio. Los cambios se **actualizarán** al **arrancar** Icestudio, al **abrir una ventana nueva** o bien al darle a la opción de **Reload**

**Seleccionamos** la nueva colección **test-1**. En los siguientes ejemplos la modificaremos. Todo el proceso se resume en esta **animación**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/collection-07.gif)

## Estructura de las colecciones

Todas las colecciones tienen la **misma estructura**. Nos metemos dentro de la carpeta **test-1** para ver cómo está organizada

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/collection-08.png)

Todos los elementos son **opcionales**, salvo el fichero **package.json**


| Elemento         | Obligatorio | Descripción |
|------------------|-------------|-------------|
| **package.json** | **SI**      | **Información** sobre la colección: nombre, versión, autores, repo... Icestudio necesita este fichero para reconocerlo como una colección |
| **blocks**       | NO          | Carpeta con los **bloques** de la colección. Su contenido se muestra en la parte superior derecha del **menú de Icestudio**| 

* **examples**: Carpeta con los **ejemplos** de la colección. Su contenido se muestra en el **menú Archivo/Ejemplos**
* **locale**: Carpeta con las traducciones a diferentes idiomas
* **README.md**: Información de la colección, para humanos. Su contenido se muestra en la opción **Ver/Informacón de la coleción**
* **LICENSE**: Fichero de texto con la licencia de la colección

(TODO)

# Ejercicios propuestos (X BitPoints)

Ver los detalles de los ejercicios y las **entregas** en el menú **Archivos/Ejemplos/2-Ejercicios** de la colección de este tutorial

**Resumen**:

* **Ejercicio 22.1** (Total **x Bitpoints**): 

* **Ejercicio 22.2** (Total **x Bitpoints**): 

* **Ejercicio 22.3** (Total **x Bitpoints**): 

* **Ejercicio 22.4** (**5 Bitpoints**). Ejercicio Libre. Premiar la creatividad. **Entregar** por redes sociales o github: Pantallazos, enlaces, vídeos, etc...

# Ejercicios entregados

## Primero

### Ejercicio 22.1
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 22.2
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 22.3
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 22.4
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()


## Segundo

### Ejercicio 22.1
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 22.2
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 22.3
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 22.4
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

## Tercero

### Ejercicio 22.1
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 22.2
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 22.3
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 22.4
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



