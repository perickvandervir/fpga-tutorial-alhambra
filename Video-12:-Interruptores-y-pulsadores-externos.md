![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-12/Portada/Tut-12-portada.png)

# Vídeo

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

Haz click en la imagen para ver el **vídeo en Youtube**

# Descripción

Utilizaremos **interruptores** y **pulsadores** externos para **introducir bits** en nuestros circuitos digitales. Aprenderemos las diferentes formas de conexión, y construiremos **paneles de control** con ellos

# Colección

[Academia-Jedi-HW-12.zip](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-12/Collection/Academia-Jedi-HW-12.zip): Colección para este tutorial. Descargar e instalar 

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
  * [Piezas 3D para el panel](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-12:-Interruptores-y-pulsadores-externos#piezas-3d-para-el-panel)
  * [Panel de prueba](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-12:-Interruptores-y-pulsadores-externos#panel-de-prueba)
* [Ejemplo 1: Pulsador, Interruptor y LEDs](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-12:-Interruptores-y-pulsadores-externos#ejemplo-1-pulsador-interruptor-y-leds)
* [Ejemplo 2: Tres interruptores y LEDs](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-12:-Interruptores-y-pulsadores-externos#ejemplo-2-tres-interruptores-y-leds)
* [Ejemplo 3: Apertura de una cerradura con clave](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-12:-Interruptores-y-pulsadores-externos#ejemplo-3-apertura-de-una-cerradura-con-clave)
* [Ejercicios propuestos (16 Bitpoints)](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-12:-Interruptores-y-pulsadores-externos#ejercicios-propuestos-16-bitpoints)



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
i
# Paneles personalizados
c
Ya hemos visto algunos **periféricos** con los que empezar a montar **paneles de control** para propar nuestros circuitos circuitos. Utilizaremos una **base de corcho** donde colaremos los elementos con **chinchetas**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-12/panel-01.jpg)

## Piezas 3D para el panel

Usaremos **piezas impresas en 3D** para fijar los elementos al panel. Todos los que se muestran a continuación se han diseñado con [FreeCAD](https://www.freecadweb.org/?lang=es_ES)

|  Pieza    |  Descripción    |
|-----------|-----------|
| ![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-12/panel-02-icezum-alhambra-support.jpg)   | [Soporte para Icezum Alhambra](https://github.com/FPGAwars/Icezum-Alhambra-3D-support/wiki). Coloca la Icezum Alhambra en su base y sujétala al corcho usando **fíjadores de esquina**  |
| ![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-12/panel-03-icezum-alhambra-support.jpg)  | [Soporte para Servo Futaba 3003](https://github.com/Obijuan/3D-parts/wiki/Soporte-para-servo-Futaba-3003). Base para dar estabilidad al servo. Sujétala al corcho usando **fijadores de esquina**  |
| ![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-12/panel-04-puntero-servo.jpg)   | [Puntero para Servo Futaba 3003](https://github.com/Obijuan/3D-parts/wiki/Puntero-para-Servo-Futaba-3003). Muy útil para ver cómo ha girado el servo     |
| ![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-12/panel-05-clavijas-servo.png)  |  [Clavijas de amarre para servos](https://github.com/Obijuan/3D-parts/wiki/Servo-pins-para-Futaba-3003). Fija otras piezas a los servos, sin usar tornillos   |  
| ![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-12/panel-06-tablero-indicador-servo.jpg)  | [Tablero indicador para servo](https://github.com/Obijuan/3D-parts/wiki/Tablero-indicador-binario-para-Servo). Mostrar las dos posiciones del servobit de 180 grados. Fijado al servo a través de clavijas de amarre  |
| ![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-12/panel-07-fijador-esquinas.jpg)   |    [Fijador de esquinas](https://github.com/Obijuan/3D-parts/wiki/Fijador-de-esquinas). Amarra al corcho cualquier pieza con esquinas    |
| ![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-12/panel-08-fijador-cables.jpg)  |  [Fijador de cables](https://github.com/Obijuan/3D-parts/wiki/Fijador-de-cables-con-chinchetas). Mantén los cables fijados al corcho y bien ordenados :-) |
| ![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-12/panel-09-fijador-placas.jpg)  |  [Fijador de placas](https://github.com/Obijuan/3D-parts/wiki/Fijador-de-placas). Fija los PCBprints y otras placas al corcho   |

## Panel de prueba

Este es un **ejemplo** de panel para hacer **pruebas**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-12/panel-10.jpg)

Tiene **dos pulsadores**, **tres interruptores** y un **servo**. Tanto la icezum Alhambra como el servo están amarrados mediante **fijadores de esquinas** y los **PCBprints** con **fijadores de placas**

# Ejemplo 1: Pulsador, Interruptor y LEDs

En este primer ejemplo conectadores un **Interruptor** y un **pulsador externos** en los pines de 5v **D12** y **D13**. Haremos un circuito para que enciendan los **LEDS 7** y **0** respectivamente. Este es el **panel** creado para probarlo:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-12/ejemplo1-01.jpg)

El circuito en **Icestudio** ya lo sabemos hacer. La única novedad es que elegimos los pines de entrada **D13** y **D12** para el **pulsador** y el **interruptor** respectivamente

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-12/ejemplo1-02.jpg)

**Cargamos** el ejemplo en la placa y lo **probamos**. En esta **animación** vemos el funcionamiento: Con el interruptor encendemos el LED 0 y con el pulsador el LED 7 (ambas cosas se pueden hacer a la vez, por supuesto)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-12/Ejemplo-1-anim.gif)

# Ejemplo 2: tres interruptores y LEDs

En este ejemplo conectaremos **tres interruptores** a los pines **D13**, **D12** y **D1**1 y los usaremos para encender **seis LEDS**, dos por cada interruptor. El **panel** es el siguiente:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-12/Ejemplo2-01.jpg)

En el circuito **conectaremos** el primer interruptor a los **LEDs 7** y **6**, el segundo a **4** y **3**, y el tercero a los **LEDs 1** y **0**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-12/Ejemplo2-02.jpg)

Lo **cargamos** para probarlo. En esta **animación** se muestra su funcionamiento:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-12/Ejemplo-2-anim.gif)

Utilizando los interruptores, ya podemos introducir **números binarios** en nuestros circuitos

# Ejemplo 3: Apertura de una cerradura con clave

Utilizamores **3 interruptores** para introducir un **código** de 3 bits. Al apretar un **pulsador** se moverá un **servo** si el código es el correcto, simulando que es la **apertura de la caja fuerte**. El código para abrir la caja fuerte será **111**. Es decir, los tres switches a 1. En los **LEDs** se mostrará el estado de los interruptores, igual que en el ejemplo 2

El **panel** es el siguiente

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-12/Ejemplo-3-01.png)

Para implementar el circuito, utilizaremos **dos puertas AND** para saber si el código es el correcto. Se activará la señal final si todos los interruptores están a 1. La cerradura se **abrirá** si el **código es correcto** Y se ha **apretado** el pulsador, por lo que utilizaremos una **tercera puerta AND**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-12/Ejemplo-3-02.png)

**Cargamos** el circuito y lo **probamos**. En esta **animación** se muestra el funcionamiento

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-12/Ejemplo-3-anim.gif)

Al **soltar** el pulsador, la cerradura vuelve a su **posición inicial**. Lo suyo sería que se quedase abierta durante un tiempo, o hasta que apretásemos otro pulsador. Pero para ello **necesitamos almacenar bits**, que todavía no sabemos :-)

# Ejercicios propuestos (16 BitPoints)

Ver los detalles de los ejercicios y las **entregas** en el menú **Archivos/Ejemplos/2-Ejercicios** de la colección de este tutorial

**Resumen**:

* **Ejercicio 1** (Total **5 Bitpoints**): Utilizar un **interruptor** y **pulsador externos** para 
controlar a **Franky**. Diseñar un circuito digital para que Franky mueva la cabeza a 
derecha o izquierda según el estado del interruptor. Al apretar el pulsador ambos ojos 
parpadearán con una frecuencia de 10Hz. Con esto convertimos a Franky en un robot defensivo. Con sus ráfagas láser dispara a los enemigos, que le vienen por la derecha y la izquierda :-)

* **Ejercicio 2** (Total **3 Bitpoints**): 

* **Ejercicio 3** (Total **5 Bitpoints**): 

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




