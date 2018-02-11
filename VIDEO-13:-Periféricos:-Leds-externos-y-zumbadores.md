(EN CONSTRUCCIÓN)

![]()

# Vídeo

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

Haz click en la imagen para ver el **vídeo en Youtube**

# Descripción

# ¡Icestudio 0.3.2!

Con motivo de nuestra asistencia a la [FOSDEM 2018](https://fosdem.org/2018/), hemos liberado una nueva versión de **Icestudio: 0.3.2**. Por favor, **actualizarse** a esa versión. La colección empleada en este tutorial está hecha con esta versión, y en las anteriores no se verá correctamente

# Colección

**Academia-Jedi-HW-13.zip**: Colección para este tutorial. Descargar e instalar 

# Contenido

* [Introducción](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/VIDEO-13:-Perif%C3%A9ricos:-Leds-externos-y-zumbadores#introducci%C3%B3n)
* [LEDs externos](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/VIDEO-13:-Perif%C3%A9ricos:-Leds-externos-y-zumbadores#leds-externos)
  * [Conexión directa](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/VIDEO-13:-Perif%C3%A9ricos:-Leds-externos-y-zumbadores#conexi%C3%B3n-directa)
  * [Conexión a través de un transistor](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/VIDEO-13:-Perif%C3%A9ricos:-Leds-externos-y-zumbadores#conexi%C3%B3n-a-trav%C3%A9s-de-un-transistor)
    * [PCBPrint: Alhambra-LED](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/VIDEO-13:-Perif%C3%A9ricos:-Leds-externos-y-zumbadores#pcbprint-alhambra-led)
* [Ejemplo 1: Sirena Luminosa con 2 LEDs](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/VIDEO-13:-Perif%C3%A9ricos:-Leds-externos-y-zumbadores#ejemplo-1-sirena-luminosa-con-2-leds)
* [Zumbador pasivo](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/VIDEO-13:-Perif%C3%A9ricos:-Leds-externos-y-zumbadores#zumbador-pasivo)
  * [Conexión en protoboard](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/VIDEO-13:-Perif%C3%A9ricos:-Leds-externos-y-zumbadores#conexi%C3%B3n-en-protoboard)
  * [Conexión de placa comercial con zumbador](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/VIDEO-13:-Perif%C3%A9ricos:-Leds-externos-y-zumbadores#conexi%C3%B3n-de-placa-comercial-con-zumbador)
* [Ejemplo 2: Generando un tono de 1Khz](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/VIDEO-13:-Perif%C3%A9ricos:-Leds-externos-y-zumbadores#ejemplo-2-generando-sonido-tono-de-1khz)


# Introducción

Hay muchos **periféricos**, tanto de entrada como de salida, que todavía no hemos visto, y que nos permitirán hacer muchísimas cosaas, sobre todo relacionadas con la **robótica**. Muchos los iremos viendo en estos tutoriales y en las siguientes temporadas de tutoriales. También es posible conectar periféricos analógicos, como **potenciómetros** o **sensores de luz**, cuya señal se digitaliza (se convierte en números) usando un conversor **analógico-digital**. En la Placa **Icezum Alhambra** hay un **conversor A/D** de 4 canales

En esta imagen se **listan** los periféricos. De todos ellos ya hemos visto 3: los **pulsadores**, los **interruptres** y los **servos**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-13/Introduccion-01.png)

En este capítulo nos centraremos en los **LEDs externos** y en los **zumbadores**

# LEDs externos

En el [tutorial 8](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos) ya vimos cómo conectar **LEDs externos** a los **pines de 3.3v** de la [icezum Alhambra](https://github.com/FPGAwars/icezum/wiki). En este veremos cómo hacerlo a los **pines de 5v**, para conectar directamente los LEDs como **periféricos de salida**

Hay dos formas de conexión: **Directa** y a través de **transistor**

## Conexión directa

El **esquema** para conectar un LED directamente a los **pines de 5v** es el siguiente:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-13/Leds-externos-01.png)

Los **pines de 5v** están conectados a los de la FPGA a través de unos **conversores de nivel** (3.3v <--> 5v). El valor de la **resistencia R** que usamos, determina la **configuración** del conversor: entrada o salida. Para conectar un LED el pin debe ser de **salida** y para ello hay que colocar una resistencia **mayor o igual a 2K2**.

El inconveniente de esto es que el **LED se iluminará poco** porque la resistencia es grande y deja pasar **poca corriente**. Para que el LED luzca con **más intensidad** hay dos opciones: utilizar un **LED de alta luminosidad** o bien realizar la conexión a través de un **transistor**

## Conexión a través de un transistor

El **esquema** de conexión es el siguiente

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-13/Leds-externos-02.png)

Al enviarse un 1 por el pin de la FPGA, se **activa el transitor**, que funciona como un interruptor, conectando  la resistencia a GND y cerrando el circuito. Ahora por el LED circuilará la **suficiente corriente** para hacer que luzca normalmente

Este es un **esquema** de montaje en Fritzzing. Se ha usado el **transistor** NPN **BC547B**, con encapsulado **TO-92**, **R1** es de **10K** y **R2** de **220 ohms**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-13/Leds-externos-03.png)

y este es el **montaje real**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-13/Leds-externos-04.jpg)

**NOTA**: El patillaje de los transitores cambia según el modelo usado, en este ejemplo estoy usando el transistor **BC547B** que tiene la **base** en la **pata central**, sin embargo hay otros que la tienen en un lateral

### PCBPrint: Alhambra-LED

Una opción muy cómoda es usar un **PCBprint** con **LED**. Esta es la [Alhambra LED](https://github.com/FPGAwars/alhambra-led/wiki)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-13/alhambra-led-1.png)

Se conecta directamente a los **conectores de 5v** a través de un cable de tres hilos, y las podemos usar en nuestros **paneles**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-13/Alhambra-led-2.jpg)

**NOTA**: El patillaje de los transitores cambia según el modelo. En la Alhambra-LED se usa el **BC635**, que tiene la **base** en una de las **patas laterales**

# Ejemplo 1: Sirena luminosa con 2 LEDs

Como ejemplo vamos a conectar **dos LEDs externos** a los pines de 5v **D13** y **D12**, y los haremos **parpadear alternativamente**, igual que hicimos en el [tutorial 8](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-8:-Pines-y-LEDs-externos) con los leds conectados a los pines de 3.3v

Primero construimos nuestro **panel** con los dos LEDS

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-13/Alhambra-led-03.jpg)

El circuito ya lo conocemos. Esta vez hemos añadido un título usando el nuevo renderizado del **Mark down** que incorpora **Icestudio 0.3.2**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-13/Alhambra-led-04.png)

**Cargamos** el circuito en la placa para probarlo

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-13/Alhambra-led-05.gif)

Para **cambiar la frecuencia de parpadeo** sólo hay que cambiar el corazón por otro de diferente frecuencia. Antes teníamos que borrar el cable (o el corazón), colocar el nuevo y volver a tirar el cable. En **Icestudio 0.3.2** se pueden **remplazar bloques** simplemente colocándolos encima

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-13/Alhambra-led-06.gif)

Y ahora es mucho más fácil añadir **documentación** en los **bloques de información** usando como notación el [markdown](https://guides.github.com/features/mastering-markdown/) de github

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-13/Alhambra-led-07.gif)

Para cambiar al **modo edición** sólo hay que hacer **doble click** en el bloque. Y lo mismo para volver al **modo normal**. Se pueden poner **emoticonos** también :smile:

# Zumbador pasivo

Utilizaremos un **zumbador pasivo** o **altavoz** para escuchar sonidos generados desde nuestros circuitos. Es necesario conectar un **transistor** al zumbador para que circule **más corriente** y se active, escuchándose el sonido. El **esquema de conexión** es el siguiente:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-13/zumbador-01.png)

## Conexión en protoboard

La **construcción** del circuito en una **placa de entrenamiento** se muestra en este esquema de Fritzzing:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-13/zumbador-02.png)

y este es el **montaje real**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-13/zumbador-03.jpg)

## Conexión de placa comercial con zumbador

Existen placas comercionales con el **zumbador**, que son muy cómodas porque se **conectan directamente** a la Icezum Alhambra a través de un **cable de 3 hilos**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-13/zumbador-04.jpg)

Algunos ejemplos son:

* [Octopus passive buzzer](http://www.elecfreaks.com/estore/octopus-passive-buzzer-brick-obpb01.html), de Elecfreak
* [Kit de sensores para Arduino](http://tienda.bricogeek.com/kits-arduino/832-kit-de-37-sensores-compatible-arduino-1247563871496.html). BricoGeek. Dentro del kit con 37 módulos, hay uno con zumbador

En este **panel** está conectado el Zumbador al pin de salida **D0**. ¡Listo para usarse!

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-13/zumbador-05.jpg)

# Ejemplo 2: Generando Sonido. Tono de 1Khz

Para generar un sonido tenemos que producir una **señal cuadrarda** (enviando 1's y 0's alternativamente) a una **frecuencia** que se encuentre dentro del **rango audible**. Esa señal, al llegar al **zumbador**, hace que una **membrana** vibre, agitando las **moléculas del aire** a esa misma frecuencia, y por tanto produciendo una perturbación que captamos con nuestros oidos

El **rango audible humano** es aproximadamente entre **20Hz** (sonido muy grave) hasta **20Khz** (sonido muy agudo)

En este ejemplo haremos que el **zumbador** produzca un pitido a la **frecuencia de 1Khz**. ¿Cómo lo hacemos? Simplemente conectado el **pin de salida** con un **corazón** que lata a **1Khz**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-13/zumbador-06.jpg)

El **Corazón de 1Khz** se encuentra en el menú **Varios/Bombeo** de la colección 13. Para escucharlo conectamos el zumbador al **pin D0**, usando el panel mostrado en el [apartado anterior](#conexi%C3%B3n-de-placa-comercial-con-zumbador)

Al cargar el circuito en la placa empezaremos a **oir el tono**. Como es un poco molesto, lo podemos **apagar** con el **interruptor** de la Icezum Alhambra, que elimina la **alimentación** de los periféricos (pero que mantiene la de la FPGA para poder seguir cargando circuitos)

(animación pulsador on/off icezum alhambra)


# Ejemplo 3: Timbre

# Ejemplo 4: Sirena luminosa y acústica, con dos zumbadores


# Ejercicios propuestos (X BitPoints)

Ver los detalles de los ejercicios y las **entregas** en el menú **Archivos/Ejemplos/2-Ejercicios** de la colección de este tutorial

**Resumen**:

* **Ejercicio 1** (Total **x Bitpoints**): 

* **Ejercicio 2** (Total **x Bitpoints**): 

* **Ejercicio 3** (Total **x Bitpoints**): 

* **Ejercicio 4** (**3 Bitpoints**). Ejercicio Libre. Premiar la creatividad. **Entregar** por redes sociales o github: Pantallazos, enlaces, vídeos, etc...

# Ejercicios entregados

## Primero

### Ejercicio 1
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 2
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 3
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 4
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()


## Segundo

### Ejercicio 1
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 2
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 3
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 4
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

## Tercero

### Ejercicio 1
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 2
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 3
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 4
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

# FAQs

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

