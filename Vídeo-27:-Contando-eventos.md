![]()

# Vídeo

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

Haz click en la imagen para ver el **vídeo en Youtube**

# Descripción
(TODO)

# ¡Icestudio 0.3.3!

Este tutorial está hecho con la versión [0.3.3 de Icestudio](https://github.com/FPGAwars/icestudio/releases/tag/v0.3.3). Asegúrate de tener instalada esta versión (o superior)

# Colección

**Academia-Jedi-HW-27.zip**: Colección para este tutorial. Descargar e instalar 

# Contenido

* [Contadores](#contadores)
* [Contando tics](#contando-tics)
  * [Ejemplo 1: Contando las pulsaciones de un botón](#ejemplo-1-contando-las-pulsaciones-de-un-bot%C3%B3n)
  * [Ejemplo 2: Inicializando el contador](#ejemplo-2-inicializando-el-contador)
  * [Ejemplo 3: Contando en decimal](#ejemplo-3-contando-en-decimal)
  * [Ejemplo 4: Notificando el overflow](#ejemplo-4-notificando-el-overflow)
  * [Ejemplo 5: Cambiando el módulo del contador](#ejemplo-5-cambiando-el-m%C3%B3dulo-del-contador)
  * [Ejemplo 6: Contador de 0 a 9](#ejemplo-6-contador-de-0-a-9)
* [Encadenando contadores](#encadenando-contadores)
  * [Ejemplo 7: Dos contadores de 2-bits encadenados](#ejemplo-7-dos-contadores-de-2-bits-encadenados)
  * [Ejemplo 8: Contador hexadecimal de 4 bits, encadenando dos de 2-bits](#ejemplo-8-contador-hexadecimal-de-4-bits-encadenando-dos-de-2-bits)
  * [Ejemplo 9: Contando pulsaciones triples (triple clicks)](#ejemplo-9-contando-pulsaciones-triples-triple-clicks)
* [Contando objetos](#contando-objetos)
  * [Ejemplo 10: Escáner de supermercado. Contando los artículos comprados](#ejemplo-10-esc%C3%A1ner-de-supermercado-contando-los-art%C3%ADculos-comprados)
  * [Detectando el movimiento de spinners](#detectando-el-movimiento-de-spinners)
  * [Ejemplo 11: Contando las vueltas de un spiner](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-27:-Contando-eventos#ejemplo-11-contando-las-vueltas-de-un-spiner)
* [Contando tiempo](#contando-tiempo)
  * [Ejemplo 12: segundero](#ejemplo-12-segundero)
  * [Ejemplo 13: Cronómetro básico](#ejemplo-13-cron%C3%B3metro-b%C3%A1sico)
* Ejercicios propuestos (X Bitpoints)
* [Ejercicios entregados](#ejercicios-entregados)
* [Autor](#autor)
* [Licencia](#licencia)
* [Enlaces](#enlaces)
* [Preguntas frecuentes](#preguntas-frecuentes)

# Contadores

Los **contadores** son unos componentes **esenciales**, que se utilizan muchísimo. Con ellos hacemos otros elementos, como **temporizadores**, **unidades de PWM**, **controladores**... y también nos permiten **direccionar memorias** o **recorrer tablas**, entre otras muchas cosas

Los contadores **cuentan tics**. Existen de muchos tipos. Los que nosotros utilizaremos en este tutorial son **contadores ascendentes**, que parten desde **cero** y suman **una unidad** a la cuenta cada vez que llega un tic. Este es el **bloque** que utilizaremos

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/counter-01.png)

Por la entrada **cnt**, llegan los **tics** que queremos contar. La cuenta actual sale por el **bus** de la derecha, de **N** bits. Por la **salida ov** se emite un tic para indicar un **evento de desbordamiento**: el contador ha llegado a la **cuenta máxima** y comienza desde cero. Con la **entrada rst** ponemos el contador otra vez a 0. 

Como **parámetro** se introduce el **módulo del contador**: la cuenta máxima, que una vez alcanzada hace que vuelva a comenzar desde cero (provocando un overflow). Si no se indica ninguno, se toma el **su valor máximo** (2 elevado al número de bits del contador)

En esta **animación** se mustra el funcionamiento de un **contador de 2 bits**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/counter-02.gif)

# Contando tics

Los **contadores** cuentan los **tics** que reciben por su *entrada cnt**. Nos familiarizaremos con ellos usando como ejemplo el contador más sencillo: uno de **2 bits**, como el de la animación anterior. Realiza la cuenta 0,1,2,3 y en el cuarto tic vuelve a comenzar desde 0

## Ejemplo 1: Contando las pulsaciones de un botón

Comenzamos con un ejemplo de **contar** las veces que **apretamos un pulsador**, y mostramos la cuenta en **2 LEDs** externos. La entrada de **reset** la dejamos a 0. El **circuito** es el siguiente:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/counter-03.png)

Y el **montaje** se muestra en esta foto. El LED **amarillo** es el de menor peso (LED 0), y el **rojo** el de mayor (LED 1)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/counter-04.png)

Lo **cargamos** y lo **probamos**. ¡Nuestro primer contador está funcionando!. Efectivamente, al apretarse la cuarta vez, el contador vuelve a 0

[![Click to see the youtube video](http://img.youtube.com/vi/3W57NzJkwHo/0.jpg)](https://www.youtube.com/watch?v=3W57NzJkwHo)

## Ejemplo 2: Inicializando el contador

El contador **comienza a contar** desde **0**. Es el valor que tiene al alimentar el circuito. A partir de ahí, su valor dependerá de los **tics** que se hayan recibido por su **entrada cnt**. Si en un momento determinado queremos que vuelva a su valor inicial de 0, hay que poner a **1** su **entrada rst**

Este ejemplo es igual que el anterior, pero hemos conectado la entrada **rst** al **pulsador SW1**. De esta forma, cuando se **apriete**, enviará un 1 y el contador se **inicializará**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/counter-05.png)

Lo **cargamos** y lo **probamos**. En cuanto se aprieta el **reset**, la cuenta se pone a **0** y los LEDs se apagan

[![Click to see the youtube video](http://img.youtube.com/vi/SdsyM3bqprc/0.jpg)](https://www.youtube.com/watch?v=SdsyM3bqprc)

## Ejemplo 3: Contando en decimal

Si conectamos un **decodificador** para **display de 7 segmentos** a la salida del contador, veremos la cuenta en **dígitos decimales**, lo cual es mucho más fácil de leer :-) Usamos el **DisplayBit2**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/counter-06.png)

El **montaje** es el mismo de los ejemplos anteriores, pero añadiendo el **display de 7 segmentos**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/counter-07.png)

Lo **cargamos** y lo **probamos**. Ahora se ven los **dígitos 0**, **1**, **2** y **3** al **apretar** el pulsador sucesivamente.  También vemos la **cuenta en binario** en los LEDs inferiores. Al apretar el **reset** vuelve a **0**.

[![Click to see the youtube video](http://img.youtube.com/vi/3HFkcehVeyM/0.jpg)](https://www.youtube.com/watch?v=3HFkcehVeyM)

### Ejemplo 4: Notificando el overflow

Cada vez que el **contador da la vuelta** y comienza de desde **cero**, se emite el **evento de overflow**, que es un **tic**. Lo podemos capturar con un **biestable RS** y notificarlo en un **LED**. Este es el **circuito**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/counter-08.png)

Se ha añadido un **pulsador** para **borrar la notificación**. El **LED rojo** se usa para mostrar la **notifición**. El resto del **montaje** es **igual** que el del ejemplo 3

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/counter-09.png)

Lo **cargamos** y lo **probamos**. El desbordamiento se produce cuando el contador vale 3 y se aprieta el pulsador. En ese momento se **activa el LED** y el contador pasa a valer **0**. O lo que es lo mismo, el LED se enciende cuando se ha **pulsado 4 veces** el botón, partiendo del estado de reposo (0)

[![Click to see the youtube video](http://img.youtube.com/vi/AQFVeJZapBg/0.jpg)](https://www.youtube.com/watch?v=AQFVeJZapBg)

### Ejemplo 5: Cambiando el módulo del contador

El contador que hemos usado en todos los ejemplos es de **2 bits**. Esto significa que **sólo puede representar 4 números** (2 elevado a 2): 0, 1, 2 y 3. Al recibir el cuarto tic vuelve a comenzar desde cero. Se trata de lo que llamamos un contador **módulo 4**: sólo puede contar como máximo 4 tics (y vuelve a empezar)

El **módulo del contador** lo podemos **cambiar** con el **parámetro** superior. En este ejemplo se muestra el mismo circuito del ejemplo 4, pero se ha cambiado el módulo para que sea 3. Es un **contador módulo 3**. Por ello ahora sólo cuenta 3 tics, y vuelve a comenzar. La cuenta que hace es: 0,1 y 2.

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/counter-10.png)

Lo **cargamos** y lo **probamos**. Comprobamos que ahora efectivamente el contador llega hasta 2 y con la siguiente pulsación vuelve a 0 y se activa la **notificación de desbordamiento**

[![Click to see the youtube video](http://img.youtube.com/vi/Bf8JTTj89E8/0.jpg)](https://www.youtube.com/watch?v=Bf8JTTj89E8)

## Ejemplo 6: Contador de 0 a 9
 
Ya conocemos todos los secretos de los contadores. Ahora los aplicaremos para hacer más ejemplos. ¿Cómo podemos hacer un contador que cuente en **decimal**, desde el **0** hasta el **9** y vuelva a empezar?

Para representar los números del 0 al 9 (10 en total), necesitamos usar un **contador de 4 bits**. Como queremos que la cuenta sea del **0** al **9**, el contador será **módulo 10**. Partimos del ejemplo anterior y cambiamos el **decodificador del 7 segmentos**, el contador y el módulo:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/counter-11.png)

Lo **cargamos** y lo **probamos**. Ahora cuenta desde el **0** hasta el **9**. Y al apretar el pulsador por **décima vez** vuelve a 0 y se activa la **notificación de desbordamiento**

[![Click to see the youtube video](http://img.youtube.com/vi/_5SDIPNTLAo/0.jpg)](https://www.youtube.com/watch?v=_5SDIPNTLAo)

# Encadenando contadores

Los **contadores** los podemos considerar también como **componentes generadores de tics**, que los emiten por su salida de **overflow** (ov). Esto permite conectar la salida de overflow de un **contador fuente** a la entrada **cnt** del **contador destino**. Cada vez que el **contador fuente** se desborde, el **contador destino** se incrementa

En esta **animación** se muestra un ejemplo de **dos contadores** de 2 bits **encadenados**. El **contador fuente** se va incrementando cada vez que llegan tics (no se muestran en la animación). Al desbordarse **emite un tic** que incrementa el **contador destino**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/encadenamiento-01.gif)

A su vez, el **contador destino** emite otro **tic de overflow** al llegar a 4. Esto permite **encadenarlo** con otro **elemento**

## Ejemplo 7: Dos contadores de 2-bits encadenados

En este ejemplo **encadenamos** dos **contadores** de **2-bits**, igual que en la animación anterior. El **contador 1** muestra su cuenta en **binario**, en dos LEDs mientras que el **contador 2** lo hace en un **display de 7 segmentos**. Cada vez que el contador 1 cuenta 4 pulsaciones de botón, se incrementa el contador 2

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/encadenamiento-02.png)

En el montaje se incluyen los **dos LEDs** para mostrar la **cuenta binaria** del **contador 1**, el **pulsador** para emitir tics, y el **display de 7 segmentos** para mostrar la cuenta del **contador 2**, en decimal

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/encadenamiento-03.png)

Lo **cargamos** y lo **probamos**. En este **vídeo de youtube** se muestra su funcionamiento:

[![Click to see the youtube video](http://img.youtube.com/vi/f75ZNZluRVk/0.jpg)](https://www.youtube.com/watch?v=f75ZNZluRVk)

## Ejemplo 8: Contador hexadecimal de 4 bits, encadenando dos de 2 bits

El **encadenamiento** de contadores lo podemos usar para crear un **contador de mayor número de bits**. Como ejemplo, vamos a crear un **contador hexadecimal**, de **4 bits**, a partir de **dos contadores** de 2 bits

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/encadenamiento-04.png)

La **salida ov** del **contador 1** la unimos a la **entrada cnt** del **contador 2**. Concatenamos las salidas de ambos contadores, siendo la del **contador 1** la de **menor peso**. Estos **4 bits** los llevamos al **decodificador de 7 segmentos hexadecimal**. La salida del contador 1, además, la mostramos en dos LEDs

Lo **cargamos** y lo **probamos**:

[![Click to see the youtube video](http://img.youtube.com/vi/ZL3HTtCnvHQ/0.jpg)](https://www.youtube.com/watch?v=ZL3HTtCnvHQ)

Se podría haber hecho lo mismo usando directamente un **contador de 4 bits**. Sin embargo, es útil usar la concatenación para construir otros contadores que no estén disponibles, así como usar la **señal de overflow** del contador de menor peso para activar alarmas, señales o comunicarse con otros circuitos

## Ejemplo 9: Contando pulsaciones triples (triple clicks)

El encadenamiento de contadores es muy útil para contar **grupos de eventos**. Por ejemplo, hacer un contador de **triples clicks**. Cada vez que se aprieta el pulsador **tres veces**, se **incrementa** el contador. 

Configuramos el primer contador para contar los **elementos del grupo**, cambiando su módulo. Para contar tres pulsaciones usaremos un **contador de 2 bits con módulo 3**. Ahora lo **encadenamos** con el **segundo contador**. Usaremos uno de **3 bits**, que nos permitirá contar hasta 8 (dígitos del 0 al 7)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/encadenamiento-05.png)

Lo **cargamos** y lo **probamos**

[![Click to see the youtube video](http://img.youtube.com/vi/WVu6E8bI4KM/0.jpg)](https://www.youtube.com/watch?v=WVu6E8bI4KM)

Sólo con cambiar el **módulo** del **primer contador**, cambiamos la candidad de clicks a contar: dos, tres, cuatro... Es decir, **el módulo del contador 1** determina el **tamaño del grupo**

# Contando objetos

Si los tics provienen de un **sensor externo**, como por ejemplo un **sensor de infrarrojos** (IR), podemos usar los **contadores** para contar el **número de objetos detectados**. Por ejemplo, contar el **número de artículos comprados** en un **supermercado**, al pasarlos por el **escáner** (de juguete), o el **número de vueltas** que da un **spinner**

## Ejemplo 10: Escáner de supermercado: contando los artículos comprados

Construiremos un escáner, para jugar a los **supermercados**. Cada vez que se pasa un objeto sobre este escáner, se emite un **pitido** y se **incrementa** el **contador de artículos**, mostrádolo en un **display de 7 segmentos**. El escenario es este:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/encadenamiento-06.png)

Usaremos un **contador de 3 bits**, por lo que sólo podemos contar hasta **8 objetos**. El **tic** recibido al **detecta**r un objeto se usa para activar un **timer** y generar el **pitido** y **activar el LED**. Su tic de salida lo introducimos en la **entrada cnt** del contador, para incrementarlo

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/IR-01.png)

El pitido tiene una duración de **100ms**. El pulsador externo se usa para la puesta a 0 del contador (reset). **Cargamos** el circuito y lo **probamos**. Pasamos los objetos por encima del sensor para ver cómo las cuenta. **¡Es adictivo!**

[![Click to see the youtube video](http://img.youtube.com/vi/X4lc718gB64/0.jpg)](https://www.youtube.com/watch?v=X4lc718gB64)

## Detectando el movimiento de spinners

Los [Spinners](https://es.wikipedia.org/wiki/Fidget_spinner) son unos juguetes que tienen **3 brazos** que giran alrededor de un centro. Son muy populares entre los niños. Los usaremos, en combinación con los **sensores de IR** para **detectar su movimiento**.

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/IR-03.png)

El montaje es el siguiente: colocamos el **sensor de infrarrojos** de forma que los **brazos del spinner** pasen por encima al girar. En nuestros circuitos colocamos el **componente IR-tic** para que **genere un tic** cada vez que el sensor detecta un brazo. En esta **animación** lo vemos en funcionamiento: 

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/IR-02.gif)

Cada vez que un brazo pasa por encima del sensor, se **emite un tic**. Como el spinner tiene **3 brazos**, sabremos que **ha dado una vuelta completa** cada vez que se reciban **3 tics**. Ya sabemos **detectar 3 tics**: basta con poner un **contador módulo 3**, que emitirá un tic cada vez que reciba **3** por su entrada

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/IR-04.gif)

Este es nuestro **circuito detector de vueltas del spinner**. Cada vez que el contador módulo 3 emite un **tic de overflow** significa que **el spinner ha dado una vuelta**. Ahora sólo hay que **encadenarlo** con otro contador para contar el número de vueltas

## Ejemplo 11: Contando las vueltas de un spiner

Vamos a hacer un circuito para **contar las vueltas** que da un **spinner**. Para detectar las vueltas usaremos un **contador módulo 3**, que encadenaremos con otro **módulo 10**, de **4 bits**. La cuenta será desde **0 hasta 9** y luego volverá a 0. Usaremos un **zumbador** para emitir un **pitido de 10ms** cada vez que un brazo pasa por encima del infrarrojo

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/IR-05.png)

La salida del **contador módulo 3** la mostramos en **binario**, en **dos LEDs** externos. El pulsador nos permite poner a **cero** los contadores. El circuito es el siguiente:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/IR-06.png)

Cada vez que un **brazo del spinner** pasa por encima del **sensor IR**, se emite un tic que activa el **temporizador de 10ms** que provoca un pitido. La salida de este temporizador es la que llevamos al **contador módulo 3** detector de vueltas, que  cuenta 3 tics recibido y emite uno para indicar que el spinner ha dado una vuelta. Lo **cargamos** y lo **probamos**:

[![Click to see the youtube video](http://img.youtube.com/vi/FhPjXto5SZY/0.jpg)](https://www.youtube.com/watch?v=FhPjXto5SZY)

La salida del componente **IR-tic** la podríamos llevar en **paralelo** al temporizador que emite el pitido y al contador detector de vuelta completa. Sin embargo, en este ejemplo lo hemos puesto **en serie**. Se ha hecho así para eliminar los posibles **tics espúreos** que se pudiesen aparecer.  Los tics que estén a distancias de pocos microsegundos, no han podido ser originados por el paso de los brazos del espinner. Colocando el **temporizador en serie** con el contador módulo 3 se eliminan si apareciesen.

# Contando tiempo

Los **generadores periódicos de tics** emiten uno cada vez que ha transcurrido un **tiempo T**. Mediante un contador podemos contar estos tics y medir el tiempo que ha transcurrido. Si como generador usamos un **corazón de tics** de 1 segundo, el contador se incrementará cada segundo: tendremos un **segundero**. Pero podemos usar otras unidades de tiempo: décimas de segundo, centésimas, minutos, horas...

## Ejemplo 12: Segundero

Utilizaremos un **contador de 4 bits módulo 10** conectado a un **corazón de tics de 1 segundo**. Su salida la mostramos por un **display de 7 segmentos**. Empezará en 0 y cuando llegue a 9 volverá a comenzar. El circuito es el siguiente:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/tiempo-01.png)

Lo **cargamos** y lo **probamos**:

[![Click to see the youtube video](http://img.youtube.com/vi/Qof6gAulBEs/0.jpg)](https://www.youtube.com/watch?v=Qof6gAulBEs)

Con sólo cambiar el **parámetro del tiempo** en el corazón, podemos hacer que las unidades que se cuentan sean décimas de segundo, segundos, minutos...

## Ejemplo 13: Cronómetro básico

Vamos a realizar un **cronómetro** que cuente hasta **9 minutos**, **59 segundos** y **9 décimas**, y luego vuelva a empmezar desde cero. Como sólo tenemos un display de 7 segmentos, sólo podremos ver **un dígito**, que se seleccionará mediante **dos interruptores**. En total necesitamos **4 dígitos**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/tiempo-02.png)

El cronómetro tiene **2 botones**: uno para poner a cero y arrancarlo (Reset/start), y otro para pararlo (STOP). Además, en **tres LEDs** se indicará el dígito que se está **visualizando en el display**. El montaje es el siguiente:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/tiempo-03.png)

Además, el **punto** del display de 7 segmentos **parpaderá** cada segundo (periodo de 500ms), para mostrar actividad en el cronómetro. **¿Cómo sería el circuito?**

Lo iremos haciendo poco a poco. Como tiene una precisión de **décimas**, empezando colocando un **corazón de tics** de décimas, que emita un tic cada **0.1 segundo** (cada 100 milisegundos). Las décimas las contamos con un **contador módulo 10 de 3 bits**, ya que su valor es entre **0** y **9**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/tiempo-04.png)

Este contador **generará un tic de salida** cada vez que se hayan contado **10 décimas**, es decir, **un segundo** y lo **encadenaremos** con el **contador de segundos**, que diseñaremos a continuación

El **segundero** toma los valores desde el **0** hasta el **59**, y luego vuelve a empezar. En vez de utilizar un **contador de 6 bits**, es más fácil divirlo en **dos contadores**, uno para cada **dígito**. Así, tendremos un dígito para las **unidades de segundo**, que varía entre **0** y **9** (Módulo 10), y otro para las **decenas de segundo**, que lo hace entre **0** y **5** (Módulo 6).

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/tiempo-05.png)

El **contador de unidades** de segundo se incrementa con cada tic que viene del **contador de décimas**. Cuando llega a 10, emite un tic y se incrementa el de las **decenas de segundo**. Sigue avanzando hasta que llega a **6**, momento en el que vuelve a **0** y **emite un tic** para indicar que ha transcurrido **un minuto**

El **último contador** es uno de **4 bits**, **módulo 10**, que cuenta las **unidades de minuto**, con valores entre 0 y 9

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/tiempo-06.png)

Como sólo tenemos **un display de 7 segmentos**, usamos un **multiplexor de 4 a 1** para mostrar el **dígito seleccionado**: décimas, unidades de segundo, decenas de segundo o unidades de minuto, según la posición de **dos interruptores**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-27/tiempo-07.png)

Esta es la **tabla** con el **dígito mostrado** según el valor de los **interruptores**

| Switches | Digito |
|----------|--------|
| 00       | Décimas|
| 01       | Unidades de segundo |
| 10       | Decenas de segundo | 
| 11       | Unidades de minuto |  

Para hacer más fácil la lectura, usaremos **tres LEDs** para indicar el **dígito** que se está visualizando. Si no hay ninguno encendido se están mostrando las décimas. Utilizamos un **decodificador de 2 a 4**, implementado mediante una **tabla de verdad**


(LEDs indicadores)

(Actividad en el punto del 7seg)

(Biestable para el estado del contador)

(Vídeo)

(TODO)

# Recorriendo tablas

* Secuencia en los LEDs
* Texto en el 7-segmentos

(TODO)

# Ejercicios propuestos (X BitPoints)

Ver los detalles de los ejercicios y las **entregas** en el menú **Archivos/Ejemplos/2-Ejercicios** de la colección de este tutorial

**Resumen**:

* **Ejercicio 27.1** (Total **x Bitpoints**): 

* **Ejercicio 27.2** (Total **x Bitpoints**): 

* **Ejercicio 27.3** (Total **x Bitpoints**): 

* **Ejercicio 27.4** (**5 Bitpoints**). Ejercicio Libre. Premiar la creatividad. **Entregar** por redes sociales o github: Pantallazos, enlaces, vídeos, etc...

# Ejercicios entregados

## Primero

### Ejercicio 27.1
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 27.2
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 27.3
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 27.4
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()


## Segundo

### Ejercicio 27.1
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 27.2
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 27.3
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 27.4
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

## Tercero

### Ejercicio 27.1
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 27.2
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 27.3
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 27.4
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