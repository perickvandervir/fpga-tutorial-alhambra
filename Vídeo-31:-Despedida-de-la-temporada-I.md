![]()

# Vídeo

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

Haz click en la imagen para ver el **vídeo en Youtube**

# Descripción

TODO

# Contenido

* [Evolución de las FPGAs libres](#evoluci%C3%B3n-de-las-fpgas-libres)
  * [Placas incorporadas en Icestudio](#placas)
    * [Alhambra II](#alhambra-ii)
    * [TinyFPGA-BX](#tinyfpga-bx)
    * [Icebreaker](#icebreaker)
    * [BlackIce-II](#blackice-ii)
    * [Upduino v2.0](#upduino-v20)
    * [Ice40 UltraPlus Breackout Board](#ice40-ultraplus-breakout-board)
  * [Otras Placas]


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




## Otras

ECP5

## Nuevas herramientas

(TODO)

* Comunidad

# Rango de Caballero Jedi

(TODO)

# Certificados emitidos

(TODO)

# Colección JEDI

* Bloque conversor A/D

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

# Enlaces

