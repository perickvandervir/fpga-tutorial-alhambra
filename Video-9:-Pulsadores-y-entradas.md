![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-09/portada/Tut-9-portada.png)

# Vídeo

[![Click to see the youtube video](http://img.youtube.com/vi/7LOdYJt077M/0.jpg)](https://www.youtube.com/watch?v=7LOdYJt077M&list=PLmnz0JqIMEzXaeYVzf2TfTzRekPIVoljw&index=9)

Haz click en la imagen para ver el **vídeo en Youtube**

# Descripción
Los bits se introducen en los circuitos digitales a través de sus **entradas**. Veremos cómo meter bits mediante los **pulsadores internos** de la Icezum Alhmabra, y haremos circuitos sencillos con entradas y salidas

# Colección

[Academia-Jedi-HW-09.zip](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-09/Collection/Academia-Jedi-HW-09.zip): Colección para este tutorial. Descargar e instalar 

# Contenido

* [Entradas digitales](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-9:-Pulsadores-y-entradas#entradas-digitales)
* [Pulsadores internos en la Icezum Alhambra](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-9:-Pulsadores-y-entradas#pulsadores-internos-en-la-icezum-alhambra)
* [Ejemplo 1: Encendiendo un LED con el pulsador](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-9:-Pulsadores-y-entradas#ejemplo-1-encendiendo-un-led-con-el-pulsador)
* [Ejemplo 2: apagando un LED con el pulsador](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-9:-Pulsadores-y-entradas#ejemplo-2-apagar-el-led-con-el-pulsador)
* [Ejemplo 3: LEDs alternantes con pulsador](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-9:-Pulsadores-y-entradas#ejemplo-3-leds-alternantes-con-pulsador)
* [Ejemplo 4: Superposición de los ejemplos 1 y 2](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-9:-Pulsadores-y-entradas#ejemplo-4-superposici%C3%B3n-de-los-ejemplos-1-y-2)
* [¡No me funcionan los pulsadores!](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-9:-Pulsadores-y-entradas#no-me-funcionan-los-pulsadores)
* [Ejercicios propuestos (12 Bitpoints + 2)](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-9:-Pulsadores-y-entradas#ejercicios-propuestos-12-bitpoints--2)
  * [Bonus Star Wars](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-9:-Pulsadores-y-entradas#bonus-star-wars-episodio-viii)
* [Ejercicios entregados](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-9:-Pulsadores-y-entradas#ejercicios-entregados)
  * [Carlos Obregón (Carlobre)](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-9:-Pulsadores-y-entradas#carlos-obreg%C3%B3n-carlobre)
  * [JuanDGomezM](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-9:-Pulsadores-y-entradas#juandgomezm)
  * [Josep Montoliu (Klarojms)](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-9:-Pulsadores-y-entradas#josep-montoliu-klarojms)
* [Licencia](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-9:-Pulsadores-y-entradas#autor)
* [Enlaces](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-9:-Pulsadores-y-entradas#enlaces)
* [FAQs](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-9:-Pulsadores-y-entradas#faqs)

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

Si miramos en la documentación también podemos ver que están conectados a los **pines físicos** **10** y **11** de la FPGA. De esta forma, nos inyectan los bits dentro de la FPGA, que leeremos desde nuestros circuitos hechos con Icestudio. En su estado normal, **leeremos 0** por las entradas SW1 y SW2. Al apretarlos, se pondrán a **1**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-09/Alhambra-03.png)

# Ejemplo 1: Encendiendo un LED con el pulsador

Haremos un circuito que **enciendo** el **LED 0** cuando se **aprieta** el **pulsador SW1**. Abrimos Icestudio y nos vamos al menú **Básico/Entrada** para colocar un bloque de entrada

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-09/Ejemplo-1-01.png)

Se nos abre una ventana para darle un **nombre al bloque**. Le ponemos, por ejemplo, **Pulsador** y le damos al **OK**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-09/Ejemplo-1-02.png)

Nos aparece el **bloque** y lo **colocamos**. Hacemos click en el **botón izquierdo** del ratón para ponerlo

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-09/Ejemplo-1-03.png)

Pinchamos en el **desplegable del bloque** para seleccionar el pin **SW1**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-09/Ejemplo-1-04.png)

Ya tenemos listo nuestro **bloque de entrada**. Por ahí es por donde recibiremos los bits procedentes del **pulsador SW1**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-09/Ejemplo-1-05.png)

Ahora colocamos el **bloque de salida**, como ya sabemos. Le ponemos como **nombre LED** y lo asociamos al **LED 0**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-09/Ejemplo-1-06.png)

y por último tiramos **un cable** desde la **entrada** hasta la **salida**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-09/Ejemplo-1-07.png)

¡Ya tenemos listo el circuito! Ahora lo **cargamos** en la placa y lo probamos

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-09/Ejemplo-1-anim.gif)

El **LED0** inicialmente está apagado. Al dejar **apretado** el pulsador **SW1**, se enciende. Y al volver a soltarlo se apaga

El **circuito que se ha creado** se muestra en este dibujo. Físicamente, el pulsador **SW1** está unido al **pin 10** de la FPGA. Nuestro circuito une internamente este pin de **entrada** con el de **salida**, que físiciamente llega hasta este **LED0**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-09/Ejemplo-1-08.png)

Y esta es una **animación** de lo que está pasando internamente :-)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-09/Ejemplo-1-anim-2.gif)

# Ejemplo 2: Apagar el LED con el pulsador

Haremos el ejemplo contrario. El **LED 7** está encendido hasta que se aprieta el **pulsador SW2**, que se apaga. Al soltarse se vuelve a encender

En este caso, hay que colocar una **puerta NOT**. El circuito es:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-09/Ejemplos-2-01.png)

Lo **cargamos** en la placa y probamos su funcionamiento

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-09/Ejemplo-2-anim.gif)

Al cargar el circuito, el **LED7 se encenderá**. Cuando pulsamos **SW2**, se apaga. Al liberarlo, se vuelve a  encender. Justo el comportamiento contrario que el ejemplo anterior

Esto es lo que ocurre en su **interior**. Cuando el **pulsador no está apretado**, entra un **0** por la entrada, que se convierte en un **1** al pasar por la **puerta NOT** y enciende el LED

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-09/Ejemplos-2-02.png)

El proceso completo se muestra en esta **animación**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-09/Ejemplo-2-anim-2.gif)

# Ejemplo 3: LEDs alternantes con pulsador

Haremos un circuito que haga **parpadear** los LEDS **7** y **0** alternativamente al **apretar el pulsador SW1**. Cuando no está apretado, el LED7 está encendido, y el LED 0 apagado. Al apretar el pulsador se apaga el 7 y se enciende el 0

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-09/Ejemplo-3-01.png)

Lo **cargamos** en la placa para ver su funcionamiento. Se muestra en esta **animación**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-09/Ejemplo-3-anim.gif)

Este es un ejemplo de un circuito que tiene **1 entrada** y **2 salidas**

# Ejemplo 4: Superposición de los ejemplos 1 y 2

Los ejemplos 1 y 2 son dos **circuitos independientes**, que tiene cada uno **una entrada** y **una salida**. Aplicando el **principio de superposición**, podemos colocar los dos **circuitos en paralelo** para que funcionen a la vez, obteniendo un **circuito de 2 entradas con 2 salidas**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-09/Ejemplo-4-01.png)

**Inicialmente** el **LED7** está **encendido** y el resto **apagados**. Al apretar el **puslador SW1**, se enciende el **LED0**. Ambos LEDs, 7 y 0, estarán encendidos.  Si apretamos sólo el **pulsador SW2**, el LED7 se apgarán, por lo que todos los LEDs estarán apagados. Finalmente, si apretados los **dos pulsadores a la vez**, sólo se encenderá el LED0.  El funcionamiento se muestra en esta **animación**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-09/Ejemplo-4-anim.gif)

En total hay **4 casos**: cuando los pulsadores NO están apretados (00), cuando el SW1 está apretado y el SW2 no (10), cuando el SW2 sí pero el SW1 no (01) y cuando ambos están apretados (11). Para cada uno de estos posibles estados hay una salida diferente en los LEDs 7 y 0.

# ¡No me funcionan los pulsadores!

Si has probado los ejemplos y has detectado que algún pulsador **no te funciona bien**, puede ser porque se ha quedado **un poco de flux en su interior**, y no hace buen contacto. Algunos usuarios han reportado este problema, con las Icezum Alhambras de las **tiradas 1 y 2**. La **solución** es muy sencilla: usando un **cuentagotas** o una pajita, echar una **gotas de alchol de 96 grados** sobre los pulsadores, mientras la **placa está encendida** (el alcohol no conduce, no hay problema). 

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-09/arreglando-pulsadores-1.jpg)

**Apretar los pulsadores repetidamente** hasta que se disuelva el flux y funcionen correctamente. En menos de un minuto ya estarán operativos

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-09/arreglando-pulsadores-2.jpg)

# Ejercicios propuestos (12 BitPoints + 2)

Ver los detalles de los ejercicios y las **entregas** en el menú **Archivos/Ejemplos/2-Ejercicios** de la colección de este tutorial

**Resumen**:

* **Ejercicio 1** (Total **3 Bitpoints**): Hacer un circuito digital que encienda los 
LEDs 0,1,2 y 3 al apretar el pulsador SW1, y deje apagados el resto. Al soltarlo, se 
deben encender los LEDS 4,5,6 y 7, y apagar los anteriores

* **Ejercicio 2** (Total **3 Bitpoints**): Hacer un circuito digital con dos pulsadores de entrada.
Al apretar SW1 se enciende el LED5 y se apaga el LED7, y al soltarlo se enciende LED7 y se 
apaga el LED5. Al apretar SW2 se enciende LED2 y se apaga LED0, y al soltarlo se enciende 
LED0 y se apaga LED2

* **Ejercicio 3** (Total **3 Bitpoints**): Hacer un circuito digital para que se enciendan los
dos ojos de FRANKY al apretar un pulsador, y que se apaguen al soltarlo

* **Ejercicio 4** (**3 Bitpoints**). Ejercicio Libre. Premiar la creatividad. **Entregar** por redes sociales o github: Pantallazos, enlaces, vídeos, etc...

## Bonus Star Wars Episodio VIII

Para celebrar el estreno del **episodio VIII** de **Star Wars**, todas las entregas de los ejercicios del tutorial 9 recibidas hasta el **Viernes 22/Dic/2017** (incluido) tendrán **2 Bitpoints Extras**

# Ejercicios entregados

## Carlos Obregón (Carlobre)

### Ejercicio 1

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-9/Carlobre/Tutorial%209.1.png)

* [VIDEO](https://www.youtube.com/watch?v=cMqs-IE9SuY)

### Ejercicio 2

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-9/Carlobre/Tutorial%209.2.png)

* [VIDEO](https://www.youtube.com/watch?v=r-jlhWob6JA)

### Ejercicio 3

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-9/Carlobre/Tutorial%209.3.png)

* [VIDEO](https://www.youtube.com/watch?v=-FyJm5TRQCM)

### Ejercicio 4

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-9/Carlobre/Tutorial%209.4.png)

* [VIDEO](https://www.youtube.com/watch?v=zOvTJ0xJRUY)

## JuanDGomezM

### Ejercicio 1

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-9/JuanDGomezM/Ejerc.9.1.png)

* [VIDEO](https://plus.google.com/u/0/photos/117217596152589136489/album/6500242594000616081/6500242596698192306?authkey=CPC0-_PA37H3aQ)

### Ejercicio 2

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-9/JuanDGomezM/Ejerc.9.2.png)

* [VIDEO](https://plus.google.com/u/0/photos/117217596152589136489/album/6500242594000616081/6500242597635124242?authkey=CPC0-_PA37H3aQ)

### Ejercicio 3

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-9/JuanDGomezM/Ejerc.9.3.png)

* [VIDEO](https://plus.google.com/u/0/photos/117217596152589136489/album/6500242594000616081/6500242597713648834?authkey=CPC0-_PA37H3aQ)

## Josep Montoliu (Klarojms)

### Ejercicio 1

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-9/klarojms/Ejercicio%201-1.png)

* [VIDEO](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-9/klarojms/Ejercicio%201-1.mp4)

### Ejercicio 2

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-9/klarojms/Ejercicio%202-1.png)

* [VIDEO](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-9/klarojms/Ejercicio%202-2.mp4)

### Ejercicio 3

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-9/klarojms/Ejercicio%203-1.png)

* [VIDEO](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-9/klarojms/Ejercicio%203-1.mp4)

### Ejercicio 4

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-9/klarojms/Ejercicio%204-1.png)

* [VIDEO](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-9/klarojms/Ejercicio%204-2.mp4)

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

# FAQs

* **He probado los ejemplos, pero los pulsadores no me funcionan**

Eso es debido a que se han metido restos de flux y no hacen buen contacto. En el apartado [¡No me funcionan los pulsadores!](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-9:-Pulsadores-y-entradas#no-me-funcionan-los-pulsadores) se indica cómo solucionarlo fácilmente

* **¿Dónde puedo conseguir la placa Icezum Alhambra?**

Pueden conseguir una desde [Alhambrabits](https://alhambrabits.com/buy/)

* **¿Cómo aprendo a manejar github?**

Hay mucha información en internet. En su momento hice este Tutorial: [Github y FreeCAD](http://www.iearobotics.com/wiki/index.php?title=Tutorial:_Github_y_Freecad) para enseñar a manejarlo. Los ejemplos están hechos con ficheros de FreeCAD, sin embargo, lo que se enseña es genérico. También vale para las entregas de los ejercicios del tutorial de Electrónica digital para makers

* **¿Dónde puedo comprar material electrónico?**. Hay muchos sitios. Uno muy bueno es [Bricogeek](http://tienda.bricogeek.com/)




