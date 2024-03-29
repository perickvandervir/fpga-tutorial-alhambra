![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/Portada/Tut-16-portada.png)

# Vídeo

[![Click to see the youtube video](http://img.youtube.com/vi/iIJkpmfZkUY/0.jpg)](https://www.youtube.com/watch?v=iIJkpmfZkUY&list=PLmnz0JqIMEzXaeYVzf2TfTzRekPIVoljw&index=16)

Haz click en la imagen para ver el **vídeo en Youtube**

# Descripción

Los **sensores de infrarrojos** nos permiten **detectar** objetos a corta distancia. Aprenderemos a manejarlos y los usaremos para dotar al robot **icebot** de su primer **comportamiento reactivo**

# ¡Icestudio 0.3.2!

Hemos liberado hace muy poco [Icestudio 0.3.2](https://github.com/FPGAwars/icestudio/releases/tag/0.3.2). La que estábamos usando antes era la 0.3.2-Beta. Por favor, **actualizarse** a esa versión. La colección empleada en este tutorial está hecha con esta versión, y en las anteriores no se verá correctamente

# Colección

[Academia-Jedi-HW-16.zip](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/Collection/Academia-Jedi-HW-16.zip): Colección para este tutorial. Descargar e instalar 

# Contenido

* [Introducción](#introducci%C3%B3n)
* [Sensores IR](#sensores-ir)
* [Modelos de sensores](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/VIDEO-16:-Sensores-de-Infrarrojos-(IR)#modelos-de-sensores)
* [Practicando con el sensor octopus IR](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/VIDEO-16:-Sensores-de-Infrarrojos-(IR)#practicando-con-el-sensor-octopus-ir)
   * [Conexión a la Icezum Alhambra](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/VIDEO-16:-Sensores-de-Infrarrojos-(IR)#conexi%C3%B3n-a-la-icezum-alhambra)
  * [Ejemplo 1: Encendiendo un LED al detectar presencia](#ejemplo-1-encendiendo-un-led-al-detectar-presencia)
  * [Ejemplo 2: Emitiendo pitidos al detectar objetos](#ejemplo-2-emitiendo-pitidos-al-detectar-objetos)
  * [Ejemplo 3: Pitidos con el spinner](#ejemplo-3-pitidos-con-spinner)
  * [Ejemplo 4: Detección blanco - negro](#ejemplo-4-detecci%C3%B3n-blanco---negro)
* [Comportamientos reactivos con el Icebot](#comportamientos-reactivos-con-el-icebot)
  * [Robots reactivos](#robots-reactivos)
  * [Esquema del Icebot](#esquema-del-icebot)
  * [Experimento 1: Sensor derecho - motor izquierdo](#experimento-1-sensor-derecho---motor-derecho)
  * [Experimento 2: Sensor derecho negado - motor derecho](#experimento-2-sensor-derecho-negado---motor-derecho)
  * [Experimento 3: Sensor izquierdo negado - motor izquierdo](#experimento-3-sensor-izquierdo-negado---motor-izquierdo)
  * [Experimento 4: Superposción. Comportamiento de seguir objetos](#experimento-4-superposici%C3%B3n-comportamiento-de-seguir-objetos)
    * [El patito y su mamá](#el-patito-y-su-mam%C3%A1)
* [Ejercicios propuestos (25 Bitpoints)](#ejercicios-propuestos-25-bitpoints)
* [Ejercicios entregados](#ejercicios-entregados)
  * [Ximo Catala (Ximocat)](#ximo-catala-ximocat)
  * [Josep Montoliu (Klarojms)](#josep-montoliu-klarojms)
  * [Andrés (@Avarez_)](#andr%C3%A9s-avarez_)
* [Autor](#autor)
* [Licencia](#licencia)
* [Enlaces](#enlaces)
* [Preguntas frecuentes](#preguntas-frecuentes)

# Introducción

En este tutorial practicaremos con un sensor nuevo: el **sensor de IR digital**, de corto alcance, que nos permitirá **detectar objetos** a corta distncia, así como **distinguir** el color **negro** del **blanco** en una superficie plana. Así es como nos queda el **mapa de periféricos** que hemos tratado hasta ahora

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/perifericos-vistos.png)


# Sensores IR
Los **sensores de infrarrojos** (IR) que usaremos nos permiten detectar la **presencia** de un objeto que está **delante** de ellos, a un centímetro aproximadamente. Constan de un **emisor** y un **receptor**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/sensor-ir-01.png)

El emisor es un **LED infrarrojo**. Es un LED de los que ya conocemos, pero en vez de emitir luz visible, la emite en el **espectro infrarrojo**, que no nuestros ojos no pueden ver. El emisor está **constantemente emitiendo**, cuando el sensor está alimentado. Esto lo podemos observar mirando el sensor a través de la **cámara** de nuestro **teléfono móvil**: se puede a preciar un **color azulado/violeta**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/sensor-ir-02.png)

El receptor es un **fototransistor**, que se activa cuando recibe luz infrarroja. La **detección de objetos** se hace por **reflexión**. La luz infrarroja que está constantemente generando el emisor se **refleja** en el objeto y llega al **receptor**, que nos devuelve un **1** (objeto detectado). Si por el contrario no hay objeto, la luz infrarroja se pierde y **no** regresa al receptor. En este caso el sensor nos devuelve un **0** (Objeto no detectado)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/sensor-ir-03.png)

Estos sensores también se pueden utilizar para distinguir el **blanco** del **negro** en una superficie plana, y construir así robots que puedan por ejemplo **seguir un camino negro**. Cuando el sensor está sobre blanco, la luz del emisor se **refleja completamente**, devolviéndo un **1**. Cuando esta sobre la parte **negra**, **no hay reflexión**. El negro absorbe la luz, y no la refleja, por lo que no llega nada al receptor y devuelve un **0**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/sensor-ir-04.png)

# Modelos de sensores

Los **sensores de IR** que utilizaremos en este tutorial son **digitales**. Devuelven **0** ó **1** dependiendo de si detectan el objeto o no. Cualquier de estos valdría: (y si buscas por internet encontrarás todavía más)

| Foto  | Nombre | Descripción |
|-------|--------|-------------|
| ![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/sensor-modelo-1.png)      | [Octopus Hunt sensor](http://www.elecfreaks.com/estore/octopus-hunt-sensor.html) | Este es el modelo que estoy usando en el tutorial. Está fabricado por [Elecfreaks](http://www.elecfreaks.com/). Es el que se encuentra en los kits de robótica de BQ |
| ![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/sensor-modelo-2.jpg) | [Módulo sigue líneas mblock](https://www.makeblock.es/productos/modulo_sigue_lineas/)   |  Es el sensor del kit del [robot mbot](https://makeblock.es/productos/robot_educativo_mbot/). Incluye **2 sensores IR** en la misma placa. Hay que soldarle pines para conectar a la Icezum Alhambra  |
| ![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/sensor-modelo-3.jpg) | [TCRT5000-ir](https://www.iberobotics.com/producto/modulo-sensor-siguelineas-tcrt5000-ir/)    |  Compatible con la Icezum Alhambra. Permite también lectura analógica. Distribuido por [Iberobotics](https://www.iberobotics.com/)    |
| ![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/sensor-modelo-4.png) | [TCRT5000-IR-estrecho](https://www.iberobotics.com/producto/modulo-sensor-siguelineas-tcrt5000-ir-2/)  | Modelo estrecho. Compatible con Icezum Alhambra. Distribuido por [Iberobotics](https://www.iberobotics.com/)  |
| ![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/sensor-modelo-5.jpg) | [Sensor QTR-8RC](http://tienda.bricogeek.com/componentes/257-array-de-sensores-infrarojos-qtr-8rc-digital.html)  | Tira de **8 sensores IR**. Se puede partir en dos grupos de 2 y 6 sensores. Hay que soldarle los pines. Distribuido por [BricoGeek](http://tienda.bricogeek.com/)   |
| ![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/sensor-modelo-6.jpg)  | [Sensores IR del kit Beduino](http://www.logix5.com/roboticaeducativa/producto/beduino/) | Kit distribuido por [Logix5](http://www.logix5.com/roboticaeducativa/) |

# Practicando con el sensor Octopus IR

El sensor que usaremos para las pruebas es el [Octopus IR](http://www.elecfreaks.com/estore/octopus-hunt-sensor.html)

## Conexión a la Icezum Alhambra

La conexión del sensor a la placa Icezum Alhambra se hace igual que los sensores que hemos visto hasta ahora: mediante un **cable de tres hilos** (señal, 5v y masa)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/octopus-ir-1.jpg)

Por un lado se conecta al sensor, y por el otro a cualquiera de los **pines de datos** con alimentación de la placa (**D0** - **D13**). En esta foto está conectado a D13:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/octopus-ir-2.jpg)

¡Y ya está listo! Ahora funciona exactmente igual que un pulsador externo

## Ejemplo 1: Encendiendo un LED al detectar presencia

Vamos a probar el sensor. El circuito más sencillo posible que nos permite probarlo es el mismo que en el caso del pulsador: un **cable** que vaya directo desde el **sensor IR** a un **LED externo**. De esta forma, cuando el sensor detecte un objeto, devolverá un **1** que hará que se encienda en LED. Cuando no detecta objeto, devolverá **0** y el LED estará apagado

El **montaje** es el mostrado en la siguiente foto. El sensor está conectado a la entrada **D13**, y el LED a la salida **D12**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/Ejemplo-1-2.jpg)

El circuito en Icestudio es el siguiente. Está accesible también desde la colección **Academia-Jedi-HW-16.zip**, en el menú **Archivo/Ejemplos/1-Ejemplos/1-Senosr-IR-LED**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/Ejemplo-1-1.png)

Lo cargamos en la placa para probar. Al pasar un objeto, a una distancia de **1 cm** aproximadamete, vemos que se enciende el LED

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/Ejemplo-1-anim.gif)

# Ejemplo 2: Emitiendo pitidos al detectar objetos

Ampliamos el montaje anterior añadiendo un **zumbador** conectado a la salida **D11**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/Ejemplo-2-1.jpg)

Haremos que pite al detectar un objeto, además de encenderse el LED. El circuito en Icestudio ya lo sabemos hacer. Sería así:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/Ejemplo-2-2.jpg)

Se ha añadido un **corazón de 2Khz**, para **emitir un pitido** a esa frecuencia. Va modulado por la señal procedente del sensir IR. Cuando no hay objeto, por el sensor llega un 0 que deshabilita la señal de 2Khz, por lo que al zumbador sólo le entra una señal con todo ceros, y no suena. Al detectarse un objeto, la señal de corazón llega al zumbador y pita

Cargamos el circuito y lo probamos. Funcionará igual que en el ejemplo 1, pero ahora además **sonará un pitido** que se mantendrá mientras tengamos el objeto delante del sensor

En este **Vídeo de youtube** se puede ver un **ejemplo de funcionamiento**

[![Click to see the youtube video](http://img.youtube.com/vi/rdhIZm3kZ_c/0.jpg)](https://www.youtube.com/watch?v=rdhIZm3kZ_c)

Este ejemplo es muy sencillo, pero muy divertido. Suena como los **escáneres** que hay en las **cajas de los supermercados**. De hecho, cuando mi hija Alicia de 8 años vió este ejemplo por primera vez, exclamó: "¡Papi! Vamos a jugar a los supermercados" :-)

# Ejemplo 3: Pitidos con spinner

La cosa se pone más divertida si al montaje anterior, usando el mismo circuito, añadimos un spinner de tal forma que sus brazos pasen por encima del sensor IR

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/Ejemplo-3-1.jpg)

Ahora si le damos **vueltas al spinner**, se escucharán pitidos continuamente, cada vez que los brazos atraviesan el sensor IR

En este **vídeo de youtube** se puede ver en **acción**:

[![Click to see the youtube video](http://img.youtube.com/vi/9gU3GpuzH3A/0.jpg)](https://www.youtube.com/watch?v=9gU3GpuzH3A)

## Ejemplo 4: Detección blanco - negro

Este tipo de sensores son muy útiles para detectar el **color negro** sobre el **blanco** en superficies **planas**. Y así podemos crear **robots rastreadores**, capaces de seguir una **línea negra**

Como ejemplo haremos un circuito que encienda un LED y emita un **pitido** cuando se **detecta el color Negro**. Es igual que el circuito del ejemplo 3, pero añadimos una **puerta NOT**. Antes pitaba cuando el sensor estaba a 1 (objeto detectado). Esto es equivalente a detectar el color blanco. Ahora queremos lo contrario: que pite cuando no hay objeto, es decir, cuando no hay señal reflejada. Esto es lo que el negro consigue. Por eso añadimos la puerta NOT

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/Ejemplo-4-1.png)

El montaje es similar al del ejemplo anterior. Ahora colocamos una **hoja blanca** con un trozo de **cinta aislante negra**, para que haya zonas negras y blancas. Cambiamos la orientación del sensor para que apunte a la hoja

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/Ejemplo-4-2.jpg)

**Cargamos** el circuito y probamos. En este **vídeo en youtube** se puede ver su **funcionamiento**

[![Click to see the youtube video](http://img.youtube.com/vi/zX8-kVyQrNo/0.jpg)](https://www.youtube.com/watch?v=zX8-kVyQrNo)

# Comportamientos reactivos con el Icebot

Los **robots móviles** más sencillos son los **robots reactivos**. Construiremos nuestro primer robot reactivo con el **Icebot**, y haremos una serie de experimentos para entender bien los **comportamientos reactivos**

## Robots reactivos

Los **robots reactivos** son aquellos que **reaccionan** ante un **estímulo**, sin conocimiento del **entorno**. Hay unos **estímulos** de entrada, que provocan una **respuesta inmediata** en el robot

El **esquema** de un robot reactivo es el mostrado en el siguiente **digrama**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/robot-reactivos-1.png)

El robot está formado por **tres elementos**:

* **Sensores**: Captan los **estímulos del entorno** y los entregan a la unidad que realiza su procesamiento
* **Circuito de procesamiento**: Es el que lee la información de los sensores y genera unas respuestas de salida para controlar los actuadores y generar la respuesta del robot. Es la parte que define el comportamiento del robot. Nosotros usaremos circuitos digitales en la FPGA
* **Actuadores**: Son los que realizan una acción sobre el entorno, y permiten al robot dar una respuesta

El **comportamiento que emerge** del robot, siguiendo este esquema se llama **comportamiento reactivo**

## Esquema del Icebot

Para convertir el **Icebot** en un **robot reactivo** sólo tenemos que añadirle los **sensores IR**. Se los colocaremos en la **parte frontal**, sujetos por una **goma**. El **sensor derecho** lo conectaremos a **D12** y el izquierdo a **D13**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/robot-reactivos-2.jpg)

El **esquema** de nuestro robot reactivo es:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/robot-reactivos-3.jpg)

Para este caso concreto, nuestros **elementos** serán los siguientes:

|    |  |
|------------|-------------|
| **Estimulos** | Son la **presencia** o **NO** de **objetos** delante de los sensores del robot |
| **Sensores** | Dos **sensores de infrarrojos** digitales, que devuelven **1** cuando hay un objeto delante y **0** cuando no lo hay |
| **Actuadores** | Dos **servos de rotación continua**, que tienen un controlador con 2 bits de entrada (Motorbit) que permiten que cada rueda esté en alguno de sus **tres estados posibles**: **parada**, giro en sentido **horario**, o giro en sentido **antihorario** |
| **Unidad de procesamiento** | **Circuito digital** que diseñaremos nosotros y que estará dentro de la **FPGA**
| **Respuesta** | Son los **movimientos del robot**: avanzar, parado, arco derecha, arco izquierda...|

## Experimento 1: Sensor derecho - motor derecho

Comenzaremos por un experimento muy sencillo: hacer que el **motor derecho** se mueva en **sentido horario** cuando se activa el **sensor derecho**. Además encederemos el **LED0** de pruebas 

El **circuito** es el siguiente:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/Ejemplo-5-Exp-1.png)

El **sensor derecho** está conectado directamente al **bit de on** del motor de la rueda derecha, de modo que al detectarse un objeto, se recibe un **1** y se activa el **motor derecho**, mientras el izquierdo está parado. El robot girará a la izquierda en arco, **embistiendo** el objeto que había delante. En cuanto ho tiene nada en su campo, el sensor lee un 0 y el motor se para

En este **vídeo en youtube** se puede ver el comportamiento en acción

![]([![Click to see the youtube video](http://img.youtube.com/vi/YM_dUvG2Ay8/0.jpg)](https://www.youtube.com/watch?v=YM_dUvG2Ay8))

## Experimento 2: Sensor derecho negado - motor derecho

Modificamos el circuito del experimento 1 añadiendo una **puerta NOT**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/Ejemplo-5-Exp-2.png)

Ahora, cuando el sensor derecho **detecte un objeto**, el motor derecho se **parará**, y cuando no haya nada seguirá movimiento, haciendo que el robot gire hacia la izquierda, en arco

El comportamiento se puede ver en este **vídeo en Youtube**:

[![Click to see the youtube video](http://img.youtube.com/vi/azZ6sUeNqLE/0.jpg)](https://www.youtube.com/watch?v=azZ6sUeNqLE)

## Experimento 3: Sensor izquierdo negado - motor izquierdo

El comportamiento del experimento anterior lo vamos a reproducir con el **lado izquierdo del robot**. Para que la rueda izquierda gire hacia "adelante" hay que configurarla en **sentido antihorario**, colocando un **0** en su bit del **sentido de giro**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/Ejemplo-5-Exp-3.png)

Y en este **vídeo en youtube** se ve el nuevo comportamiento

[![Click to see the youtube video](http://img.youtube.com/vi/XdsftCxiXMI/0.jpg)](https://www.youtube.com/watch?v=XdsftCxiXMI)

## Experimento 4: Superposición: Comportamiento de seguir objetos

Los circuitos de los experimentos 2 y 3 son **independientes**, ya que no tienen ningún recurso en común. Por tanto los podemos combinar mediante **superposición**, en la que los dos circuitos funcionan en **paralelo**. Uno controla la parte derecha de robot: sensor y rueda. Y el otro la izquierda. De forma independiente

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-16/Ejemplo-5-Exp-4.png)

El resultado es que aparece un **comportamiente emergente** que hace que el Icebot **siga un objeto**. Lo podemos ver en este **vídeo de youtube**

[![Click to see the youtube video](http://img.youtube.com/vi/k_445ceKKMc/0.jpg)](https://www.youtube.com/watch?v=k_445ceKKMc)

### El patito y su mamá

Este comportamiento de seguir objetos lo utiliza mi hija Alicia, de 8 años, para jugar al **juego del patito y su mamá**. Nos explica en este vídeo cómo funciona :-)

[![Click to see the youtube video](http://img.youtube.com/vi/CT7C3uGb3Ro/0.jpg)](https://www.youtube.com/watch?v=CT7C3uGb3Ro)

# Ejercicios propuestos (25 BitPoints)

Ver los detalles de los ejercicios y las **entregas** en el menú **Archivos/Ejemplos/2-Ejercicios** de la colección de este tutorial

**Resumen**:

* **Ejercicio 1** (Total **5 Bitpoints**): Alarma activada por sensor IR

Diseñar un circuito digital que haga sonar una **alarma** mientras el **sensor de 
infrarrojos** esté detectando un objeto. La alarma sonará por un **zumbador**, y estará  
compuesta por **dos tonos** de **1Khz** y **2Khz**, alternados a la frecuencia de **2Hz**

Cuando el sensor no detecta objetos, la alarma estará callada


* **Ejercicio 2** (Total **5 Bitpoints**): Barrera automática

Diseñar un circuito digital que suba una **barrera** cuando el **sensor de IR** detecta la  
presencia de un coche. Se cierra cuando no se detecta nada. El circuito todavía no 
temporiza nada, ni almacena información. Simplemente sube o baja la barrera en función
del estado del sensor IR


* **Ejercicio 3** (Total **10 Bitpoints**): **Icebot Policia**

Hacer un circuito digital para que el robot icebot **siga a un objeto**. Utilizará **dos  
sensores IR** colocados en su parte delantera. Siempre que el icebot esté en movimiento  
se activará una **sirena acústina** y otra **luminosa**. La sirena es la misma que la del 
ejercicio 1. La luminosa está formada por **dos LEDs** que parpadean anternativamente a  
la misma frecuecia que la acústica (2Hz)

* **Ejercicio 4** (**5 Bitpoints**). Ejercicio Libre. Premiar la creatividad. **Entregar** por redes sociales o github: Pantallazos, enlaces, vídeos, etc...

# Ejercicios entregados

## Ximo Catala (ximocat)

### Ejercicio 1
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-16/ximocat/Ejercicio16_1.jpg)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/RG4z2Z1_H4I/0.jpg)](https://www.youtube.com/watch?v=RG4z2Z1_H4I)

### Ejercicio 2
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-16/ximocat/Ejercicio16_2.jpg)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/BjGqC5q85Po/0.jpg)](https://www.youtube.com/watch?v=BjGqC5q85Po)

### Ejercicio 3
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-16/ximocat/Ejercicio16_3.jpg)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/vQSzpW_d6nQ/0.jpg)](https://www.youtube.com/watch?v=vQSzpW_d6nQ)

### Ejercicio 4
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-16/ximocat/Ejercicio16_4.jpg)

* **Vídeo** en Youtube: El **icebot** siguiendo al **escornabot** :-)

[![Click to see the youtube video](http://img.youtube.com/vi/38jg-GRpXAY/0.jpg)](https://www.youtube.com/watch?v=38jg-GRpXAY)

## Josep Montoliu (Klarojms)

### Ejercicio 1
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-16/klarojms/Ejercicio%201-1.png)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/evpH6hFIpG4/0.jpg)](https://www.youtube.com/watch?v=evpH6hFIpG4)

### Ejercicio 2
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-16/klarojms/Ejercicio%202-1.png)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/FMsJqQH3R5M/0.jpg)](https://www.youtube.com/watch?v=FMsJqQH3R5M)

### Ejercicio 3
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-16/klarojms/Ejercicio%203-1.png)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/kU7h_GlA_Ss/0.jpg)](https://www.youtube.com/watch?v=kU7h_GlA_Ss)

### Ejercicio 4
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-16/klarojms/Ejercicio%204-2.png)

* **Vídeo** en Youtube: El icebot siguiendo la línea negra

[![Click to see the youtube video](http://img.youtube.com/vi/HK_jZnUTWxw/0.jpg)](https://www.youtube.com/watch?v=HK_jZnUTWxw)

## Andrés (@Avarez_)

### Ejercicio 1
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-16/avarez/Ejercicio.16.1.png)

* [Vídeo en twitter](https://twitter.com/avarez_/status/987648918832996352)

### Ejercicio 2
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-16/avarez/Ejercicio.16.2.png)

* [Vídeo en Twitter](https://twitter.com/avarez_/status/987649683790155776)

### Ejercicio 3
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-16/avarez/Ejercicio.16.3.png)

* [Vídeo en twitter](https://twitter.com/avarez_/status/987650266240552960)

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
* [Octopus passive buzzer](http://www.elecfreaks.com/estore/octopus-passive-buzzer-brick-obpb01.html), de Elecfreak
* [Kit de sensores para Arduino](http://tienda.bricogeek.com/kits-arduino/832-kit-de-37-sensores-compatible-arduino-1247563871496.html). BricoGeek. Dentro del kit con 37 módulos, hay uno con zumbador


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



