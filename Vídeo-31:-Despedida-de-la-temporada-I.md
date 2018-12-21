![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-31/Portada/Tut-31-portada.png)

# Vídeo

[![Click to see the youtube video](http://img.youtube.com/vi/GZWLwvGn088/0.jpg)](https://www.youtube.com/watch?v=GZWLwvGn088&index=48&list=PLmnz0JqIMEzXaeYVzf2TfTzRekPIVoljw)

Haz click en la imagen para ver el **vídeo en Youtube**

# Descripción

**Último** vídeo de la **Temporada I**. Haremos un repaso de lo que ha avanzado el **ecosistema de las FPGAs libres** durante este año. Han aparecido muchas placas, y las herramientas siguen evolucionando para soportar **más modelos de FPGAs**. Como ejemplo de la **colección Jedi**, veremos cómo usar el **conversor analógico-digital**

# Contenido

* [Evolución de las FPGAs libres](#evoluci%C3%B3n-de-las-fpgas-libres)
  * [Placas incorporadas en Icestudio](#placas-incorporadas-en-icestudio)
    * [Alhambra II](#alhambra-ii)
    * [TinyFPGA-BX](#tinyfpga-bx)
    * [Icebreaker](#icebreaker)
    * [BlackIce-II](#blackice-ii)
    * [Upduino v2.0](#upduino-v20)
    * [Ice40 UltraPlus Breackout Board](#ice40-ultraplus-breakout-board)
  * [Otras Placas](#otras-placas)
    * [TinyFPGA EX](#tinyfpga-ex)
    * [ULX3S](#ulx3s)
  * [Nuevas herramientas](#nuevas-herramientas)
    * [Proyecto Icestorm](#proyecto-icestorm)
    * [Symbiflow](#symbiflow)
      * [Herramientas software](#herramientas-software)
      * [Documentación de las FPGAs](#documentaci%C3%B3n-de-las-fpgas)
* [Colección Jedi](#colecci%C3%B3n-jedi)
  * [Bloque para lecturas analógicas](#bloque-para-lecturas-anal%C3%B3gicas)
  * [Ejemplo 1: Lectura de un potenciómetro](#ejemplo-1-lectura-de-un-potenci%C3%B3metro)
  * [Ejemplo 2: Envío de muestras al PC por el puerto serie](#ejemplo-2-env%C3%ADo-de-muestras-al-pc-por-el-puerto-serie)
  * [Ejemplo 3: Movimiento de un servo con el potenciómetro](#ejemplo-3-movimiento-de-un-servo-con-el-potenci%C3%B3metro)
* [Rango de Caballero Jedi](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-31:-Despedida-de-la-temporada-I#rango-de-caballero-jedi) 
* [Los 3 primeros certificados emitidos](#los-3-primeros-certificados-emitidos)
  * [Ximo Catala](#ximo-catala)
  * [Josep Montoliu](#josep-montoliu)
  * [Federico Coca](#federico-coca)
* [Soluciones a los ejercicios del tutorial 30: Puerto serie](#soluciones-a-los-ejercicios-del-tutorial-30-puerto-serie)
  * [Ejercicio 30.1: Transmisión de dos cadenas](#ejercicio-301-transmisi%C3%B3n-de-dos-cadenas)
  * [Ejercicio 30.2: Contador de pasadas del spiner](#ejercicio-302-contador-de-pasadas-del-spiner)
  * [Ejercicio 30.3: Control de Franky por puerto serie](#ejercicio-303-control-de-franky-por-puerto-serie)
* [Estadísticas del tutorial](#estad%C3%ADsticas-del-tutorial)
* [Autor](#autor)
* [Licencia](#licencia)
* [Enlaces](#enlaces)
* [Preguntas frecuentes](#preguntas-frecuentes)



# Evolución de las FPGAs libres

La **temporada I** de los tutoriales empezó el **13 de Octubre de 2017**. Ahora estamos a **20 de Diciembre de 2018**. Han sucedido muchas cosas desde ese primer tutorial. La comunidad ha crecido, y ha avanzado tanto que muchas de las cosas comentadas al comienzo del curso han quedado obsoletas. Y eso es muy bueno, significa que avanzamos a un **gran ritmo :-)**

## Placas incorporadas en Icestudio

En la comunidad han aparecido más placas, que no existían cuando se hizo el [Tutorial 3: La icezum Alhambra y otras placas con FPGAs libres](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-3:-La-Icezum-Alhambra-y-otras-placas-con-FPGAs-libres)

### Alhambra II

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-31/Alhambra-II.jpg)

| Ficha             |            |
|-------------------|------------|
| **Nombre**        | [Alhambra](https://github.com/FPGAwars/Alhambra-II-FPGA/wiki)  |
| **Autor**         | Eladio Delgado
| **Fabricante**    | [Mareldem Technologies](http://mareldem.com/), Pinos del valle, Granada, España  |
| **Donde conseguirla** | [Alhambrabits](https://alhambrabits.com)
| **Precio**        | 50€ + IVA  |
| **FPGA**          | ICE40Hx4K |
| **Frecuencia**    | 12Mhz      |
| **Periféricos**   | 8 LEDs, 2 pulsadores, 4 canales A/D  |
| **Observaciones** | Hardware libre. Compatible Arduino |

Es la **evolución** de la Icezum Alhambra. Los **cambios más importantes** de la Alhambra II con respecto a la anterior son (Más información en [este hilo de FPGAwars](https://groups.google.com/forum/#!searchin/fpga-wars-explorando-el-lado-libre/alhambra$20II|sort:date/fpga-wars-explorando-el-lado-libre/flvaYt9nCaA/GVbCpPvPAQAJ
)):

* **FPGA ice40HX4K**, que es equivalente a una **8K**. Podemos meter circuitos **8 veces mayores**. En ella se pueden sintetizar fácilmente microprocesadores como el **Latuino** o el **picorisv32**
* **GPIOs** a **3.3V tolerante a 5V** (como entrada acepta niveles entre 3.3 y 5V, como salida genera 3.3V)
* **Alimentación** por **USB** (dos conectores), hasta **4.8A**, para alimentarla con **power bank** y tener más corriente para los servos
* Los pines de **selección de bitstream** para **cold boot** están accesibles en el GPIO
* **Reguladores conmutados** de **1A** para las alimentaciones de 1.2 y 3.3V, lo que permitirá activar los **PLLs** y trabajar a velocidades mucho mayores.
* **Pines analógicos** integrados en los pines **D0** a **D3** (sólo 4 de los 6 pines del header son analógicos) para mayor compatibilidad con Arduino
* Pulsadores de usuario más cómodos de accionar (3 veces menos fuerza por unidad de superficie que los anteriores)

### TinyFPGA-Bx

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-31/tiny.jpg)

| Ficha             |            |
|-------------------|------------|
| **Nombre**        | [TinyFPGA](https://www.crowdsupply.com/tinyfpga/tinyfpga-bx)  |
| **Autor**         | [Luke Valenty](https://github.com/tinyfpga)
| **Donde conseguirla** | [Crowdsupply](https://www.crowdsupply.com/tinyfpga/tinyfpga-bx)
| **Precio**        | $38  |
| **FPGA**          | ICE40LP8K |
| **Frecuencia**    | 16 MHz      |
| **Periféricos**   | 1 LED  |
| **Observaciones** | Hardware libre |

La **TinyFPGA** es del tamaño de un **Arduino nano**. Se puede insertar en una **protoboard** para hacer nuestros prototipos. Se conecta por el USB para la descarga de diseños, pero en vez de llevar un chip externo para ello (un FTDI), tiene un [bootloader hardware](https://github.com/tinyfpga/TinyFPGA-Bootloader). La FPGA por defecto está configurada como un **controlador USB** y al cargar nuestro diseño se re-configura. Al apretar el **botón de reset** se re-configura otra vez al estado inicial

### IceBreaker

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-31/icebreaker-01.jpg)

| Ficha             |            |
|-------------------|------------|
| **Nombre**        | [Icebreaker](https://github.com/icebreaker-fpga/icebreaker)  |
| **Autor**         | [Piotr Esden-Tempski](https://github.com/esden)
| **Donde conseguirla** | [Crowdsupply](https://www.crowdsupply.com/1bitsquared/icebreaker-fpga)
| **Precio**        | $69  |
| **FPGA**          | [iCE40 UltraPlus 5K](http://www.latticesemi.com/-/media/LatticeSemi/Documents/DataSheets/iCE/iCE40-UltraPlus-Family-Data-Sheet.ashx) |
| **Frecuencia**    |  48 MHz     |
| **Periféricos**   | 2 LEDs, 1 pulsador |
| **Observaciones** | Hardware libre |

Placa con la FPGA [iCE40 UltraPlus 5K](http://www.latticesemi.com/-/media/LatticeSemi/Documents/DataSheets/iCE/iCE40-UltraPlus-Family-Data-Sheet.ashx), que incluye **DSP** y dos cores hardware de SPI e I2C. Está pensada con fines educativos. Dispoine de 4 PMODs para conectar fácilmente diferentes periféricos: switches, pulsadores, 7-segmentos, VGA...

### BlackIce II

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-31/BlackIce-II.jpg)

| Ficha             |            |
|-------------------|------------|
| **Nombre**        | [BlackIce-II](https://github.com/mystorm-org/BlackIce-II)  |
| **Autor**         | [Folknology](https://github.com/folknology) |
| **Donde conseguirla** | [Tindie](https://www.tindie.com/products/Folknology/blackice-ii/) | 
| **Precio**        | $55  |
| **FPGA**          | ICE40Hx4K |
| **Frecuencia**    |  100Mhz     |
| **Periféricos**   | Dip Switches, Pulsadores, 4 LEDs,  |
| **Observaciones** | Hardware libre |

### Upduino V2.0

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-31/Upduino-2.0.jpg)

| Ficha             |            |
|-------------------|------------|
| **Nombre**        | [UPDuino V2.0](https://github.com/gtjennings1/UPDuino_v2_0)  |
| **Autor**         | [gtjennings1](https://github.com/gtjennings1) |
| **Donde conseguirla** | [gnarlygrey.com](http://www.gnarlygrey.com/) | 
| **Precio**        | $14  |
| **FPGA**          | [iCE40 UltraPlus 5K](http://www.latticesemi.com/-/media/LatticeSemi/Documents/DataSheets/iCE/iCE40-UltraPlus-Family-Data-Sheet.ashx) |
| **Frecuencia**    |  12Mhz     |
| **Periféricos**   | 1 LED RBG  |
| **Observaciones** | Hardware libre |

### iCE40 UltraPlus Breakout Board

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-31/iCE40UltraPlusBreakoutTop.png)

| Ficha             |            |
|-------------------|------------|
| **Nombre**        | [iCE40 UltraPlus Breakout Board](https://www.latticesemi.com/Products/DevelopmentBoardsAndKits/iCE40UltraPlusBreakoutBoard)  |
| **Autor**         | [Lattice](https://www.latticesemi.com/Products/DevelopmentBoardsAndKits/iCE40UltraPlusBreakoutBoard) |
| **Donde conseguirla** | [Lattice](https://www.latticesemi.com/Products/DevelopmentBoardsAndKits/iCE40UltraPlusBreakoutBoard) | 
| **Precio**        | $49  |
| **FPGA**          | iCE40UP5K |
| **Frecuencia**    | 12 MHz  |
| **Periféricos**   | LED RGB, Dip Switches  |
| **Observaciones** | Placa de Lattice. No libre |

## Otras placas

Las siguientes son placas con FPGA de **gama media**, en las que se pueden sintetizar sistemas más complejos, como un procesador capaz de **correr Linux**, usando sólo herramientas libres

### TinyFPGA EX

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-31/tinyfpga-ex.jpg)

| Ficha             |            |
|-------------------|------------|
| **Nombre**        | [TinyFPGA-EX](https://github.com/tinyfpga/TinyFPGA-EX)  |
| **Autor**         | [Luke Valenty](https://github.com/tinyfpga) |
| **Donde conseguirla** | [Crowdsupply](https://www.crowdsupply.com/tinyfpga/tinyfpga-ex) | 
| **Precio**        | No disponible todavía |
| **FPGA**          | [ECP5 FPGA](https://www.latticesemi.com/view_document?document_id=50461) |
| **Frecuencia**    | 200Mhz  |
| **Periféricos**   | Tarjeta MicroSD  |
| **Observaciones** | Hardware libre |

Placa en diseño

### ULX3S

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-31/radiona_fpga_ULX3S.jpg)

| Ficha             |            |
|-------------------|------------|
| **Nombre**        | [ULX3S](https://github.com/emard/ulx3s)  |
| **Autor**         | [emard](https://github.com/emard) |
| **Donde conseguirla** | [radiona.org](http://radiona.org/new-fpga-board-ulx3s/) | 
| **Precio**        |  |
| **FPGA**          | [Lattice ECP5 LFE5U-85F-6BG381C (85K LUT)](http://www.latticesemi.com/~/media/LatticeSemi/Documents/DataSheets/ECP5/FPGA-DS-02012.pdf?document_id=50461) |
| **Frecuencia**    | 25 MHz |
| **Periféricos**   | Tarjeta microSD, 8 leds, 4 pulsadores, jack para audio, 8 canales ADC,   |
| **Observaciones** | Hardware Libre |

En el [proyecto Trellis](https://github.com/SymbiFlow/prjtrellis) se está haciendo ingeniería inversa de estas FPGAs para tener disponibles herramientas libres. En la placa ULX3S ya se [ha conseguido sinteizar un OpenRisc que corre Linux](https://twitter.com/fpga_dave/status/1053290842809683968)

## Nuevas herramientas

La comunidad ha estado **muy activa durante este año**, y el avance las herramientas es **imparable**. Cada vez se están documentando más FPGAs, mejorando las herramientas existentes y creando nuevas aplicaciones. El ecosistema de las **FPGAs libres** sigue creciendo

### Proyecto Icestorm

El [proyecto icestorm](http://www.clifford.at/icestorm/) ya tiene documentadas **30 FPGAs** de la familia Ice40 de Lattice, de gama baja. Las últimas han sido las UltraPlus (UP5K), que incluyen DSPs. Ya hay tres placas de esta familia soportadas en **Icestudio**

### SymbiFlow

El ecosistema de las **FPGAs libres** nació con el [proyecto icestorm](http://www.clifford.at/icestorm/) creado por **Clifford Wolf**, para las FPGAs de la familia **ICE40** de **Lattice**. Fue todo un logro. Durante el 2018 este ecosistema ha evolucionado al [proyecto Symbiflow](https://github.com/SymbiFlow): **Herramientas libres** para completar el ciclo de diseño desde el **Verilog** hasta la generación del **Bitstream** para **FPGAs de diferentes fabricantes**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-31/symbiflow-01.png)

Se ha creado una **arquitectura más general**, para integrar **FPGAs de diferentes fabricantes**. ¡¡Y esto es algo importantísimo!!. Los fabricantes, actualmente, tiene cada uno sus propias herramientas, que sólo valen para sus FPGAs. Esto dificulta enormemente el hacer diseños hardware **reutilizables** en FPGAs de otros fabricantes. Esto mismo ya ocurrió en el pasado con los **microprocesadores**: cada fabricante tenía **su propio compilador**. Hasta que llegó el **primer compilador libre**: el **GCC**, que permitía reutilizar el código en diferentes procesadores. Pues bien, gracias a Symbiflow, **¡tenemos el primer sintetizador libre multi-FPGA!**. Y esto va a cambiar el panorama de las FPGAs muchísimo, a largo plazo

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-31/symbiflow-02.png)

[Más información sobre Symbiflow](https://www.google.com/url?q=https://j.mp/orconf-symbiflow&sa=D&ust=1545158641352000&usg=AFQjCNF0RWbq1GORqXHBP2Hoj0AwyYXqkg), en las transparencias que se presentaron en el congreso ORCONF-2018

El proyecto tiene **2 partes fundamentales**: las **herramientas software** y la **documentación de las FPGAs**

### Herramientas software

* [Yosys](https://github.com/YosysHQ). Es el sintetizador. Pasa del verilog al netlist
* [Nextpnr](https://github.com/YosysHQ/nextpnr). Herramienta de rutado y emplazado
* [VTR](https://github.com/SymbiFlow/vtr-verilog-to-routing). otra herramienta de rutado y emplazado

### Documentación de las FPGAs

La parte más importante del proyecto es la **documentación** de las diferentes FPGAs. Esta información NO la proporciona el fabricante, por lo que se está obteniendo mediante ingeniería inversa, y es un proceso largo y tedioso, pero está dando sus frutos

| Nombre  | Descripción |
|---------|-------------|
| [Proyecto Icestorm](http://www.clifford.at/icestorm/) | Documentación de la **Familia ICE40 de Lattice** |
| [Proyecto Trellis](https://symbiflow.github.io/prjtrellis-db/) | Documentación de la **Familia ECP5 de Lattice** |
| [Proyecto X-ray](https://symbiflow.github.io/prjxray-db/) | Documentación de la **Serie-7 de Xilinx** |
| [Proyecto Chibi](https://github.com/rqou/project-chibi) | Documentación de las FPGA **MAX-V de Intel** |
| [Proyecto 2064](https://github.com/JohnDMcMaster/project2064)| Documentación de la familia **xc20xx de Xilinx** (Las primeras FPGAs que hubo) |

# Colección JEDI

La **temporada I** se termina, pero la acción continúa en la [Colección Jedi](https://github.com/FPGAwars/Collection-Jedi). Iré añadiendo nuevos bloques y ejemplos

* [Collection-jedi-1.0.zip](https://github.com/FPGAwars/Collection-Jedi/archive/v1.0.0.zip): Descargar e instalar
* [Colección Jedi: Repositorio](https://github.com/FPGAwars/Collection-Jedi)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-31/jedi-collection-01.png)

Esta colección se ha creado a partir de la **colección de la Academia Jedi** de tutorial anterior, y en ella se irán añadiendo nuevos bloques. Para este tutorial de despedida, he añadido una primera versión del **conversor Analógico-Digital (A/D)** que nos permite leer una **entrada analógica**. La explicación detallada la dejamos para la temporada II, pero aquí os muestro un par de ejemplos para que juguéis :-)

## Bloque para lecturas analógicas

Las placas **Icezum Alhambra** y **Alhambra II** incorporan el **conversor analógico-digital** [ADS7924](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-31/datasheet/ads7924.pdf) de texas instrument. Tiene **4 canales de 12 bits** 

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-31/ADC-02.png)

La lectura se hace a través del **bus I2C**, por los pines **ADC-SDA** (datos) y **ADC-SCL** (reloj) de la FPGA

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-31/ADC-03.png)

Un primer bloque para leer uno de los canales analógicos se encuentra en la **colección Jedi**, en el menú **Varios/ADC/adc**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-31/ADC-01.png)

Por los puertos **adc-sda** y **adc-scl** se conectan directamente los pines del mismo nombre en Icetudio. Si tenemos una tarjeta diferente, este bloque se puede usar también conectando en ese caso a los pines SDA y SCL del I2C donde está conectado el conversor

Por la entrada **ch[1:0]** indicamos el **canal a leer** (0-3) e introducimos un **tic por start** para que **comience** la conversión. La lectura digital es de **8 bits** (Se toman los 8 bits más significativos del valor interno de 12 bits), y se devuelve por el **bus de salida**. Se emite un **tic de dato listo** por **done**, para indicar que la **muestra** ya está **disponible**

## Ejemplo 1: Lectura de un potenciómetro

Vamos a conectar un **potenciómetro** lineal de **10K** al **canal 0** del conversor A/D y leeremos su **valor digital**, de 8 bits, que mostraremos en los **LEDs** de la Icezum Alhambra. El **escenario** es el siguiente:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-31/ADC-04.png)

En el circuito colocamos el **bloque conversor A/D**. Mediante una constante de 2 bits indicamos que queremos leer el **canal 0**, y colocamos un **corazón de tics de 20Hz** para realizar 20 lecturas por segundos. La salida la conectamos directamente a los **LEDs**. Este ejemplo se encuentra en la colección Jedi en el menú **Archivo/Ejemplos/ADC/01-Potentiometer-LEDs**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-31/ADC-05.png)

Lo **cargamos** y lo probamos. En los LEDs veremos el **valor digital de la tensión** proporcionada por el potenciómetro, en **binario**. En un extremo su valor será **0** (0v), y en el otro **255** (5v)

[![Click to see the youtube video](http://img.youtube.com/vi/0g8tuKTo0yA/0.jpg)](https://www.youtube.com/watch?v=0g8tuKTo0yA)

## Ejemplo 2: Envío de muestras al PC por el puerto serie

Usando el **mismo escenario** que en el ejemplo 1, añadimos el **bloque transmisor serie** para enviar las lecturas del potenciómetro al PC, por el **puerto serie**. Para que se realice la transmisión sólo hay que conectar la señal **done** del conversor a la **txmit** del bloque serie. La frecuencia de muestreo la cambiamos a 100, para que se envíen más datos por segundo. El **circuito** es el siguiente:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-31/ADC-06.png)

Lo **cargamos** y lo **probamos**. En el PC ejecutamos el **ScriptCommuniator** y mostramos la pestaña con los datos en **decimal**. Veremos cómo en un extremo se recibe el **000** y en el otro el **255**

[![Click to see the youtube video](http://img.youtube.com/vi/bJaM6gJl_Vg/0.jpg)](https://www.youtube.com/watch?v=bJaM6gJl_Vg)

## Ejemplo 3: Movimiento de un servo con el potenciómetro

Como último ejemplo de la temporada I de tutoriales, vamos a mover un **servo a cualquier posición**, usando el **potenciómetro**. El escenario es el mismo de antes pero añadiendo un servo Futaba 3003

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-31/ADC-07.png)

En el circuito colocamos el **controlador de servos** igual que el transmisor serie del ejemplo 2: por su entrada **write** conectamos la salida **done**, para que mueva el servo a la posición recibida del conversor

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-31/ADC-08.png)

Lo **cargamos** y lo **probamos**. Ahora podemos llevar el servo a cualquier posición fácilmente moviendo el potenciómetro. ¡Es muy adictivo! :-)

[![Click to see the youtube video](http://img.youtube.com/vi/vg7P8ZVle3Q/0.jpg)](https://www.youtube.com/watch?v=vg7P8ZVle3Q)

# Rango de Caballero Jedi

Si has participado en la **Academia Jedi**, el curso estará oficialmente terminado cuando alcances el **rango de Caballero Jedi**. Para ello necesitarás tener al menos... **¡600 Bitpoints!**. Los bitpoints que te faltan los podrás conseguir haciendo **tus propios proyectos** que podrás entregar en la [carpeta del tutorial 31](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/tree/master/Tutorial-31) en el github de las entregas. Es obligatorio que la entrega sea por **github**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-31/22-Caballero-Jedi.png)

Una vez que consigas los **600 Bitpoints**, se emitirá un **Certificado Jedi** que acredite tus logros

# Los 3 primeros Certificados emitidos

Los **tres primeros** estudiantes de la Academia Jedi en alcanzar el rango máximo de **Caballero Jedi** son:

## Ximo Catala 

* **Usuario Github**: [ximocat](https://github.com/ximocat)

* **Bitpoints totales**: 600 (+465)

* **Certificado**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/certificados/000-certificado-Ximo-Catala.png)

## Josep Montoliu 

* **Usuario Github**: [klarojms](https://github.com/klarojms)

* **Bitpoints totales**: 600 (+20)

* **Certificado**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/certificados/001-certificado-Josep-Montoliu.png)

## Federico Coca

* **Usuario Github**: [fgcoca](https://github.com/fgcoca)

* **Bitpoints totales**: 600 (+5)

* **Certificado**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/certificados/002-certificado-Federico-Coca.png)

# Soluciones a los ejercicios del tutorial 30: Puerto Serie

Las soluciones a los ejercicios planteados en el [tutorial 30: Puerto serie]((TODO)) se muestran a continuación:

## Ejercicio 30.1: Transmisión de dos cadenas

* [Sol-Tut30-1.ice](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-31/Soluciones-30/Sol-Tut30-1.ice)
* [msg0.list](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-31/Soluciones-30/msg0.list)
* [msg1.list](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-31/Soluciones-30/msg1.list)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-31/Soluciones-30-1.png)

## Ejercicio 30.2: Contador de pasadas del spiner

* [Sol-Tut30-2.ice](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-31/Soluciones-30/Sol-Tut30-2.ice)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-31/Soluciones-30-2.png)

## Ejercicio 30.3: Control de Franky por puerto serie

* [Sol-Tut30-3.ice](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-31/Soluciones-30/Sol-Tut30-3.ice)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-31/Soluciones-30-3.png)

# Estadísticas del tutorial

* **Primer vídeo**: 13-Octubre-2017
* **Último vídeo**: 21-Dic-2018
* **Tiempo desarrollo Total**: 1 año y 2 meses
* **Ejemplos de circuitos**: 220.  Todos sintetizados y comprobados en hardware real
* **Ejercicios propuestos:** 90. Con sus soluciones
* **Imágenes:** 1357. Entre figuras, pantallazos y animaciones. Con sus ficheros fuentes en SVG en el propio repositorio del tutorial
* **Tutoriales:**: 31, con vídeos e información en wiki
* **Vídeos**:
  * 48 con explicaciones
  * 159 de apoyo (sin voz): ejemplos, ejercicios propuestos, aclaraciones...
* **Número de ediciones de la wiki**: 7340 
* **Commits de desarrollo**: 1563
* **Número de entregas de ejercicios recibidas**: 1160
* **Numero total de apuntados**: 193
  * **Curso Completado**: 3
    * **Caballeros Jedi**: 3
  * **Tercer curso**: 8
    * **Jedis Nivel 3**: 2
    * **Jedis Nivel 2**: 0
    * **Jedis Nivel 1**: 6
    * **Jedis**: 0
  * **Segundo curso**: 18
    * **Aspirantes a Jedi Nivel 3**: 1
    * **Aspirantes a Jedi Nivel 2**: 1
    * **Aspirantes a Jedi Nivel 1**: 1
    * **Aspirantes a Jedi**: 2
    * **Padawans Nivel 3**: 3
    * **Padawans Nivel 2**: 1
    * **Padawans Nivel 1**: 2
    * **Padawans**: 7
  * **Primer curso**: 123
    * **Aspirantes a Padawans Nivel 3**: 12
    * **Aspirantes a Padawans Nivel 2**: 2
    * **Aspirantes a Padawans Nivel 1**: 16
    * **Aspirantes a Padawans**: 9
    * **Cadetes Nivel 3**: 23
    * **Cadetes Nivel 2**: 20
    * **Cadetes Nivel 1**: 13
    * **Cadetes**: 28
  * **Pre-academia**: 41
    * **Aspirantes a Cadete**: 39
    * **Observadores**: 2

# Autor

* [Juan González-Gómez](https://github.com/Obijuan) (Obijuan)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/logos-urjc-gsyc-peloto-jderobot.png)

# Licencia

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/attribution-share-alike-creative-commons-license.png)

# Créditos y agradecimientos

* [Imagen del sable láser](https://commons.wikimedia.org/w/index.php?curid=3846827). De Tim Kloske (talk) - Trabajo propio, Dominio público, 
* [Señal analógica](https://commons.wikimedia.org/w/index.php?curid=9378313), By Fleshgrinder - Own work, Public Domain

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




