![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/Portada/Portada-Tutorial-8.png)

# Vídeo

[![Click to see the youtube video](http://img.youtube.com/vi/aWXtGDKhGVk/0.jpg)](https://www.youtube.com/watch?v=aWXtGDKhGVk&list=PLmnz0JqIMEzXaeYVzf2TfTzRekPIVoljw&index=8)

Haz click en la imagen para ver el **vídeo en Youtube**

# Descripción

La icezum Alhambra dispone de un total de **32 pines de E/S** repartidos en diferentes conectores. Aprenderemos a conectar **LEDs externos** a los pines de **3.3V** de la FPGA y cómo hacerlos **parpadear** desde circuitos en Icestudio. Veremos cómo hacer distintos tipos de **circuitos físicos** para colocar estos LEDs

# Colección

[Academia-Jedi-HW-08.zip](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/Collection/Academia-Jedi-HW-08.zip): Colección para este tutorial. Descargar e instalar 

# Contenido

* [Material necesario](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos#material-necesario)
* [Documentación de la Icezum Alhambra](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos#documentaci%C3%B3n-de-la-icezum-alhambra)
* [Pines de la Icezum Alhambra](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos#pines-de-la-icezum-alhambra)
  * [Conectores hembra de 5v](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos#conectores-hembra-de-5v)
  * [Conectores macho de 5v con alimentación y masa](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos#conectores-de-es-macho-de-5v-con-alimentaci%C3%B3n-y-masa)
  * [Conectores macho de E/S de 3.3V (GPx)](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos#conectores-de-es-macho-de-33v-gpx)
  * [Conectores macho para entradas analógicas](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos#conectores-macho-para-entradas-anal%C3%B3gicas)
* [Conectando un LED externo a los pines de 3.3V](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos#ejemplo-1-conectando-un-led-externo-a-los-pines-de-33v)
  * [Material necesario](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos#material-necesario-1)
  * [Esquema](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos#esquema)
  * [Esquema del montaje](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos#esquema-del-montaje)
  * [Montaje físico](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos#montaje-f%C3%ADsico)
  * [Circuito en Icestudio](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos#circuito-en-icestudio)
* [LEDs externos intermitentes](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos#ejemplo-2-leds-externos-intermitentes)
  * [Esquema de montaje](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos#esquema-del-montaje-1)
  * [Montaje físico](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos#montaje-f%C3%ADsico-1)
  * [Circuito en Icestudio](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos#circuito-en-icestudio-1)
* [Montando circuitos externos](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos#montando-circuitos-externos)
  * [Placas entrenadoras](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos#placas-entrenadoras)
  * [Conexiones directas](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos#conexiones-directas)
  * [Circuitos sobre Cartón o papel](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos#circuitos-sobre-cart%C3%B3n--papel)
    * [Montaje de Franky](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos#construcci%C3%B3n-de-franky)
  * [Circuito soldado en placas prototipos](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos#circuito-soldado-en-placas-prototipos)
  * [PCBprints](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos#circuitos-imprimibles-pcbprints)
  * [Circuitos Impresos (PCBs)](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos#circuitos-impresos-pcbs)
* [Ejercicios propuestos (18 Bitpoints)](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos#ejercicios-propuestos-18-bitpoints)
* [Ejercicios entregados](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos#ejercicios-entregados)
  * [Federico Coca](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos#federico-coca)
  * [Ricardo Gómez](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos#ricardo-g%C3%B3mez-eagleman)
  * [Diego Lale](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos#diego-lale)
* [Autor](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos#autor)
* [Licencia](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos#licencia)
* [Créditos y agradecimientos](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos#cr%C3%A9ditos-y-agradecimientos)
* [Enlaces](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos#enlaces)
* [FAQs](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos#faqs)


# Material necesario

Materia necesario para hacer los **ejemplos** y **ejercicios** del tutorial:

|  Foto   |  Material |
|---------|-----------|
| ![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/Material-01.jpg) | **Placa entrenadora** pequeña |
| ![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/Material-02.jpg) | **LED** pasante, de cualquier color. Tamaño 3mm ó 5mm. Mínimo 2 |
| ![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/Material-03.jpg) | **Resistencia** de 100 Ohmios, de 1/4 W. Al menos 2 |
| ![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/Material-04.jpg) | **Cable macho - hembra**. Al menos dos. Este cable se puede obtener uniendo un hembra-hembra con uno macho-macho |
| ![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/Material-05.jpg) | **Cable macho - macho**. Al menos dos |
| ![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/Material-06.jpg) | **Cable hembra - hembra**. Al menos dos |




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

Cada **entrada analógica** (Azul) tiene un pin adicional de **alimentación** (rojo, 5v) y otro de **masa** (negro, GND)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/pines-alhambra-10.png)

Estas tiras de 3 pines permiten **conectar directamente** sensores de **Luz** o **potenciómetros**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/pines-alhambra-11.jpg)

Aquí se pueden ver las conexiones con **más detalle**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/pines-alhambra-12.jpg)

La FPGA **NO** tiene entradas analógicas, por lo que en la Icezum Alhambra hay un **conversor Analógico-digital (A/D)** que se conecta a la FPGA a través de un **bus I2C**. Por ello, para leer las entradas analógicas es preciso **incluir** en nuestros diseños de un circuito capaz de **leer el bus I2C**

# Ejemplo 1: Conectando un LED externo a los pines de 3.3v

Vamos a **conectar** un **LED externo** y hacer que parpadee. Lo conectaremos a las salidas **GPx** de **3.3 Voltios**

## Material necesario

El material adicional a la [Icezum Alhambra](https://github.com/FPGAwars/icezum/wiki) para la conexión del **LED externo** es:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/Led-externo-2-material.jpg)

1. **Protoboard**. Placa de entrenamiento pequeña
2. **Cable Macho-hembra**
3. **Cable macho-macho**
4. **LED** pasante, de 5mm ó 3mm, de cualquier color
5. **Resistencia** pasante de 100 Ohm y 1/4W

## Esquema

El **esquema** para encender el LED externo es

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/Led-externo-3-material.jpg)

Como la salida es de **3.3V**, usamos una resistencia de **100 Ohm** en serie con el LED

## Esquema del montaje

El esquema del montaje se muestra en este **diagrama** hecho con [Fritzing](http://fritzing.org/home/) (Versión 0.9.3b)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/Led-externo-1-fritzing.png)

El **archivo** para abrir en Fritzing está  disponible en el repo de los tutoriales: [Ejemplo-1.fzz](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/Fritzing/Ejemplo-1.fzz)

## Montaje físico

El montaje del circuito lo haremos sobre una **base de corcho**. Esto nos permite utilizar **chinchetas** para **fijar** los cables y otros elementos. En este primer circuito no usaremos más piezas, pero en los siguientes iremos colocando **piezas impresas** para amarrar los **sensores** y **actuadores** al corcho

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/Led-externo-montaje.jpg)

## Circuito en Icestudio

Para hacer **parpadear** el LED usaremos el circuito que ya conocemos, con un **corazón de 1Hz** (por ejemplo). Bien lo podemos cargar directamente desde los ejemplos, en el menú **Archivo/Ejemplos/1-Ejemplos/01-LED-externo-parpadeante**, o bien lo creamos desde cero. En esta colección el Bombeo de bits está bajo el **menú Varios**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/Led-externo-1-icetudio.png)

**Cargamos** el circuito en la placa, y podremos ver el LED externo parpadeando

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/Led-externo-1-anim.gif)

# Ejemplo 2: LEDs externos intermitentes

Conectaremos ahora **dos LEDs externos**, a las salidas **GP0** y **GP7** respectivamente, y haremos que **parpadeen alternativamente**

El esquema es el mismo que en el ejemplo anterior, pero ahora con **2 LEDs**, **2 resistencias** y **4 cables**

## Esquema del montaje

El esquema de montaje en **Fritzing** es

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/Leds-alternantes-fritzing.png)

Se ha duplicado el circuito del ejemplo 1 y se han conectado los cables a diferentes puntos

## Montaje físico

Partiendo del montaje del ejemplo anterior, añadidos los nuevos componentes para conectar el **segundo LED**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/Leds-alternantes-montaje.jpg)

## Circuito en Icestudio

El circuito de los **leds parpadeando alternativamente** ya lo sabemos hacer. Bien lo hacemos desde 0 o bien lo abrimos desde los ejemplos a través del menú **Archivo/Ejemplos/1-Ejemplos/02-LEDS-externos-alternantes**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/Leds-alternantes-icestudio.png)

**Cargamos** el circuito y veremos los **dos LEDs** en acción:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/Leds-alternantes-anim.gif)


# Montando circuitos externos

Los **circuitos externos** para trabajar con placas como la Icezum Alhambra o Arduino se pueden realizar de diferentes maneras. Aquí mostraremos algunas de ellas

## Placas entrenadoras

Una forma es utilizando [protoboards o placas de pruebas](https://es.wikipedia.org/wiki/Placa_de_pruebas). Es lo que hemos usado en los ejemplos 1 y 2

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/Circuitos-externos-1.jpg)

## Conexiones directas

Cuando se trata de componentes sencillos, como LEDs y resistencias, se pueden hacer **conexiones directas**. Por ejemplo, **enrollando** la pata de la resistencia de **100 ohm** con el **LED**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/Circuitos-externos-2.png)

Luego usamos **dos cables hembra-hembra** para insertar la **pata del LED** en un cable y la de la **resistencia** en otro

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/Circuitos-externos-3.jpg)

Por último **conectamos** el cable del LED a cualquier de las **salidas GPx de 3.3V** y el cable de la pata de la resistencia a cualquier **pin macho negro**, que son **GND**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/Circuitos-externos-4.jpg)

## Circuitos sobre cartón / papel

Mediante la misma técnica de **conexiones directas**, pero usando un **papel / cartón** de soporte, se pueden hacer circuitos externos muy divertidos. Este es **Franky**: 

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/Franky-anim.gif)

Es un **robot de cartón** cuyos **ojos** son dos **LEDs**, y su **nariz** y **boca** **resistencias** de 100 Ohm

### Construcción de Franky

Se parte de un **trozo de cartón o cartulina**, alargado, como se muestra en la foto. Con una **chincheta** se hacen **agujeros** para introducir los dos **LEDs** y las dos **resistencias** de 100 Ohm

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/Franky-02.jpg)

Por la parte de atrás del cartón **unimos** las patas de los LEDs con sus respectivas resistencias. Los patas positivas del led (las patas largas) las dejamos sin unir. Las patas de las resistencias que no están unidas a los LEDS, las unimos entre sí, dejando un trozo de pata recto al final que sobresalga

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/Franky-03.jpg)

Luego conectamos **tres cables hembra-hembra**, uno para cada LED y otro para las patas unidas de la resistencia, que van a masa

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/Franky-04.jpg)

**Plegamos** el cartón, para darle forma de **caja**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/Franky-05.jpg)

Y lo **cerramos**. Pegamos los laterales con celo

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/Franky-06.jpg)

Los **cables** los sacamos por **la parte trasera**, por un hueco recortado en la parte inferior y colocamos **dos chinchetas** en los lateras, para darte un aspecto más de **Frankenstain** :-)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/Franky-07.jpg)

Ponemos un poco de **cinta aislante** para juntar los **cables**. Y usamos una **chincheta** para **fijar a Franky al corcho**. **Conectamos** los positivos de los LEDs a los pines **GP0** y **GP7** de la Icezum, y el otro cable a cualquier de los **pines machos negro de GND**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/Franky-08.jpg)

Hacemos un **rectángulo de papel** con unos dobleces, de las dimensiones de la parte superior de la cabeza de franky. Lo usaremos como tapa

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/Franky-09.jpg)

Y se la **colocamos**. La pegamos en los laterales con un poco de celo. **¡Ya tenemos a Franky Listo!**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/Franky-10.jpg)

## Circuito soldado en placas prototipos

Una opción para hacer **circuitos externos más robustos** es usar **placas de puntos** donde se sueldan los componentes. Se vende en placas de **tamaños fijos** que se pueden cortar fácilmente con una **segueta** para tener el tamaño de placa que queramos. Se colocan lo componentes, se sueldan y se usen con cables. En el caso de la placa del LED, como es muy sencilla, he usado las mismas patas de los componentes, en vez de cables

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/Circuitos-externos-5.jpg)

La **conexión** se puede realizar directamente con **cables hembra - hembra**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/Circuitos-externos-06.jpg)

O pinchando la placa en una **protoboard**, y tirando cables macho - hembra

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/Circuitos-externos-07.jpg)

## Circuitos imprimibles (PCBPrints)

Una opción muy divertida y sencilla es utilizar [PCBprints](https://github.com/PCBPrints/PCbPrints). Son placas hechas con una **impresora 3D**, donde se colocan los componentes y luego se sueldan. La más sencilla de todas es ["Hola Mundo"](https://github.com/Obijuan/3D-parts/wiki/PCB-Led-hola-mundo), que sólo tiene un **LED**, una **resistencia** y un **conector macho**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/Circuitos-externos-08.jpg)

En [este enlace están las instrucciones de montaje](https://github.com/Obijuan/3D-parts/wiki/PCB-Led-hola-mundo#instrucciones-de-montaje)

Igual que las placas anteriores, se pueden **conectar directamente** a la Icezum Alhambra usando **cables hembra - hembra**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/Circuitos-externos-09.jpg)

O también se pueden conectar a través de una **protoboard**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/Circuitos-externos-10.jpg)

## Circuitos impresos (PCBs)

Por último, la opción más **profesional** es hacerte tu propio **PCB** y mandarlo a **fabricar industrialmente**. Una herramienta libre para diseñar PCBs es [Kicad](http://kicad-pcb.org/), que ya lo usaste para los ejercicios del [tutorial 3](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-3:-La-Icezum-Alhambra-y-otras-placas-con-FPGAs-libres)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-08/Circuitos-externos-11.jpg)

Esta es la [placa FreeLEDs](http://www.iearobotics.com/wiki/index.php?title=Freeleds), que hicimos en el año **2005** y que fue una de las **primeras placas libres** hecha exclusivamente usando **software libre** :-)

# Ejercicios propuestos (18 BitPoints)

Ver los detalles de los ejercicios y las **entregas** en el menú **Archivos/Ejemplos/2-Ejercicios** de la colección de este tutorial

**Resumen**:

* **Ejercicio 1** (Total **3 Bitpoints**): Hacer un circuito digital que haga parpadear
alternativamente dos LEDs externos, conectados en una protoboard, a la velocidad de 2Hz

* **Ejercicio 2** (Total **4 Bitpoints**): Hacer un circuito digital para que los dos ojos de Franky 
parpadeen a la vez, a la velocidad de 4Hz. Es necesario construir a **Franky**

* **Ejercicio 3** (Total **8 Bitpoints**): Montar al menos una **PCBprint** con un led y conectarlo a la
Icezum Alhambra. Hacer que parpadee a la frecuencia de 1Hz. Se concecerán bitpoints extras por
montar y poner más de un PCBprint (hasta un máximo de 5 PCBprints). Si has puesto más de 1 LED, 
dividirlos en dos grupos y hacer que parpadeen alternativamente a 1Hz

* **Ejercicio 4** (**3 Bitpoints**). Ejercicio Libre. Premiar la creatividad. **Entregar** por redes sociales o github: Pantallazos, enlaces, vídeos, etc...

# Ejercicios entregados

## Federico Coca

### Ejercicio 1

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/blob/master/Tutorial-8/fgcoca/Ejercicio-1/Ejercicio8_1-P.png)

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-8/fgcoca/Ejercicio-1/Ejercicio8_1-F.jpg)

* **Vídeo**

[![Click to see the youtube video](http://img.youtube.com/vi/hMsPvRHlL1U/0.jpg)](https://www.youtube.com/watch?v=hMsPvRHlL1U)

## Ejercicio 2

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-8/fgcoca/Ejercicio-2/Ejercicio8_2-P.png)

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-8/fgcoca/Ejercicio-2/Franky-Blue-Eyes.jpg)

**Vídeo**:

[![Click to see the youtube video](http://img.youtube.com/vi/BAxxuT5_QDY/0.jpg)](https://www.youtube.com/watch?v=BAxxuT5_QDY)

## Ricardo Gómez (eagleman)

### Ejercicio 1

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-8/eagleman/ejercicio-8-1.ice.png)

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-8/eagleman/ejercicio-8-1.JPG)

### Ejercicio 2

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-8/eagleman/ejercicio-8-2.ice.png)

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-8/eagleman/ejercicio-8-2.conexiones1.JPG)

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-8/eagleman/ejercicio-8-2.conexiones2.JPG)

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-8/eagleman/ejercicio-8-2.final.JPG)

* [VIDEO](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-8/eagleman/ejercicio-8-2.mp4)

### Ejercicio 3

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-8/eagleman/ejercicio-8-3.ice.png)

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-8/eagleman/ejercicio-8-3.JPG)

* [VIDEO 1](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-8/eagleman/Ejercicio-8-3-parte1.m4v)
* [VIDEO 2](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-8/eagleman/Ejercicio-8-3-parte2.m4v)

## Diego Lale

### Ejercicio 1

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-8/Diego%20Lale/ejercicio1.png)

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-8/Diego%20Lale/ejercicio1-1.jpg)

### Ejercicio 2

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-8/Diego%20Lale/ejercicio2.png)

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-8/Diego%20Lale/ejercicio2-1.jpg)

## Ejercicio 3

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-8/Diego%20Lale/ejercicio3.png)

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-8/Diego%20Lale/ejercicio-3-1.jpg)

## Ejercicio 4

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-8/Diego%20Lale/ejercicio4.png)

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-8/Diego%20Lale/ejercicio4-1.jpg)

# Autor

* [Juan González-Gómez](https://github.com/Obijuan) (Obijuan)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/logos-urjc-gsyc-peloto-jderobot.png)

# Licencia

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/attribution-share-alike-creative-commons-license.png)

# Créditos y agradecimientos

* A [Alberto Piganti](http://www.pighixxx.com/test/) (Pighixxx) por hacer la documentación del pinout de la Icezum Alhambra. ¡Muchas Gracias! :-)
* A [Jorge Lobo](https://github.com/lobotic) (Lobotic) Por incluir la [Icezum Alhambra en Fritzing](https://github.com/lobotic/IceZUM_Alhambra_Fritzing). ¡Muchas gracias! :-)

# Enlaces

* [Repositorio con las colecciones de la Academia Jedi de Hardware](https://github.com/Obijuan/Academia-Jedi-Hw)
* [BricoGeek](http://tienda.bricogeek.com/). Tienda Friki donde comprar componentes electrónicos
* [Repositorio de la Icezum Alhambra](https://github.com/FPGAwars/icezum/wiki)
* Documentación de la Icezum Alhambra:  ([PNG](https://github.com/FPGAwars/icezum/raw/master/doc/pinout/icezum-pinout.png))([SVG](https://github.com/FPGAwars/icezum/raw/master/doc/pinout/Icezum-alhambra-pinout.svg))([PDF](https://github.com/FPGAwars/icezum/raw/master/doc/pinout/icezum-pinout.pdf)) 
* [Monedas Bit imprimibles](https://github.com/Obijuan/3D-parts/wiki/Monedas-Bit)

# FAQs

* **¿Dónde puedo conseguir la placa Icezum Alhambra?**

Pueden conseguir una desde [Alhambrabits](https://alhambrabits.com/buy/)

* **¿Cómo aprendo a manejar github?**

Hay mucha información en internet. En su momento hice este Tutorial: [Github y FreeCAD](http://www.iearobotics.com/wiki/index.php?title=Tutorial:_Github_y_Freecad) para enseñar a manejarlo. Los ejemplos están hechos con ficheros de FreeCAD, sin embargo, lo que se enseña es genérico. También vale para las entregas de los ejercicios del tutorial de Electrónica digital para makers






