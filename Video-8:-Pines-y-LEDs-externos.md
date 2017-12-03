![]()

# Vídeo

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

Haz click en la imagen para ver el **vídeo en Youtube**

# Descripción


# Colección

**Academia-Jedi-HW-08.zip**: Colección para este tutorial. Descargar e instalar 

# Contenido

* [Material necesario](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos#material-necesario)
* [Documentación de la Icezum Alhambra](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos#documentaci%C3%B3n-de-la-icezum-alhambra)
* [Pines de la Icezum Alhambra](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos#pines-de-la-icezum-alhambra)
  * [Conectores hembra de 5v](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos#conectores-hembra-de-5v)
  * [Conectores macho de 5v con alimentación y masa](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos#conectores-de-es-macho-de-5v-con-alimentaci%C3%B3n-y-masa)
  * [Conectores macho de E/S de 3.3V (GPx)](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos#conectores-de-es-macho-de-33v-gpx)
  * [Conectores macho para entradas analógicas](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos#conectores-macho-para-entradas-anal%C3%B3gicas)

# Material necesario

TODO

# Documentación de la Icezum Alhambra

La documentación de la placa [Icezum Alhambra](https://github.com/FPGAwars/icezum/wiki) está resumida en este **diagrama**, realizado por [Alberto Piganti](http://www.pighixxx.com) (¡Gracias!)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/icezum-pinout.png)

Está disponible en **otros formatos**: ([PNG](https://github.com/FPGAwars/icezum/raw/master/doc/pinout/icezum-pinout.png))([SVG](https://github.com/FPGAwars/icezum/raw/master/doc/pinout/Icezum-alhambra-pinout.svg))([PDF](https://github.com/FPGAwars/icezum/raw/master/doc/pinout/icezum-pinout.pdf))

En este diagrama hay mucha información. Vamos a **analizar** la parte que nos es más familiar: los **LEDS** de la placa. Si miramos el diagrama veremos esto:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/icezum-pinout-2.png)

Junto a cada **pin/LED** hay unos cuadros con la **siguiente información**:

* **Pin físico**: Es el **número de pin** del encapsulado de la FPGA. En la Icezum alhambra, el encapsulado de la FPGA es un **TQ144**, y la numeración de los pines es como se muestra en la siguiente figura. También se han incluido los **pines de los leds**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/icezum-pinout-3.png)

* **Nombre del pin**. Es el nombre asignado por Lattice, con independencia del encapsulado (Ya que cada encapsulado tiene una numeración diferente). Así, el pin denominado **1_62** es una salida de la FPGA que está en el banco 1 y que para los encapsulados TQ144 sale por el pin físico 95, pero saldrá por otro en un encapsulado diferente

* **Nombre en Icestudio**. Es el nombre que se le asigna en los bloques amarillos de Icestudio

* **Tipo de pin**. Indica de qué tipo es el pin. Las flechas blancas con fondo naranja significa que se trata de un LED

La información de la placa también está disponible desde el menú **Ver/Pinout** de Icestudio

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/icezum-pinout-4.png)

Al pulsar la opción de Pinout se nos abre **una ventana con la documentación** de la Icezum Alhambra. Si tenemos seleccionada otra placa, saldrá su propia documentación

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/icezum-pinout-5.png)

Sobre esta ventana podemos hacer **zoom y navegar**. En el caso de la icezum Alhambra, la documentación que se muestra en **icestudio 0.3.1** está **obsoleta**. Hay una más moderna en el repo, que es la que se recomienda usar. En las siguientes versiones de Icestudio se actualizará

# Pines de la Icezum Alhambra

La placa [Icezum Alhambra](https://github.com/FPGAwars/icezum/wiki) tiene **4 tipos de pines** para conectarse al exterior, resumidos en este **diagrama**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/pines-alhambra-01.png)

Estos **conectores** son:

**1.** Conectores de E/S hembra de **5 Voltios**  
**2.** Conectores de E/S macho de **5 Voltios**, con alimentación y masa  
**3.** Conectores de E/S macho de **3.3 Voltios**  
**4.** Conectores macho para **entradas analógicas**  

## Conectores hembra de 5V

Son los **típicos conectores de Arduino** que sirven para conectar **cables macho** y **shields** de expasión. Se encuentran en la parte superior e inferior de la placa, como se muestra en la figura

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/pines-alhambra-02.png)

En total hay **31 pines**, de los cuales **20** son de **E/S de 5v**. Los pines de E/S superiores se denominan **D13** - **D0** en Icestudio, y los inferiores **DD5** - **DD0**. Todos estos pines tienen la característica de que son de **5v**. Como los pines de la FPGA son de 3.3 Voltios, se pasan a través de unos **conversores bidireccioie* nales de 3V3 - 5v**. Por ello, **no están conectados directamente a los pines de la FPGA**, y sus características las **determinan estos conversores**.

## Conectores de E/S macho de 5V con alimentación y masa

Son **20 pines de E/S**, machos, **dulicados** de los 20 pines E/S de los conectores hembra de 5v

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/pines-alhambra-03.png)

Cada uno de estos pines incluye uno adicional de **alimentación (+5v)** y **masa (GND)**. En total son tres pines separados por colores. El **pin blanco** contiene la señal de E/S, el **rojo** la alimentación de 5v y el **negro** la masa (GND)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/pines-alhambra-04.png)

Tienen esta disposición para poder **conectar directamente servos y sensores**. Se denominan igual que sus duplicados hembra: **D0** - **D13** para los de la parte superior y **DD0** - **DD5** en la parte inferior. En esta foto se muestra un **servo** conectado al pin **D0** y un sensor de infrarrojos en el **D13**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/pines-alhambra-5.jpg)

Aquí se muestran más **detalles** de la conexión a los pines machos

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/pines-alhambra-6.jpg)

## Conectores de E/S macho de 3.3V (GPx)

Son **8 pines** macho dispuestos en dos filas de 4 pines, de color **amarillo**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/pines-alhambra-07.png)

Los 8 pines están **conectados directamente** a pines de la FPGA, que trabajan a **3.3V**. Los pines hembra y macho anteriores están conectados a la FPGA a través de conversores de nivel. Se denotan con la nomenclatura **GP0** - **GP7**. Esta es la **disposición de los pines**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/pines-alhambra-08.png)

## Conectores macho para **entradas analógicas** 

La Icezum Alhambra tiene **4 entradas analógicas** situadas en la parte derecha, accesibles a través de **pines macho**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/pines-alhambra-09.png)

Cada entrada analógica (Azul) tiene un pin adicional de **alimentación** (rojo, 5v) y otro de **masa** (negro, GND)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/pines-alhambra-10.png)



# Ejemplo 1: Encender led externo

# Borrador

-Dos leds intermitentes
-Semaforo
-Robot con ojos alternates (maqueta en cartón)
-PCBprint?

# Ejercicios propuestos (11 BitPoints)

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
* [Monedas Bit imprimibles](https://github.com/Obijuan/3D-parts/wiki/Monedas-Bit)

# FAQs

* **¿Dónde puedo conseguir la placa Icezum Alhambra?**

Pueden conseguir una desde [Alhambrabits](https://alhambrabits.com/buy/)

* **¿Cómo aprendo a manejar github?**

Hay mucha información en internet. En su momento hice este Tutorial: [Github y FreeCAD](http://www.iearobotics.com/wiki/index.php?title=Tutorial:_Github_y_Freecad) para enseñar a manejarlo. Los ejemplos están hechos con ficheros de FreeCAD, sin embargo, lo que se enseña es genérico. También vale para las entregas de los ejercicios del tutorial de Electrónica digital para makers






