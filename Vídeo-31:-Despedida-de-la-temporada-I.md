![]()

# Vídeo

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

Haz click en la imagen para ver el **vídeo en Youtube**

# Descripción

TODO

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

* Collection-jedi-1.0.zip: Descargar e instalar
* [Colección Jedi: Repositorio](https://github.com/FPGAwars/Collection-Jedi)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-31/jedi-collection-01.png)

Esta colección se ha creado a partir de la **colección de la Academia Jedi** de tutorial anterior, y en ella se irán añadiendo nuevos bloques. Para este tutorial de despedida, he añadido una primera versión del **conversor Analógico-Digital (A/D)** que nos permite leer una **entrada analógica**. La explicación detallada la dejamos para la temporada II, pero aquí os muestro un par de ejemplos para que juguéis :-)

## Bloque para lecturas analógicas

Las placas **Icezum Alhambra** y **Alhambra II** incorporan el **conversor analógico-digital** [ADS7924](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-31/datasheet/ads7924.pdf) de texas instrument. Tiene **4 canales de 12 bits**, y la lectura se hace a través del **bus I2C**, por los pines ADC-SDA (datos) y ADC-SCL (reloj).

(Dibujo)

Un primer bloque para leer uno de los canales analógicos se encuentra en la **colección Jedi**, en el menú **Varios/ADC/adc**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-31/ADC-01.png)

Por los puertos **adc-sda** y **adc-scl** se conectan directamente los pines del mismo nombre en Icetudio. Si tenemos una tarjeta diferente, este bloque se puede usar también conectando en ese caso a los pines SDA y SCL del I2C donde está conectado el conversor

Por la entrada **ch[1:0]** indicamos el **canal a leer** (0-3) e introducimos un **tic por start** para que **comience** la conversión. La lectura digital es de **8 bits** (Se toman los 8 bits más significativos del valor interno de 12 bits), y se devuelve por el **bus de salida**. Se emite un **tic de dato listo** por **done**, para indicar que la **muestra** ya está **disponible**

## Ejemplo 1: Lectura de un potenciómetro

(Explicación)  
(Escenario)  
(Circuito)  
(Vídeo)  

## Ejemplo 2: Envío de muestras al PC por el puerto serie

(Explicación)  
(Escenario)  
(Circuito)  
(Vídeo)  

## Ejemplo 3: Movimiento de un servo con el potenciómetro

(Explicación)  
(Escenario)  
(Circuito)  
(Vídeo)  

(TODO)

# Rango de Caballero Jedi

(TODO)

# Certificados emitidos

(TODO)



# Estadísticas del tutorial

* Primer vídeo: 13-Octubre-2017
* Último vídeo: 21-Dic-2018
* Total: 1 año y 2 meses

# Soluciones a los ejercicios del tutorial 30

(TODO)



(TODO)

# Autor

* [Juan González-Gómez](https://github.com/Obijuan) (Obijuan)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/logos-urjc-gsyc-peloto-jderobot.png)

# Licencia

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/attribution-share-alike-creative-commons-license.png)

# Créditos y agradecimientos

* [Imagen del sable láser](https://commons.wikimedia.org/w/index.php?curid=3846827). De Tim Kloske (talk) - Trabajo propio, Dominio público, 
* [Señal analógica](https://commons.wikimedia.org/w/index.php?curid=9378313), By Fleshgrinder - Own work, Public Domain

# Enlaces

