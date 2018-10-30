![]()

# Vídeo

TODO

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

Haz click en la imagen para ver el **vídeo en Youtube**

# Descripción

TODO

# Colección

**Academia-Jedi-HW-29.zip**: Colección para este tutorial. Descargar e instalar 

# Contenido

* [Introducción](#introducci%C3%B3n)
* [Registros](#registros)
  * [Registros con carga paralela](#registro-con-carga-paralela)
    * [Ejemplo 1: Almacenamiento de un número de 3 bits](#ejemplo-1-almacenamiento-de-un-n%C3%BAmero-de-3-bits)
  * [Registros de desplazamiento](#registros-de-desplazamiento)
    * [Ejemplo 2: Carga y desplazamiento de un dato de 3 bits](#ejemplo-2-carga-y-desplazamiento-de-un-dato-de-3-bits)
    * [Ejemplo 3: Disparos arcade](#ejemplo-3-disparos-arcade)
* [Comparadores](#comparadores)
  * [Ejemplo 4: Comparando números de 3 bits](#ejemplo-4-comparando-n%C3%BAmeros-de-3-bits)
  * [Comparadores de un operando](#comparadores-de-un-operando)
    * [Ejemplo 5: Apertura de caja fuerte con código](#ejemplo-5-apertura-de-caja-fuerte-con-c%C3%B3digo)
* [Aplicaciones](#aplicaciones)
  * [Ejemplo 6: El juego de la ruleta](#ejemplo-6-juego-de-la-ruleta)
  * [Ejemplo 7: Control por comandos](#ejemplo-7-control-por-comandos)
* [Comunicando la FPGA con un Arduino](#comunicando-la-fpga-con-un-arduino)
  * [Comunicación Arduino -> FPGA (Escritura)](#comunicaci%C3%B3n-arduino---fpga-escritura)
    * [Circuito sincronizador](#circuito-sincronizador)
    * [Receptor serie síncrono](#receptor-serie-s%C3%ADncrono)
    * [Software para escritura](#software-para-escritura)
    * [Ejemplo 8: Implementación de un puerto de salida adicional para el Arduino](#ejemplo-8-implementaci%C3%B3n-de-un-puerto-de-salida-adicional-para-el-arduino)
  * [Comunicación FPGA -> Arduino (Lectura)](#comunicaci%C3%B3n-fpga---arduino-lectura)
    * [Transmisor serie síncrono](#transmisor-serie-s%C3%ADncrono)
    * [Software para lectura](#software-para-lectura)
    * [Ejemplo 9: Implementación de un puerto de entrada adicional para el Arduino](#ejemplo-9-implementaci%C3%B3n-de-un-puerto-de-entrada-adicional-para-el-arduino)
* [Ejercicios propuestos (20 Bitpoints)](#ejercicios-propuestos-20-bitpoints)
* [Ejercicios entregados](#ejercicios-entregados)
* [Autor](#autor)
* [Licencia](#licencia)
* [Enlaces](#enlaces)
* [Preguntas frecuentes](#preguntas-frecuentes)

# Introducción

TODO

# Registros

Los **registros** son los componentes mínimos que nos permiten **almacenar números de varios bits** en nuestros circuitos. Con ellos ya no sólo recordamos bits aislados, sino datos más complejos. Están compuestos por la **unión de biestables D**, tanto en paralelo como en cadena

Hay muchos tipos de registros. Los que nosotros usaremos en este tutorial son los de **carga paralela** y los **registros de desplazamiento**. Los últimos amplían a los primeros proporcionando la opción de **desplazar los bits** previamente cargados

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/reg-01.png)

Como icono usamos varias **chinchetas**, para indicar que hay **varios biestables D en paralelo**. La anchura del bus de datos de entrada y salida, de ambos registros, es igual a la cantidad de bits del registro

## Registro con carga paralela

Son la **extensión del biestable D** a varios **bits en paralelo**. Nos permiten cargar y almacenar un número de **N bits**, que se captura cuando se recibe un **tic de captura** en su **entrada load**. Aquí se muestra un **registro de 8 bits**, junto a un biestable D

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/reg-02.png)

El **parámetro** nos permite establecer su **valor inicial** al arrancar el circuito. La **salida** del registro es **un bus de 8 bits**, por donde sale el dato almacenado. Tiene una **entrada**, también de **8 bits**, por donde se **capturan** los datos cuando llega un **tic** por la **entrada load**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/reg-03.gif)

En la **animación** se mustra un **registro genérico** que está capturando dos números, el 25 y 17 (representados en decimal) cuando llegan los **tics de captura**

### Ejemplo 1: Almacenamiento de un número de 3 bits

Para probar el funcionamiento de estos registros usaremos uno de **3 bits** para almacenar el número introducido en binario por **tres pulsadores**. El número se muestra en decimal en el **display de 7 segmentos** al apretar la **tecla de Enter** (captura). 

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/reg-04.png)

Este circuito es mucho **más claro** y **compacto** que los que hacíamos en el [tutorial 28](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-28:-Biestables-de-datos-y-cambio) al usar **biestables D** aislados. Son las ventajas del **diseño jerárquico** :-)

En el **montaje** hay **tres pulsadores**, un **botón** que hace las veces de **tecla Enter** y el **display de 7 segmentos**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/reg-05.png)

Lo **cargamos** y lo **probamos**. ¡Nuestro registro almacena!

[![Click to see the youtube video](http://img.youtube.com/vi/dsM7oMuvQK4/0.jpg)](https://www.youtube.com/watch?v=dsM7oMuvQK4)

## Registros de desplazamiento

Los **registros de desplazamiento** son iguales a los de **carga paralela**, con una entrada adicional para **desplazar los bits** una posición en un sentido. Nosotros usaremos registros que desplazan los bits hacia la **izquierda**, en el sentido de los bits más significativos (multiplicación por 2). Este es un ejemplo de **registro de desplazamiento de 8 bits**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/reg-06.png)

Cuando el registro recibe el **tic de carga**, captura el dato que entra en paralelo, igual que los registros de carga paralela. Cuando recibe un **tic de desplazamiento**, mueve los bits una posición hacia la **izquierda**, añadiendo el bit de su **entrada serie** como bit de **menor peso**, y sacando el de **mayor peso** por su **salida serie**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/reg-07.png)

### Ejemplo 2: Carga y desplazamiento de un dato de 3 bits

Para experimentar haremos un circuito para **cargar un dato** en un **registro de 3 bits**, y **desplazarlo**. El dato se introduce por **3 interruptores** y se captura al apretar la **Tecla ENTER**. Se muestra en **binario** en tres **LEDs** y en **decimal** en un **display de 7 segmentos**. Con otro **botón** hacemos que se **desplace**. El **montaje** es el siguiente:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/reg-09.png)

Este es el **circuito**. Por la **entrada serie** se introduce siempre un **bit a 0**, y la **salida serie** no se conecta a ningún sitio

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/reg-08.png)

Lo **cargamos** y lo **probamos**. En el **vídeo** se carga primero el dato 1, luego el 3 y finalmente el 7. Todos se desplazan 3 bits a la izquierda

[![Click to see the youtube video](http://img.youtube.com/vi/h3GwBqxl7O4/0.jpg)](https://www.youtube.com/watch?v=h3GwBqxl7O4)

### Ejemplo 3: Disparos arcade

En el [ejercicio 2 del tutorial 26](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-26:-Tiempo,-tics-y-temporizadores#ejercicios-propuestos-25-bitpoints) usamos **temporizadores** para generar el **movimiento de una bala** en los **LEDs**, emulando los **juegos arcade**. Crearemos el mismo efecto de una forma más fácil, usando un **registro de desplazamiento** de 8 bits.

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/reg-10.png)

El registro de desplazamiento almacena la información de **visualización** de las balas en vuelo. Un bit a **1** indica que **hay una bala** en esa posición. Si está a **0** es que **no** hay nada. El registro se está constantemente desplazando, con cada tic emitido por el corazón de **50ms**. Cada bala permanece 50ms en un **LED**, y luego pasa al siguiente. Como hay 8 leds, una bala tardará 8 * 50 = **400ms** en recorrerlos todos. Si queremos que vaya más rápido, sólo hay que poner un tiempo menor

Mediante el **pulsador de disparo**, se carga un 1 en el **biestable D** y cuya salida se usa como **entrada serie** del registro de desplazamiento. En ese momento la bala saldrá disparada con el siguiente tic del corazón (Es un biestable recámara). Adicionalmente hay conectado un bloque que **emite un pitido** cada vez que se **dispara**

Para probarlo sólo necesitamos un **pulsador** y un **zumbador** para escuchar los disparos

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/reg-11.png)

Lo **cargamos** y lo **probamos**. Cada vez que se aprieta el pulsador, se dispara una bala. Puede haber varias balas en vuelo a la vez

[![Click to see the youtube video](http://img.youtube.com/vi/picuCVb8p3w/0.jpg)](https://www.youtube.com/watch?v=picuCVb8p3w)

# Comparadores

Los **comparadores** sirven para determinar la **relación** que hay entre **dos números**. Usaremos dos tipos de comparadores: el de **igualdad** y el **menor que**. Son muy importantes, sobre todo el de igualdad, que nos permite implementar circuitos que realicen una **acción** al recibir un **comando**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Comp-01.png)

Ambos comparadores reciben **dos operandos de n bits** y producen un **bit de salida**. En el de **igualdad**, la salida se pone a **1** si ambos operandos **son iguales** y **0** si son **distintos**. La igualdad es una **operación comutativa**: da igual por donde introduzcamos cada operando

El comparador **menor que** pone a **1** su salida si el **operando a** es **menor** que el **operando b**. En caso de igualdad o que el b sea mayor, se pone a **0**. Esta es una operación **NO conmutativa**, por lo que es **MUY IMPORTANTE** introducir los operandos en el orden correcto

## Ejemplo 4: Comparando números de 3 bits

Para comprobar el funcionamiento de los comparadores, utilizaremos **números de 3 bits**. El **operando a** lo introduciremos en un **registro de 3 bits**, a través de **tres pulsadores externos** y un pulsador de **enter**. El **operando b** estará en un **contador de 3 bits**, que se incrementa con otro **pulsador**. En **dos leds** mostramos las salidas de ambos comparadores: de **igualdad** y **menor que**. El **montaje** es el siguiente:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Comp-02.png)

En el circuito colocamos un **registro** para el **operador a**, y un **contador** para el **operador b**, y conectamos sus salidas a ambos **comparadores**, de **igualdad** y **menor que**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Comp-03.png)

Lo **cargamos** y lo **probamos**. En este **vídeo** lo vemos en acción. Inicialmente los dos operandos son **0**, por lo que se enciende el **LED de igualdad**

[![Click to see the youtube video](http://img.youtube.com/vi/IgIlH-ILyLc/0.jpg)](https://www.youtube.com/watch?v=IgIlH-ILyLc)

Al pulsamos el botón de **incremento** del **operador b**, tenemos que **a = 0** y **b = 1**, por lo que **a < b** y se enciende el **LED rojo** (menor que). Luego introducimos el **número 6** en **a**, y no se enciende ningún LED porque no se cumple ninguna condición. **Incrementamos b** hasta que es **6** y se cumple **a = b**, y volvemos a **incrementar b** para tener otra vez que **a < b** y se encienda el led rojo

## Comparadores de un operando

Muchas veces hay que realizar una **comparación** entre un dato, que varía y una **constante**. Por ejemplo cuando hay que **reconocer un comandos** o un **código**. En estos caso es más fácil crear un **bloque específico** en el que la **constante** se introduce como **parámetro**. Estos comparadores tienen una entrada para el **operando a** y una para el **parámetro k** 

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Comp-04.png)

### Ejemplo 5: Apertura de caja fuerte con código

Reharemos el ejemplo que ya conocemos de la **apertura** de una **caja fuerte** con **código**, pero usando un **comparador de igualdad** con operando y constante. Por los interruptores externos introducimos **el código** y al apretar el pulsador se guardan en un **registro**. Este dato se compara con el **código de apertura** y se mueve el servo que abre la caja fuerte si es correcto. El **escenario** es el siguiente:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Comp-05.png)

El **código de apertura** se configura como **constante** del comparador, que por defecto es **5**. Para modificar el código hay que cambiar esta constante. El código introducido por el usuario se almacena en un **registro de 3 bits** al apretar el **pulsador de ENTER**, y se compara con el **código de apertura**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Comp-06.png)

Lo **cargamos** y lo **probamos**. Primero se introducen los **códigos incorrectos** 1 y 3, y la caja **no** se abre. Luego se mete el  **correcto**: 5 (101 en binario) y se enciende el **LED verde** y se mueve el **servo**. Por último se introduce otro **incorrecto**: 7. Se apaga el LED y se cierra la puerta. Se muestra en este **vídeo**

[![Click to see the youtube video](http://img.youtube.com/vi/8D1HBoAe9CQ/0.jpg)](https://www.youtube.com/watch?v=8D1HBoAe9CQ)

# Aplicaciones

Como ejemplos de dos **circuitos más avanzados** que utilizan **registros** y **comparadores** haremos el **juego de la ruleta**, en el que ganas si al tirar el **spinner** el número que sale es igual al introducido previamente, y un circuito que activa otros circuitos mediante **códigos**

## Ejemplo 6: Juego de la ruleta

Es un **juego de azar**, en el que se gana si el **número** que se obtiene al tirar la ruleta es igual al seleccionado inicialmente. Como usaremos números de 3 bits, se puede elegir cualquier número entre **0** y **7**. El jugador debe seguir los **siguientes pasos**:

1. Inicialmente se enciende el **LED verde** para indicar que el jugador debe introducir por los 3 interruptores el **número elegido.** Estamos en el **modo selección**. Al Apretar el **botón de enter** el número aparecerá en el **display de 7 segmentos**. Esta elección todavía no es definitiva. Se puede volver a seleccionar otro número y apretar enter tantas veces como se quiera

2. Una vez satisfecho con el número, se aprieta el **botón de tirar**. Se apaga el led verde y se enciende el **amarillo**. Estamos en **modo ruleta**. Ahora en el display aparecerá el número actual de la ruleta, que inicialmente es el 0.

3. El jugador **tira la ruleta** (el spiner). En el display aparecerán los números consecutivamente. Cada vez que un brazo del spiner pasa por **sensor de IR** suena un **pitido** y se incrementa el número del display

4. Cuando se **detiene el spiner**, bien se emite un **pitido grave** si el número del display es distinto al seleccionado (el jugador pierde), o bien se activa una **sirena acústica** y **luminosa** para indicar que **ha ganado**

5. Al cabo de unos segundos, el juego vuelve al **estado inicial**, y el circuito entra en el **modo selección**: Se enciende el led verde y se apaga el resto. Volvemos al **punto 1**

El **escenario** se muestra a continuación. Dispone de **3 interruptores** para introducir el número elegido, **dos pulsadores** (enter y tirar), **4 LEDs**, un **zumbador**, un **display de 7 segmentos**, el **sensor IR** y el **spiner** que hace de ruleta

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Comp-07.png)

En este **vídeo** se muestra un ejemplo del funcionamiento. Se introduce el **número 5** y se pulsa **enter**. Luego se da al **botón de tirar** y se dan **vueltas a la ruleta**. Se falla. Luego se repite el proceso con el número 1. Esta segunda vez se hace **trampa** y se detiene la ruleta para ganar y ver lo que ocurre

[![Click to see the youtube video](http://img.youtube.com/vi/yqSDqRtoCkM/0.jpg)](https://www.youtube.com/watch?v=yqSDqRtoCkM)

Visto el funcionamiento y sus partes... ¿Cómo se hace este circuito?

Lo resolveremos por partes, que luego juntaremos. Necesitamos un **biestables RS** para determinar en qué **modo** está el circuito: **modo selección** o **modo ruleta**. La salida la conectamos a los LEDs indicadores: Verde y Amarillo. **Inicialmente** se empieza en **modo selección** y al apretar el **botón de tirar** se cambia a modo ruleta

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Ruleta-01.png)

El **botón de Enter**, para elegir número, **sólo** funciona en el **modo selección**, por lo que colocamos una **AND** de habilitación (y una NOT) para que sólo se propage su tic si estamos en este modo. Y lo mismo con el tic que viene del **IR** de la ruleta: con la AND hacemos que sus tics se habiliten sólo en **modo ruleta**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Ruleta-02.png)

De esta forma, si estamos tirando la ruleta en **modo selección**, no ocurre nada. Y si pulsamos el **botón de enter** en el **modo ruleta**, tampoco ocurrirá nada. No podemos elegir otro número mientras esté en marcha

Por los **tres interruptores** se introduce el **número elegido** y se captura en un **registro de 3 bits** al apretar la **tecla Enter**, si es que estamos en el **modo de selección**. Si no, se ignora la pulsación.

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Ruleta-03.png)

Los **tics** que llegan del **infrarrojo** al tirar la **ruleta**, si estamos en **modo ruleta**, llegan a un **temporizador de 10ms** para generar el **pitido** del movimiento de la ruleta, y de este llegan a la **entrada cnt** de un **contador de 3 bits**, que contiene el **número actual** de la ruleta. Se incrementa con cada paso del brazo del spiner sobre el sensor

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Ruleta-04.png)

El **número elegido** y el **número actual** de la ruleta se llevan a un **comparador** para saber si son iguales o no. Estos números también se muestran por el **display de 7 segmentos**, según el modo en el que estemos: selección o ruleta

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Ruleta-05.png)

Una parte muy importante es saber **cuándo la ruleta está parada**. Usaremos un segundo **biestable RS** para almacenar este estado. Sabemos que está parada si han pasado al menos **2 segundos** desde la recepción del **último tic** del spiner. Cualquier tic que llegue antes de ese tiempo hace que el temporizador se **reinicie** y vuelva a empezar la cuenta. Por ello, sólo cuando el temporizador emite el tic de 2 segundos es porque se ha parado. Mientras esté en movimiento el spiner, no emitirá ningún tic de fin

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Ruleta-06.png)

Ya podemos determinar cuando se ha ganado: si el numero elegido es igual al de la ruleta, y la ruleta está parada, entonces se **ha ganado**. Si los números son diferentes, con la ruleta parada, se **ha perdido**. Con un par de **puertas AND** y una **NOT** obtenemos la señal de acierto y la de fallo

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Ruleta-07.png)

La **señal de acierto** activa la **sirena luminosa** y **la acústica**. El **zumbador** puede emitir 3 sonidos diferentes, según la situación: el sonido del movimiento de la ruleta, la sirena de acierto, y el tono de fallo. Usando la **señal de acierto** y el **estado de la ruleta** configuramos los **multiplexores** para que se escuche el sonido que toque

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Ruleta-08.png)

Para volver al **estado inicial** se genera una **señal de reset**, que inicializa los **dos biestables** del circuito. Al pararse la ruleta se emite un tic que activa otro **temporizador**, durante **3 segundos**, transcurridos los cuales se emite la señal de reset. Adicionalmente se puede hacer un **reset manual**, en cualquier momento, apretando el pulsador SW1

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Ruleta-09.png)

Juntando todos estos circuitos parciales, y reodenando los componentes, obtenemos el **circuito final** que implementa el **juego de la ruleta**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Ruleta-10.png)

## Ejemplo 7: Control por comandos

Haremos una **consola de control**, muy básica, para manejar **tres dispositivos** diferentes: una  **alarma luminosa**, que podemos encender o apagar, una **puerta** accionada por un servo, que también abrimos o cerramos, y un **motor**, que además de encenderlo y apagarlo podemos cambiar su **sentido** de la marcha.

El control de los dispositivos lo hacemos introduciendo un **código**, o comando, a través de la **consola**. Este **código de 3 bits** lo metemos por 3 interruptores y pulsamos la **tecla ENTER**. En el **display** se muestra el último comando introducido. El **montaje** es el siguiente:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Consola-01.png)

El **listado** de todos los **comandos** posibles, junto a sus códigos se muestra en la siguiente **tabla**. En total tenemos **8 comandos**

| Comando | Código | Descripción |
|---------|--------|-------------|
| RESET   | 0      | Apagar todos los dispositivos (volver al estado inicial) |
| AlarmON | 1      | Activar Alarma luminosa |
| AlarmOFF| 2      | Desactivar Alarma luminosa |
| OPEN    | 3      | Abrir la puerta (Se mueve el servo) |
| CLOSE   | 4      | Cerrar la puerta (Se mueve el servo) |
| MotorON | 5      | Encender el motor |
| MotorOFF| 6      | Apagar motor      |
| MotorDIR| 7      | Cambiar el sentido de la marcha del motor |
 
El funcionamiento es simple. Se introduce el **código en binario** y se pulsa **Enter**. En este **vídeo** se muestra un ejemplo en acción. Primero ejecuta el comando **1** para activar la alarma, luego el **3** para **abrir la puerta** y el **5** para encender el **motor**. Cada vez que se ejecuta el **7**, el **sentido de giro** del motor cambia. Con el **4** se **cierra** la puerta y finalmente se ejecuta el **0** para **apagarlo todo** y volver al **estado inicial**

[![Click to see the youtube video](http://img.youtube.com/vi/sSQvioiuxYY/0.jpg)](https://www.youtube.com/watch?v=sSQvioiuxYY)

¿Cómo se hace este circuito?

Lo haremos por partes y luego lo unimos todo. Empezamos por la parte que ya conocemos y que hemos usado en los circuitos anteriores: **la consola**. El valor de los **3 interruptores externos** se captura en el **registro de comando** al apretar la **tecla ENTER** y se muestra su valor en el **display de 7 segmentos**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Consola-02.png)

Ahora añadimos los comandos. Comenzamos con la alarma. Usamos un **biestable RS** para almacenar su **estado**: 0-apagada, 1-activada. Su salida está conectada directamente al bloque de la alarma. Mediante un **comparador de un operando** determinamos si el **comando actual** tiene el **código 1** (AlarmaON). Su salida se conecta directamente a la entrada **set** del biestable RS. Con cualquier otro código no se activa el comparador y la alarma permanece en el mismo estado

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Consola-03.png)

El **comando de apagado** de la alarma se implementa con el **mismo esquema**. Se usa un **comparador** para saber si el comando introducido es el de **código 2** (AlarmOFF). Su salida se conecta a la **entrada de reset** del **biestable de estado**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Consola-04.png)

Este **mismo esquema** lo usamos con el **dispositivo 2**: La puerta. Un **biestable de estado** para almacenar si está abierta o cerrada y **dos comparadores** para los comandos de abrir y cerrar, cuyos códigos son  **3** y **4**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Consola-05.png)

Y otra vez lo mismo para el **Dispositivo 3**: el Motor. Los códigos de activación y desactivación son **5** y **6** respectivamente

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Consola-06.png)

El comando 7 es diferente. Cada vez que se introduce, el motor **cambia de sentido**. Por ello, usamos un **biestable de cambio**, en vez de uno RS, que se conecta a la **entrada de dirección** del bloque del motor. Además necesitamos un **tic** para hacer el cambio. Usamos el propio botón de enter. Así, el cambio de sentido se producirá cuando se haya introducido el código 7 y llegue un **tic de enter**.

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Consola-07.png)

El **tic del pulsador** no se conecta directamente al biestable de cambio, sino que se pasa por un **biestable D del sistema** para que llegue a la vez que el código del comando. Si no se hiciera, llegaría antes el tic que el omando, y no funcionaría

El último comando es el de **RESET**, que pone **todos los biestables a 0**. Lo implementamos con un **comparador** para el **código 0** y la salida la llevamos a la **entrada reset** de todos los biestables, a través de una **puerta OR**. Cada dispositivo se pone a 0 bien porque recibe su comando de OFF particular o el RESET

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Consola-08.png)

Ponemos **todas las partes juntas** y tenemos el **circuito final**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Consola-09.png)

# Comunicando la FPGA con un Arduino

Una de las **aplicaciones de las FPGAs** es crear **periféricos** o **controladores** para usarlos desde un **microprocesador**, como por ejemplo **Arduino**. En la FPGA hacemos la **parte física**, con **pensamiento hardware**, mientras que en el **Arduino** la parte de programación, con **pensamiento computacional**, mezclando de esta forma el **diseño hardware** con el **software**

Una forma sencilla de empezar es usando **comunicaciones serie síncronas** entre el **Arduino** y la **FPGA**, donde los **bits** de transmiten uno detrás de otro el **cable de datos** (un cable por sentido), en los instantes indicados por una **señal de reloj**. Usaremos además un **cable de control** para indicar el **fin de la transferencia**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Arduino-01.png)

El **Arduino** es el **Máster**: es el que genera la **señal de reloj** y el que toma la **iniciativa** en la comunicación, tanto para enviar como para recibir. La **FPGA** es la **esclava**. Este tipo de comunicación se llama **maestro-esclavo**, y es el esquema usado en los buses como el [SPI](https://es.wikipedia.org/wiki/Serial_Peripheral_Interface) o [i2c](https://es.wikipedia.org/wiki/I%C2%B2C)

Aunque el Arduino incorpora **hardware específico** para realizar esta comunicación, en los ejemplos de este tutorial lo haremos por **todo por software**, para comprender mejor el funcionamiento. Primero aprenderemos a enviar datos desde el Arduino a la FPGA (escritura), y luego de la FPGA al arduino (lectura) 

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Arduino-02.png)

Usaremos números de **8 bits** (bytes) como **unidades de comunicación**, aunque podríamos usarlos de cualquier otra longitud. También estableceremos el **convenio** de enviar **primero el bit más significativo** y el **último** el de **menor peso**, en ambos sentidos de comunicación

## Comunicación Arduino -> FPGA (Escritura)

La operación de **enviar datos** desde el Arduino a la FPGA lo llamaremos **escritura**. Utilizaremos **tres cables**: el que lleva los **datos** del arduino a la FPGA (verde), el que lleva la señal de **reloj** (gris) y la señal de **control** (amarillo). Además hay que conectar las **masas** (GND) de ambas placas (negro)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Arduino-03.png)

En esta **tabla** se muestran **los pines** usados para las conexiones de los cables de los ejemplos que usaremos

| Pin Arduino  |  Pin Alhambra | Descripción  |
|--------------|---------------|--------------|
|  D12         |   D12         | Reloj        |
|  D11         |   D11         | Datos        |
|  D10         |   D10         | Control      |
|  GND         |   GND         | Masa         |

La **recepción de los datos serie** se hace usando un **registro de desplazamiento** de 8 bits. El cable de **datos** se conecta a la entrada **sin** y la **señal de reloj** (clk) a la de desplazamiento

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Arduino-04.png)

Durante la **recepción del dato**, el registro se va desplazando y en su salida aparecen **valores temporales** que **NO** son el dato final. Por ello, colocamos un **registro adicional** que capture el **dato final**, cuando se haya recibido completamente. La **orden de captura** es la que llega por el **cable de control**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Arduino-05.png)

### Circuito sincronizador

Todas las señales que llegan desde el **exterior de la FPGA** tiene que pasar por un **circuito sincronizador**, que tiene este aspecto en Icestudio, y que se encuentra en el menú **Varios/Entradas/Sync** de la **colección 29**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Arduino-06.png)

El sincronizador está formado por **dos biestables D** en **cascada** cuya misión es minimizar los **problemas de metaestabilidad** que suceden cuando la señal exterior cambia en el **mismo instante** que el **flanco de reloj del sistema** de la FPGA. En esos casos, el dato capturado **no** es ni **uno** ni **cero**. Se puede encontrar **más información** sobre este problema en esta entrada de la wikipedia: [Metaestabilidad en electrónica digital](https://es.wikipedia.org/wiki/Metaestabilidad#En_electr%C3%B3nica_digital)

### Receptor serie síncrono

Nuestro **receptor serie síncrono genérico**, está formado por las **tres señales** de entrada: **datos**, **reloj** y **control**, que pasan por su respectivos sincronizadores. Además tenemos el **registro de desplazamiento** para convertir el dato seria a paralelo y el **registro de datos** que contiene el **dato final recibido**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Arduino-07.png)

Las **señales** de **reloj** y **control** las **convertimos en tics**, mediante un conversor de flancos de subida en tics, para poder introducirlas en las entradas de **shift** y **load** de los registros de **desplazamiento** y **datos** respectivamente

El **arduino** cada vez que realiza una **operación de escritura** sobre la **FPGA** está almacenando un dato de 8 bits en este **registro de datos**. Según el circuito que se esté implementando, este dato recibido se usará con un fin u otro

Para realizar esta **escritura**, el Arduino (software) tiene que realizar **estas operaciones**:
* Inicialmente las señales de **reloj** y **control** deben estar a **0**
* **Enviar el dato en seríe**, empezando por el **bit más significativo**. Por cada bit enviado debe generar un **pulso** en la señal de **reloj** (escritura de un 1, seguida de un 0)
* Una vez enviado el **octavo bit**, se debe generar otro **pulso** en la **señal de control** (un 1 y luego un 0) para que el dato se **capture** en el **registro de datos**

### Software para escritura

Para realizar la **escritura** desde el **Arduino** a la **FPGA** implementamos la función **fpga_write()**, que envía el dato pasado como parámetro. Se implementa de forma muy fácil usando la función [shiftOut](https://www.arduino.cc/reference/en/language/functions/advanced-io/shiftout/) de la **biblioteca de Arduino**

```C
void fpga_write(int value) {
  shiftOut(DAT, CLK, MSBFIRST, value);
  digitalWrite(CTRL, HIGH);
  digitalWrite(CTRL, LOW);
}
```

La función **shiftOut()** envía datos de **8 bits** de una vez. Con la constante **MSBFIRST** se indica que envíe primero **el bit de mayor peso** (que es como lo tenemos configurado en el hardware). Las constantes **CLK**, **DAT** y **CTRL** son los **pines** de arduino por donde sacar las señales de **reloj**, **datos** y **control** respectivamente

Las señales de **reloj** y **datos** las controla la propia función **shiftOut**. Una vez que se ha enviado el dato, se emite el pulso en la **señal de control** para que se captura en el **registro de datos**. Este pulso lo emitimos nosotros, desde la función **fpga_write()**

### Ejemplo 8: Implementación de un puerto de salida adicional para el Arduino

Como ejemplo de escritura de un dato desde el **Arduino** a la FPGA, vamos a **aumentar las salidas** de nuestro Arduino usando un **puerto de 8 bits** en la FPGA. Es el mismo ejemplo usado en este tutorial de **Programarfacil.com**: [Aumentar salidas digitales de Arduino con el shift register](https://programarfacil.com/blog/aumentar-salidas-digitales-de-arduino-con-el-shift-register/), pero usando la **FPGA** en vez de un registro de deplazamiento discreto

El **montaje** es el siguiente. Tenemos un **Arduino Uno** conectado a una **Icezum Alhambra**, mediante **4 cables**: reloj, datos, control y GND. Ambas placas están conectas ordenador a través del USB, para cargar el **software** en el **Arduino** y el **hardware** en la **Alhambra**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Arduino-08.png)

El **conexionado** entre el **Arduino Uno** y la **Icezum Alhambra** se resume en esta **tabla**

| Pin Arduino  |  Pin Alhambra | Descripción  |
|--------------|---------------|--------------|
|  D12         |   D12         | Reloj        |
|  D11         |   D11         | Datos        |
|  D10         |   D10         | Control      |
|  GND         |   GND         | Masa         |

La **implementación del circuito** usa el **receptor serie síncrono** genérico, al que se le ha conectando la salida del **registro de datos** a los **LEDs** de la Alhambra, para ver el **dato recibido**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Arduino-09.png)

En el **Arduino** cargamos un **programa de pruebas**, que por ejemplo escriba los datos **0x55** y **0xAA** cada medio segundo. Primero se **configuran** los pines a usar. El **pin de control** se pone a **0**. En el bucle principal se envían los dos valores. El programa se puede **descargar** de aquí: [Puerto-secuencia.ino](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Arduino/Puerto-secuencia/Puerto-secuencia.ino)

```C
const int LED = 13;  //-- LED de Arduino
const int CLK = 12;  //-- Pin de reloj
const int DAT = 11;  //-- Pin de Datos
const int CTRL = 10; //-- Pin de control

void setup() {
  pinMode(LED, OUTPUT);
  pinMode(CLK, OUTPUT);
  pinMode(DAT, OUTPUT);
  pinMode(CTRL, OUTPUT);
  digitalWrite(CTRL, LOW);
  digitalWrite(LED, LOW);
}

void fpga_write(int value) {
 shiftOut(DAT, CLK, MSBFIRST, value);
 digitalWrite(CTRL, HIGH);
 digitalWrite(CTRL, LOW);
}

void loop() {
   fpga_write(0x55);
   delay(500);
   fpga_write(0xAA);
   delay(500);
}
```

Para probarlo, cargamos el **hardware** en la **Alhambra**, desde Icestudio, y el **software** en **Arduino**, desde el **IDE** de Arduino. En este **vídeo** lo vemos en acción. Los valores escritos por el Arduino aparecen en los **LEDs**. La secuencia se detiene en cualquiera de los siguientes casos: **reset** de la FPGA, de Arduino o si **desconectamos** uno de los cables

[![Click to see the youtube video](http://img.youtube.com/vi/yVoYMbUsWjs/0.jpg)](https://www.youtube.com/watch?v=yVoYMbUsWjs)

**¡Bienvenidos al mundo del codiseño Hardware/Software!** Ahora podemos tocar ambos mundos fácilmente. En la pantalla de la izquierda tengo **Icestudio**, para hacer **actualizaciones del hardware**. En la derecha el **Arduino IDE**, para **modificar el software**. Ambos los actualizamos en segundos, y en el orden que queramos

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Arduino-10.png)


## Comunicación FPGA -> Arduino (Lectura)

La operación de **recibir datos** en el **Arduino** desde la **FPGA** lo llamaremos **lectura**. Igual que para la escritura, Utilizaremos tres cables: **reloj**, **control** y **datos**. La diferencia está en que el **cable de datos** transmite la información en el **sentido FPGA -> Arduino**. Para diferenciarlo del otro sentido (Arduino -> FPGA) usaremos el **color azúl**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Arduino-11.png)

En esta **tabla** se muestran los **pines usados** para las conexiones de los cables de los ejemplos que veremos

| Pin Arduino  |  Pin Alhambra | Descripción  |
|--------------|---------------|--------------|
|  D12         |   D12         | Reloj        |
|  D10         |   D10         | Control      |
|  D9          |   D9          | Datos        |
|  GND         |   GND         | Masa         |

La transmisión de los datos desde la FPGA se hace usando un **registro de desplazamiento** de 8 bits. El cable de **datos** se conecta a la salida serie **so**, la señal de **reloj** (clk) a la de desplazamiento (shift) y la señal de **control** a la de carga paralela. El **dato de 8 bits** se introduce por la **entrada paralela d** del registro
 
![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Arduino-12.png)

### Transmisor serie síncrono

Nuestro **transmisor serie síncrono genérico** está formado por dos señales de entrada: **reloj** y **control**, que pasan por su respectivos **sincronizadores** y llegan al **registro de desplazamiento**, que convierte el dato a enviar de **paralelo** a **serie**. El dato se envía por la **salida seríe** so, y pasa por un **biestable D** del sistema para eliminar los espúreos (glitches) y cumplir con las [reglas del diseño síncrono](https://github.com/Obijuan/open-fpga-verilog-tutorial/wiki/Cap%C3%ADtulo-22:-Reglas-de-dise%C3%B1o-s%C3%ADncrono)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Arduino-13.png)

El **dato a enviar** normalmente estará almacenado en un **registro**, que llamaremos **registro de datos**, pero podría venir de cualquier otro lugar: una memoria, un contador, etc, por eso no se ha incluido en el esquema genérico

Para realizar la **lectura**, el **Arduino** (software) tiene que realizar estas **operaciones**:
* Inicialmente las señales de **reloj** y **control** deben estar a **0**
* Envíar un **pulso** por la **señal de control**, para que la FPGA **capture** el dato a enviar
* **Recibir** el dato en serie, empezando por el bit más significativo. Cada vez que lee un bit debe segenera un pulso en la señal de reloj
* Al cabo de **8 pulsos de reloj** ya tiene el dato completo

### Software para lectura

Para realizar la lectura de la **FPGA** desde el **Arduino** implementamos la función **fpga_read()**, que devuelve el **dato recibido**. Se implementa de forma muy fácil usando la función [shiftIn](https://www.arduino.cc/reference/en/language/functions/advanced-io/shiftin/) de la biblioteca de Arduino

```c
byte fpga_read() {
  byte c;

  //-- Indicar a la FPGA que capture el dato
  digitalWrite(CTRL, HIGH);
  digitalWrite(CTRL, LOW);

  //-- Recibir el dato
  c =  shiftIn(DAT, CLK, MSBFIRST);
  return c;
}
```

La función **shiftIn()** recibe un **dato de 8 bits** de una vez. Con la constante **MSBFIRST** se indica que recibe primero el bit de mayor peso (que es como lo tenemos configurado en el hardware). Las constantes **CLK**, **CTRL** y **DAT** son los pines de arduino por donde sacar las señales de reloj y control, y el pin por donde se reciben los datos respectivamente

La **señal de reloj** la controla la propia función **shiftIn**. Antes de invocarla es necesario generar un **pulso** en la señal de control para que la **FPGA** capture el dato. Lo emitimos nosotros al comienzo de la función **fpga_read()**

### Ejemplo 9: Implementación de un puerto de entrada adicional para el Arduino

Como ejemplo de **lectura** de un dato de la FPGA desde el Arduino, vamos a implementar un **puerto de entrada** adicional de **8 bits**. En los bits menos significativos de este puerto conectaremos **tres interruptores**, y desde el Arduino leeremos sus valores

El **montaje** es el siguiente. Tenemos un **Arduino Uno** conectado a una **Icezum Alhambra**, mediante **4 cables**: reloj, datos, control y GND. Ambas placas están conectas ordenador a través del USB, para cargar el **software** en el Arduino y el **hardware** en la Alhambra

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Arduino-14.png)

Por los **3 pulsadores** se introduce un valor y se pulsa el **botón de ENTER** para capturarlo. Su valor se muestra en el **display de 7 segmentos**. Ese será el valor que **lea** el arduino, que mostrará por la **consola serie** 

La **implementación** del circuito usa el **transmisor serie síncrono genérico**, al que se le ha conectado por su entrada paralela el **registro de datos** que contiene el número introducido por los interruptores. Este registro es el que se muestra por el **display de 7 segmentos**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Arduino-15.png)

El **registro de desplazamiento** es de **8 bits**, mientras que el **registro de datos** es de **3 bits**. Por eso se usa un elemento acoplador para conectarlos, que simplemente añade ceros en los bits de mayor peso del registro de datos. Este elemento se encuentra en el menú **Varios/Bus/3-bits/Acoplador-3-8**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Arduino-16.png)

En el **Arduino** cargamos un **programa de pruebas** que lee constantemente el registro de datos, y si detecta algún cambio, muestra el número por la **consola serie**. El **programa completo** se puede **descargar** de aquí: [Puerto-entrada.ino](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-29/Arduino/Puerto-entrada/Puerto-entrada.ino) y se muestra a continuación:

```C
const int LED = 13;
const int CLK = 12;  //-- Pin de reloj
const int DAT = 9;   //-- Pin de Datos
const int CTRL = 10; //-- Pin de control

void setup() {
  pinMode(LED, OUTPUT);
  pinMode(CLK, OUTPUT);
  pinMode(DAT, INPUT);
  pinMode(CTRL, OUTPUT);
  digitalWrite(CTRL, LOW);
  digitalWrite(CLK, LOW);
  digitalWrite(LED,LOW);
  Serial.begin(9600);
}

byte fpga_read() {
  byte c;

  //-- Indicar a la FPGA que capture el dato
  digitalWrite(CTRL, HIGH);
  digitalWrite(CTRL, LOW);

  //-- Recibir el dato
  c =  shiftIn(DAT, CLK, MSBFIRST);
  return c;
}

void loop() {
  byte dat;
  byte old = 0xff;

  //-- Leer el puerto constantemente
  while(1) {

    //-- Leer dato de la FPGA
    dat = fpga_read();

    //-- Si ha habido un cambio desde la última
    //-- lectura, mostrarlo en la consola
    if (dat != old) {
      Serial.write(dat+'0');
      Serial.write("\n");
    }  

    //-- Almacenar dato leido para saber
    //-- si hay cambios
    old = dat;  
  }
}
```

En el **bucle principal** se lee el dato en la variable **dat**, y en **old** se encuentra el valor leido **anteriormente**. Si son diferentes, se que ha habido un cambio con respecto a la lectura anterior, por lo que se imprime el número. Para pasar de binario a ASCII sólo hay que sumar el carácter '0': Serial.write(dat+'0');

Para probarlo, cargamos el **hardware** en la Alhambra, desde Icestudio, y el **software** en Arduino, desde el IDE de Arduino. En este **vídeo** lo vemos en acción. Los números introducidos en los switches se muestra en la **consola serie** del Arduino al apretar el **botón de Enter**

[![Click to see the youtube video](http://img.youtube.com/vi/4RLs7_NhUtE/0.jpg)](https://www.youtube.com/watch?v=4RLs7_NhUtE)

(Foto codiseño)

# Ejercicios propuestos (20 BitPoints)

Ver los detalles de los ejercicios y las **entregas** en el menú **Archivos/Ejemplos/2-Ejercicios** de la colección de este tutorial

**Resumen**:

* **Ejercicio 29.1** (Total **x Bitpoints**): 

* **Ejercicio 29.2** (Total **x Bitpoints**): 

* **Ejercicio 29.3** (Total **x Bitpoints**): 

* **Ejercicio 29.4** (**5 Bitpoints**). Ejercicio Libre. Premiar la creatividad. **Entregar** por redes sociales o github: Pantallazos, enlaces, vídeos, etc...

# Ejercicios entregados

## Primero

### Ejercicio 29.1
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 29.2
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 29.3
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 29.4
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()


## Segundo

### Ejercicio 29.1
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 29.2
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 29.3
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 29.4
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

## Tercero

### Ejercicio 29.1
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 29.2
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 29.3
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 29.4
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

