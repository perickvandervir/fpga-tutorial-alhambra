![]()

# Vídeo

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

Haz click en la imagen para ver el **vídeo en Youtube**

# Descripción


# Colección

**Academia-Jedi-HW-09.zip**: Colección para este tutorial. Descargar e instalar 

# Contenido

* [Entradas digitales](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-9:-Pulsadores-y-entradas#entradas-digitales)

# Entradas digitales

Los **circuitos digitales**, que están dentro de los chips, reciben **bits** por sus **entradas**, los manipulan, transportan o almacenan, y prodcuen bits de **salida**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-09/Entradas-01.png)

En los ejemplos que hemos visto hasta ahora, sólo se sacaban bits por las Salidas para encender LEDs. Ahora veremos **cómo introducir BITs en nuestros circuitos**, por sus **entradas digitales**

El elemento más sencillo para **introducir** un BIT es el **pulsador**. Cuando está **apretado**, su valor es **1**, y cuando está **liberado**, es **0**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-09/Entradas-02.png)

Al **apretar** el pulsador se **inyecta** un Bit 1 en nuestro circuito digital, por la entrada

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-09/Entradas-03.png)

Al **apretar** y **soltar repetidamente**, conseguimos inyectar Bits a 0 y 1

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-09/Button-on-off-anim.gif)

# Pulsadores internos en la Icezum Alhambra

La placa [Icezum Alhambra](https://github.com/FPGAwars/icezum/wiki) incorpora dos **pulsadores genéricos**, para hacer pruebas. Están situados en la parte superior izquierda de la placa, muy cerca de los LEDs

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-09/Alhambra-01.png)

Estos pulsadores se denotan como **SW1** y **SW2** en Icestudio. 

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-09/Alhambra-02.png)

Si miramos en la documentación también podemos ver que están conectados a los pines físicos **10** y **11** de la FPGA. De esta forma, nos inyectan los bits dentro de la FPGA, que leeremos desde nuestros circuitos hechos con Icestudio

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-09/Alhambra-02.png)


-Dibujo: Pistas de los pulsadores a la FPGA

# Ejemplo 1: Encender el LED con el pulsador

-Entrada - transporte - salida
-Dibujo FPGA con el circuito físico dentro

# Ejemplo 2: Apagar el LED con el pulsador

-Entrada - manipulación - transporte - salida
- Dibujo FPGA con circuito dentro

# Ejemplo 3: Encender y apagar LEDs con los pulsadores

Superposición de los circuitos anteriores

# Ejercicios propuestos (XX BitPoints)

Ver los detalles de los ejercicios y las **entregas** en el menú **Archivos/Ejemplos/2-Ejercicios** de la colección de este tutorial

**Resumen**:

* **Ejercicio 1** (Total **x Bitpoints**): 

* **Ejercicio 2** (Total **x Bitpoints**): 

* **Ejercicio 3** (Total **8 Bitpoints**):

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
* [Fritzing](http://fritzing.org)
* [Icezum Alhambra en Fritzing](https://github.com/lobotic/IceZUM_Alhambra_Fritzing)
* [Repositorio de PCBprints](https://github.com/PCBPrints/PCbPrints)
* [PCBprint "Hola Mundo"](https://github.com/Obijuan/3D-parts/wiki/PCB-Led-hola-mundo)
* [Placa FreeLEDs](http://www.iearobotics.com/wiki/index.php?title=Freeleds)
* [Monedas Bit imprimibles](https://github.com/Obijuan/3D-parts/wiki/Monedas-Bit)

# FAQs

* **¿Dónde puedo conseguir la placa Icezum Alhambra?**

Pueden conseguir una desde [Alhambrabits](https://alhambrabits.com/buy/)

* **¿Cómo aprendo a manejar github?**

Hay mucha información en internet. En su momento hice este Tutorial: [Github y FreeCAD](http://www.iearobotics.com/wiki/index.php?title=Tutorial:_Github_y_Freecad) para enseñar a manejarlo. Los ejemplos están hechos con ficheros de FreeCAD, sin embargo, lo que se enseña es genérico. También vale para las entregas de los ejercicios del tutorial de Electrónica digital para makers

* **¿Dónde puedo comprar material electrónico?**. Hay muchos sitios. Uno muy bueno es [Bricogeek](http://tienda.bricogeek.com/)




