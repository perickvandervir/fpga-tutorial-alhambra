![]()

# Vídeo

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

Haz click en la imagen para ver el **vídeo en Youtube**

# Descripción


# Colección

**Academia-Jedi-HW-12.zip**: Colección para este tutorial. Descargar e instalar 

# Contenido

* [Introducción](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-12:-Interruptores-y-pulsadores-externos#introducci%C3%B3n)
* [Pulsadores externos](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-12:-Interruptores-y-pulsadores-externos#pulsadores-externos)
  * [Conexion a pines de 3.3v (GPx)](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-12:-Interruptores-y-pulsadores-externos#conexi%C3%B3n-a-pines-de-33v-gpx)
  * [Conexión a pines de 5v (Dx)](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-12:-Interruptores-y-pulsadores-externos#conexi%C3%B3n-a-pines-de-5v)
    * [Pulsador en placa entrenadora](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-12:-Interruptores-y-pulsadores-externos#pulsador-en-placa-entrenadora)
    * [Pulsador en PCBPrint](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-12:-Interruptores-y-pulsadores-externos#pulsador-en-pcbprint)
* [Interruptores externos](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-12:-Interruptores-y-pulsadores-externos#interruptores-externos)
  * [Conexión a pines de 3.3v (GPx)](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-12:-Interruptores-y-pulsadores-externos#conexi%C3%B3n-a-pines-de-33v-gpx-1)
  * [Conexión a pines de 5v (Dx)](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-12:-Interruptores-y-pulsadores-externos#conexi%C3%B3n-a-pines-de-5v-dx)
    * [Interruptor en placa entrenadora](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-12:-Interruptores-y-pulsadores-externos#interruptor-en-placa-entrenadora)
    * [Interruptor en PCBPrint](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-12:-Interruptores-y-pulsadores-externos#interruptor-en-pcbprint)
* [Paneles personalizados](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-12:-Interruptores-y-pulsadores-externos#paneles-personalizados)


# Introducción

Para **introducir** bits en nuestros **circuitos digitales** usamos **periféricos de entrada**, como pulsadores, interruptores, sensores de Infrarrojos, etc. Se conectan a las entradas del circuito. El circuito lee estos bits, y realiza las operaciones de **manipulación**, **transporte** y **almacenamiento**. Finalmente saca bits por sus **salidas** para que lleguen a los **periféricos de salida**, como LEDs, servos, zumbadores, etc.

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-12/Introduccion-01.png)

En este tutorial nos centraremos en los **interruptores** y **pulsadores**.
Tanto los pulsadores como los interruptores pueden estar en **dos posiciones**, en una de ellas envían un **bit a 0** y en la otra un **bit a 1**. La diferencia está en que en los **pulsadores**, uno de las posiciones es **temporal**, o **no estable**, mientras que en el **interruptor** ambas son **estables**

El **pulsador** cuando está **en reposo** se encuentra en su **posición estable**. Nosotros usaremos esta posición para transmitir el **bit 0**: que significa pulsador **NO apretado**. Al **apretarlo** con el dedo envía un **1**, y permanece en esa posición de forma **temporal**, mientras mantengamos el dedo **haciendo fuerza**. En el momento en que quitamos el dedo, el pulsador volverá **automáticamente** a su posición de reposo

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-12/Introduccion-02.png)

Su funcionamiento se muestra en esta **animación**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-12/introduccion-button-anim.gif)

Los interruptores tiene **dos posiciones estables**: una vez que están en una posición, **permanecen** en ella hasta que volvamos a ejercer fuerza para cambiarla. A diferencia de los pulsadores, **NO cambian** al dejar de ejercer esta fuerza. 


![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-12/Introduccion-03.png)

El que la posición de la derecha sea un 0 ó un 1 dependerá de cómo hagamos las conexiones. Todas las combinaciones son posibles. En esta **animación** podemos ver su funcionamiento

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-12/introduccion-switch-anim.gif)

Los **interruptores** y los **pulsadores** los podemos conectar tanto a los **pines de 3.3v** (GPx) como a los **pines de 5v** (Dx) de la [Icezum Alhambra](https://github.com/FPGAwars/icezum/wiki). Según dónde se conecten, tendremos que modificar el valor de la **resistencia**

# Pulsadores externos

Los **pulsadores** se conectan mediante el siguiete **esquema**, donde el valor de la **resistencia R** depende del **pin de la FPGA** que usemos para la conexión

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-12/pulsador-01.png)

Con este esquema tenemos un pulsador que envía un **0** cuando  **NO está pulsado**. Si sabes electrónica analógica, la resistencia es de ***pull-down**. Si conectamos una de **pull-up** el comportamiento será el inverso: el **pulsador** envíaría un **1** cuando **NO está puslado**

## Conexión a pines de 3.3v (GPx)

Cuando lo conectamos a los **pines de 3.3v** de la Icezum Alhambra (GPx), los valores típicos de la resistencia que usaremos serán entre **1K** y **100K**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-12/pulsador-02.png)

En este ejemplo se puede ver el **montaje** de un pulsador conectado al **pin GP0**, usando una **resistencia** de **10K**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-12/pulsador-03.png)

El **cable rojo** está conectado a la salida de **3.3v** de la Icezum Alhambra, el **negro** a cualquier de los de **GND** y el **amarillo** al **pin GP0**

Y este es el **montaje real**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-12/pulsador-04.png)

## Conexión a pines de 5v

Para la conexión a los **pines de 5v**, usamos el mismo esquema que para los de 3.3v pero la **resistencia** de **pull-down** tiene que estar entre **460ohm** y **2K**. El valor recomendado es de **1K**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-12/pulsador-05.png)

Este valor de las resistencias es debido al **convertidor de niveles** de 5v a 3.3v. Los pines de 5v no salen directamente de la FPGA, sino que pasan por un convertidor. Para que se **configure** correctamente como una **entrada** la resistencia de **pull-down** debe tener, típicamente, esos valores

### Pulsador en placa entrenadora

El **esquema de conexionado** de un pulsador externo al **pin D0** de la Icezum Alhambra se muestra en este dibujo hecho con **Fritzzing**. Se ha utilizado una **resistencia de 1K**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-12/pulsador-06.png)

Y este es el **montaje real**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-12/pulsador-07.jpg)

### Pulsador en PCBPrint

También podemos hacer nuestros pulsadores externos con la **impresoras 3D**. Este es el [PCBPrint Alhambra Button](https://github.com/PCBPrints/Alhambra-button/wiki), que incluye un pulsador. Todas las **instrucciones de montaje** se encuentra en el enlace de la placa

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-12/Pulsador-09.jpg)

En esta **foto** vemos el pulsador conectado al **pin D0** de la Icezum Alhambra:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-12/pulsador-08.jpg)

Puedes encontrar más [PCBPrints en el repositorio](https://github.com/PCBPrints/PCbPrints)

# Interruptores externos

Los interruptores típicamente tiene **3 pines**. Uno es el **común**, que se conecta a alguno de los otros dos según en la posición en la que se encuentre. El **esquema de conexión**  genérico es:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-12/interruptor-01.png)

En este interruptor, el **pin común** es el del **centro**, y es el que se conecta directamente al **pin de la FPGA**. Por otro pin se introduce **GND** y por el último la **alimentación**, que dependerá del tipo de pin de la FPGa al que nos conectemos. Introduciremos **5v** ó **3.3v**. Seún la posición donde esté colocado el interruptor, a la FPGA le llegará la señal GND (0) ó la de alimentación (1)

## Conexión a pines de 3.3v (GPx)

Este es un ejemplo de conexión de un interruptor al **pin GP0** de la Icezum Alhambra. La pata común del interruptor es la del **centro**, que se conecta directamente a GP0. La pata de la derecha se conecta a **GND** y la de la izquierda a **3.3v**. 

 **¡Cuidado! Es un pin de 3.3v. ¡NO CONECTARLO A 5V!**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-12/interruptor-02.png)

En esta foto se muestra el **montaje real**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-12/Interruptor-03.jpg)

## Conexión a pines de 5v (Dx)

Este es el **esquema** para conectar un interruptor a los **pines de 5v** de la Icezum alhambra. Lo implementaremos de dos maneras, con **placa entrenadora** y con **una PCBPrint**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-12/Interruptor-04.png)

### Interruptor en placa entrenadora

Este es el **esquema en Fritzzing**. Es muy parecido al interruptor para 3.3v, pero conectando ahora al **pin D0** en vez del GP0 y al de **5v** en vez del al de 3.3v

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-12/Interruptor-05.png)

Y esta es una foto del **montaje real**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-12/Interruptor-06.jpg)

### Interruptor en PCBPrint

Una opción muy cómoda es hacernos **nuestras propias placas** con interruptor externo con la **impresora 3D**. Una de estas placas es la [Alhambra Switch](https://github.com/PCBPrints/Alhambra-switch/wiki), pero puedes encontrar más en el [repositorio de los PCBPrints](https://github.com/PCBPrints/PCbPrints)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-12/Interruptor-07.jpg)

En esta **foto** vemos la **Alhambra switc**h conectada al **pin D0** de la Icezum Alhambra:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-12/Interruptor-08.jpg)

# Paneles personalizados

Ya hemos visto algunos **periféricos** con los que empezar a montar **paneles de control** para propar nuestros circuitos circuitos. Utilizaremos una **base de corcho** donde colaremos los elementos con **chinchetas**

(Panel de corcho)
(Piezas impresas para el panel)

# TODO

* Ejemplo 1: Pulsador, interrutor, LEDs
* Ejemplo 2: Interruptor + servo
* Ejemplo 3: Dos interruptores + LEDs
* Ejercicios:
  * Interruptor para definir donde mira Franky. Botón para emitir ráfagas
  * Interruptor para estado de la puerta. Pulsador para timbre luminoso
  * 4 interruptores para mostrar bits



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




