![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Portada/Tut-26-portada.png)

# Vídeo

(En construcción...)

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

Haz click en la imagen para ver el **vídeo en Youtube**

# Descripción

(TODO)

# Colección

**Academia-Jedi-HW-26.zip**: Colección para este tutorial. Descargar e instalar 

# Contenido

* [Reloj del sistema](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-26:-Tiempo,-tics-y-temporizadores#reloj-del-sistema)
  * [Evento: Flanco de subida del sistema](#evento-flanco-de-subida-del-sistema)
* [Pulsos](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-26:-Tiempo,-tics-y-temporizadores#pulsos)
  * [Pulsos periódicos](#pulsos-peri%C3%B3dicos)
* [Tics](#tics)
  * [Generadores de tics](#generadores-de-tics)
    * [Pulsador de tics](#pulsador-de-tics)
      * [Ejemplo 1: Detección de un tic proveniente de un pulsador](#ejemplo-1-detecci%C3%B3n-de-un-tic-proveniente-del-pulsador) 
      * [Ejemplo 2: Encender un LED al apretar el botón dos veces (doble click)](#ejemplo-2-encender-un-led-al-apretar-el-bot%C3%B3n-dos-veces-doble-click)
    * [IR de tics](#ir-de-tics)
      * [Ejemplo 3: Detección del paso de un objeto](#ejemplo-3-detecci%C3%B3n-del-paso-de-un-objeto)
      * [Ejemplo 4: Detección del paso de tres objetos](#ejemplo-4-detecci%C3%B3n-del-paso-de-3-objetos)
    * [Corazón de tics](#coraz%C3%B3n-de-tics)
      * [Ejemplo 5: Cazando tics periódicos](#ejemplo-5-cazando-tics-peri%C3%B3dicos)
* [Temporizadores](#temporizadores)
  * [Generando un pulso de anchura W](#generando-un-pulso-de-anchura-w)
    * [Ejemplo 6: Encender un LED durante 3 segundos](#ejemplo-6-encender-un-led-durante-3-segundos)
    * [Ejemplo 7: Pitidos de duración constante](#ejemplo-7-pitidos-de-duraci%C3%B3n-constante)
  * [Encadenamiento de temporizadores](#encadenamiento-de-temporizadores)
    * [Ejemplo 8: LEDs encadenados](#ejemplo-8-leds-encadenados)
  * [Encadenamiento en anillo](#encadenamiento-en-anillo)
    * [Ejemplo 9: Mi primer automatismo](#ejemplo-9-mi-primer-automatismo)
  * [Generando pulsos periódicos](#generando-pulsos-peri%C3%B3dicos)
    * [Ejemplo 10: LED pulsante con sonido](#ejemplo-10-led-pulsante-con-sonido)
    * [Ejemplo 11: LED con dos intesidades de brillo](#ejemplo-11-led-con-dos-intensidades-de-brillo)
    * [Ejemplo 12: Servo a dos posiciones](#ejemplo-12-servo-a-dos-posiciones)
* [Conclusiones](#conclusiones)
* [Ejercicios propuestos (25 Bitpoints)](#ejercicios-propuestos-25-bitpoints)
* [Ejercicios entregados](#ejercicios-entregados)
* [Autor](#autor)
* [Licencia](#licencia)
* [Enlaces](#enlaces)
* [Preguntas frecuentes](#preguntas-frecuentes)

# Introducción

(TODO)

# Reloj del sistema

  Los **circuitos digitales** funcionan a ritmo de un **reloj**, conocido como **reloj del sistema**. Es el que define la **velocidad máxima** a la que ocurren las cosas dentro del circuito. También nos permite **medir el tiempo**. 

En la **Icezum Alhambra** el reloj del sistema es de **12Mhz**. Se encuentra situado **fuera de la FPGA** y la señal de reloj se introduce en ella por uno de sus pines, denominado **CLK**, al que tenemos acceso desde **Icestudio**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Reloj-sistema-01.png)

En icestudio, todos los componentes que tienen una entrada de reloj, **se conectan automáticamente** a este reloj del sistema. Esto se indica mediante un **cuadrado amarillo** conectado a su entrada de reloj

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Reloj-sistema-02.png)

Pero el **reloj del sistema** es un **pin** más de entrada de nuestra **FPGA**, y **lo podemos usar** como cualquier otro. También lo podemos **conectar manualmente** a las entradas de reloj de los componentes. Estos dos circuitos, que hacen parpadear un LED a 1Hz, son **equivalentes**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Reloj-sistema-03.png)

Esta es la manera de hacer la **conexión manual**. Se coloca una entrada genérica, se conecta al pin de reloj, y se selecciona la **etiqueta CLK**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Reloj-sistema-04.gif)

El reloj del sistema para nosotros es como un **corazón**, que **bombea bits** muy rápidamente. Saca unos y ceros alternativamente, a una frecuencia de **12Mhz**. O lo que es lo mismo, el **tiempo** entre dos unos consecutivos es de **83.3ns**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Reloj-sistema-05.png)

**¡Esto es muy rápido!** Cada segundo, este super corazón... **¡bombea 12 millones de 1s!**. Si hacemos un circuito capaz de realizar una operación cada vez que llega un 1 del sistema, en un segundo realizaría **12 millones de estas operaciones**. Y si colocamos **dos** de estos circuitos **en paralelo**, haríamos **24 millones de operaciones por segundo**

Si cada vez que llega un 1, pintásemos una marca en una carreta y avanzásemos 1 milímetro, ¡¡en un segundo habríamos pintado más de 12 Kilómetros de carretera!!

## Evento: flanco de subida del sistema

La señal de reloj del sistema, o en general cualquier otra señal de reloj, la representamos mediante **señales cuadradas**. Las líneas inferiores representan los ceros y las superiores los unos. El tiempo se incrementa hacia la derecha. En este ejemplo lo primero que aparece es un **1**, luego un **0**, luego 1, etc... (de izquierda a derecha)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Reloj-sistema-06.png)

El **cambio de 0 a 1** es un **evento**, conocido con el nombre de **flanco de subida**. Es el evento que usaremos como **referencia** (también podríamos usar el flanco de bajada). Se representa colocando una **flecha** en la línea de transición entre el 0 y el 1, que **apunta hacia arriba**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Reloj-sistema-07.png)

Esto nos permite **definir mejor los tiempos**. Así, el **periodo** del reloj del sistema será el **tiempo que transcurre** entre **dos flancos de subida consecutivos**. Utilizaremos una **flecha hacia arriba**, con patas, para representar estos eventos. Se llama **Flanky** 😃

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Reloj-sistema-08.png)

El **reloj del sistema** lo podemos ver, por tanto, como un **corazón** que produce **eventos de flanco de subida** de forma periódica, con **periodo T** de **83.3ns**. Vamos, que bombea Flankys 😃

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Reloj-sistema-09.png)
Para **medir tiempo** basta con **contar estos eventos**. Cada vez que llega uno, sabemos que **ha transcurrido** un tiempo igual a **83.3ns**. El funcionamiento es similar al segundero de un reloj analógico, que avanza un ángulo cada segundo, pero con unidades de tiempo más pequeñas

# Pulsos

Cuando una señal está en **reposo** (a cero), se **activa** durante un tiempo (W) y vuelve al **reposo**, decimos que se ha producido **un pulso**. Al **tiempo** que permanece a **activo** (a 1) lo denominamos **anchura del pulso**, y solemos usar la **letra W** para denominarlo

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Pulso-01.png)

Esta **propiedad** de partir del **estado inicial**, y **volver** a él, es muy importante. Por ello, la mayoría de las veces **usaremos pulsos** para comunicar los **eventos** que ocurren en nuestro circuito

El pulso también lo podemos ver como la **llegada de un flanco de subida**, y al cabo de un tiempo W, un **flanco de bajada**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Pulso-02.png)

## Pulsos periódicos

Los pulsos los denominamos **periódicos** cuando aparecen de **forma repetitiva**, con el **mismo periodo T**, aunque la **anchura de cada pulso sea diferente**. En esta gráfica se muestra un **pulso de periodo T**, en el que las anchuras de los pulsos son **W1**, **W2** y **W3**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Pulso-03.png)

Dibujando los **pulsos en vertical**, uno de bajo de otro, se puede apreciar mejor que tienen el **mismo periodo**, y que sólo se diferencian en sus anchuras. Tenemos dos parámetros: **El periodo** (T), que es el mismo para todos y la **anchura del pulso** (W) que puede variar según el pulso

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Pulso-04.png)

Estos **pulsos periódicos** reciben el nombre de **señales PWM** (Pulse-width modulation. Modulación por anchura de pulso). Aunque las veremos un poco más adelante, os adelanto que son muy importantes, ya que nos permiten **definir la cantidad de energía** que queremos **transmitir** (Anchura del pulso), y el **canal físico** por el que hacerlo (Frecuencia), según la aplicación

# Tics

El reloj del sistema produce pulsos con un **periodo T**. Este periodo nos determina el **tiempo mínimo**. Es nuestra **resolución**. No podemos medir ni trabajar con tiempos menores a T. Imagina que tienes un cronónometro que cuente segundos. Podrás medir minutos y horas, pero nada inferior a 1 segundo. Eso miso pasa con nuestro reloj del sistema

Definimos un **Tic** como el **pulso mínimo** que podemos producir en nuestro circuito. Es decir, será un **pulso** que tenga una **anchura de T**. En el caso de la Icezum Alhambra, los tics son de **83.3ns**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Tic-01.png)

Los **Tics** son **muy importantes**. Son nuestras **unidades de medida**. Todo lo **mediremos en Tics**. Así, por ejemplo, el siguiente pulso tiene una anchura de **3 tics**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Tic-02.png)

Para pasarlo a unidaes conocidas, sólo hay que **multiplicarlo** por el periodo del reloj del sistema (T) (o el inverso de la frecuencia). Así, tendríamos que una **anchura de 3 tics** equivale a **250ns**

La **palabra tic** la usaremos para dos cosas. **1)** para referirnos a las **unidades de tiempo**: Ej. "Pulso de anchura 3 tics. **2)** Para referirnos a un **pulso de anchura 1**: Ej. "Emitir un tic"

El **tic** es tan importante, y lo usaremos tanto, que lo representaremos mediante su propio icono: **Ticky**. En este ejemplo vemos **dos tics emitidos**, separados una **distancia de 5 tics**. Y debajo la misma representación, pero usando a Ticky :-)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Tic-03.png)

Los **tics** los usaremos para **comunicar nuestros componentes** permitiendo realizar **temporizaciones** y sincronizaciones entre ellos. Por eso, lo primero que necesitamos son **componentes** que **generen tics**: Los generadores de tics

## Generadores de tics

Los **tics** tienen, por definición, una **anchura de 1**. Son nuestras unidades. Por eso para transmitir eventos los usaremos: nos indican cuándo ha sucedido algo, consumiento el **tiempo mínimo**. Veremos **tres tipos** de generadores de tics: el **pulsador de tics**, que genera un tic cada vez que se aprieta el pulsador, el **IR de tics** que lo produce cuando se detecta un objeto y el **corazón de tics**, que bombea tics periodicamente. 

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Tic-04.png)

### Pulsador de tics

El **pulsador de tics** es un componente que recibe por su entrada la **seña** directactamente de un **pulsador exterior** a la FPGA y produce como salida un **tic**. Internamente **sincroniza** la señal, **elimina los rebotes** y genera un **tic limpio**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Pulsador-tic-01.png)

El **cómo hace esto** internamente lo veremos en el futuro. Ahora de momento nos basta con saber cómo funciona: Cada vez que lo apretamos **aparece un tic**. Al soltarlo no hace nada. En esta **animación** se muestra su funcionamiento

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Pulsador-tic-02.gif)

Este componente se encuentra en la colección **Academia-Jedi-HW-26.zip**, de este tutorial, en el menú **Varios/Pulsadores/Pulsador-tic**

#### Ejemplo 1: Detección de un tic proveniente del pulsador

Para **verificar** que el componente **pulsador-tic** funciona **bien**, tenemos que **detectar el tic** que emite al apretarse el **botón**. Una posibilidad sería conectarlo directamente a un **LED**, como en este circuito:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Ejemplo-01-1.png)

Pero, aunque el LED sí que se enciende y se apaga con el pulso, lo hace tan **rápidamente** que nuestro **ojo NO lo aprecia**. Por tanto, necesitamos otro modo de **cazar el tic**

Probemos ahora con este **otro circuito**, al que le añadimos **un biestable** para capturar el tic y que nos lo **notifique** en un **LED**. Ahora sí, cada vez que apretemos el pulsador, el **LED se enciende** para notificarnos que se **ha recibido el tic**. Borramos la notificación con otro pulsador

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Ejemplo-01-2.png)

Lo **cargamos** y lo probamos. La prueba es muy tonta, pero con ella hemos comprobado que los **biestables** pueden **cazar los tics**, a pesar de que los tics son muy estrechos :-). **¡Ya no hay tic que se nos escape!**

[![Click to see the youtube video](http://img.youtube.com/vi/0x2J4SZmEz0/0.jpg)](https://www.youtube.com/watch?v=0x2J4SZmEz0)

#### Ejemplo 2: Encender un LED al apretar el botón dos veces (doble-click)

Vamos a diseñar un circuito que nos **encienda un LED** de notificación cuando **apretamos dos veces un pulsador**. La notificación la **borramos** con otro **pulsador**. ¿Cómo sería el circuito?

Utilizaremos **dos biestables**, uno para detectar **la primera pulsación**, y otro para **la segunda**. La segunda se detecta con la condición de que haya habido **una pulsación en el pasado y una en el presente**. El circuito es:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Ejemplo-2-1.png)

Lo **cargamos** y lo **probamos**. Da igual lo rápido o lento que hagamos la pulsación, el LED siempre nos **notificará** cuando se ha apretado el botón **dos veces**

[![Click to see the youtube video](http://img.youtube.com/vi/qQcr9dkCdWE/0.jpg)](https://www.youtube.com/watch?v=qQcr9dkCdWE)

### IR de tics

El **IR de tics** recibe por su entrada la seña directactamente de un **sensor de infrarrojos** digital (IR) exterior a la FPGA y produce como salida un tic. Internamente sincroniza la señal y genera un tic limpio

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/IR-tic-01.png)

La **naturaleza de la señal digital** de entrada, entre un **pulsador** y un **IR es diferente**, por lo que hay que usar componentes distintos. Los pulsadores tienen rebotes, mientras que los IR no

En esta **animación** se muestra su funcionamiento. Cuando **aparece un objeto** se **emite un tic**, y **permanece en reposo** en caso contrario

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/IR-tic-02.gif)

Este componente se encuentra en la colección Academia-Jedi-HW-26.zip, de este tutorial, en el menú **Varios/IR/IR-tic**

#### Ejemplo 3: Detección del paso de un objeto

Para comprobar que el componente IR-tic **funciona**, conectaremos un **biestable** a su salida para que nos **notifique** en un **LED** si ha pasado un **objeto** por **delante del sensor** 

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/IR-tic-03.png)

Lo **cargamos** y lo **probamos**. No es un ejemplo muy espectacular, pero siempre hay que **probar los circuitos** y comprobar que funcionan, para ir construyendo otros **más complejos** a partir de ellos. En este **vídeo** de Youtube vemos su funcionamiento

[![Click to see the youtube video](http://img.youtube.com/vi/f6LQ8KVoYMY/0.jpg)](https://www.youtube.com/watch?v=f6LQ8KVoYMY)

#### Ejemplo 4: Detección del paso de 3 objetos

Vamos a hacer un circuito que nos notifique cuando el **sensor** ha detectado **3 objetos**. Es decir, un circuito que detecte que han llegado **3 tics** del controlador IR-tic, y que nos lo notifique encendiendo un LED cuando esto ocurra. Con un pulsador borramos la notificación, para volver a comenzar. **¿Cómo lo hacemos?**

En realidad es prácticamente igual que el **ejemplo 2**, donde detectábamos 2 tics (provenientes de un pulsador). Ahora detectamos 3 tícs del IR, pero el funcionamiento es el mismo. Utilizaremos **3 biestables** y usaremos **puertas AND** para implementar las condiciones de cambio. Si han llegado **X tics**, y llega un tic nuevo (presente), entonces es que han llegado **X+1 tics** (y activamos el biestable).  La salida del último biestable es la **notificación** que estamos buscando. El circuito es:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/IR-tic-04.png)

Además usamos **3 LEDs intermedios** para mostrar los tics que van llegando, y ver lo que está pasando **internamente** en el circuito, para entenderlo bien al probarlo

El **montaje** es el mismo que hemos usado para el ejemplo 3. Tiene un **sensor de IR**, el **LED de notificación** y el **pulsador** para borrar la notificación

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/IR-tic-05.png)

Lo **cargamos** y lo **probamos**. En este **vídeo** estoy usando el mismo objeto, que pasa 3 veces, para comprobar el funcionamiento:

[![Click to see the youtube video](http://img.youtube.com/vi/YA0xIrqH3Bc/0.jpg)](https://www.youtube.com/watch?v=YA0xIrqH3Bc)

### Corazón de tics

El **corazón de tics** es un componente igual al corazón que ya conocemos, pero en vez de **bombear** bits, usa **tics**. El tiempo que transcurre entre cada tic es el **periodo T**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Corazon-tic-01.png)

En esta **animación** se muestra un corazón de tics, de **1Hz**, en acción. El tamaño del tic **NO está a escala**. Su anchura real es muchísimo menor

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Corazon-tic-02.gif)

Están disponibles en el **menú Varios/Bombeo/Tics**. Se han definido **4 corazones de tic** paramétricos, cuyas unidades están en **Hz**, **segundos**, **mili-segundos** y **micro-segundos**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Corazon-tic-03.png) 

### Ejemplo 5: Cazando tics periódicos

Para comprobar el funcionamiento de estos **generadores de tics periódicos**, NO podemos conectarlos directamente a un **LED**, como hacíamos con los corazones normales. La anchura de los tics es tan pequeña, que no se aprecia en los LEDs. Utilizaremos un **biestable para cazarlos**, con un **LED de notificación**, y borraremos manualmente esta notificación, mediante un **pulsador** conectado a la entada de **reset**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Corazon-tic-04.png)

Este circuito, además de usarlo para comprobar que el corazón de tics funciona, es muy divertido porque **nos trolea**. Con el **pulsador** puedes intentar **apagar el LED**, pero se volverá a encender con el siguiente tic que llegue :-) El escenario es este:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Corazon-tic-5.jpg)

Lo **cargamos** y lo **probamos**. Efectivamente, el LED nos trolea :-)

[![Click to see the youtube video](http://img.youtube.com/vi/yPMtfJG-Unw/0.jpg)](https://www.youtube.com/watch?v=yPMtfJG-Unw)

# Temporizadores

Los temporizadores (timers en inglés) son unos circuitos que nos informan cuándo **ha transcurrido un intervalo de tiempo**. Los que nosotros usaremos, tienen **2 salidas**, una por donde saca un **pulso** de anchura igual al intervalo de tiempo especificado y otra que **emite un tic** para notificarnos que **el tiempo ha expirado**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Timer-01.png)

Tiene una entrada **start** para ponerlo en marcha al enviarle un **tic** por ella. El **intervalo de tiempo** se especifica como **parámetro** (W). Según el temporizador, las **unidades** usadas son **segundos** (sec), **milisegundos** (msec) o **microsegundos** (usec). Por la **salida p** se obtiene un **pulso de anchura W**, mientras que por la **salida tic** se emite un **tic** cuando ha **expirado el tiempo W**. Usaremos una u otra salida, o ambas, según la aplicación

En esta **animación** se muestra el funcionamiento

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Timer-02.gif)

Para representar el **comportamiento en el tiempo** de los **circuitos secuenciales** se usa un tipo de diagrama cronocido como **cronograma**. En él se representa la **evolución de las señales en el tiempo**. El tiempo fluje de izquierda a derecha

En este **cronograma** se representa el funcionamiento de un **temporizador de intervalo de tiempo W**, que se le pasa como parámetro. Produce un **pulso de anchura W**, y un **tic** transcurridas **W unidades de tiempo** desde que se recibe el **tic de start**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Timer-03.png)

Los temporizadores tienen **muchas aplicaciones**. Vamos a ver ejemplos de algunas de ellas

## Generando un Pulso de anchura W

El uso típico es para **encender** o **apagar** un dispositivo transcurrido un **tiempo W**. Se usa la **salida p** para habilitar/deshabilitar el dispositivo

### Ejemplo 6: Encender un LED durante 3 segundos

Haremos un circuito que **encienda un LED** al **apretar un pulsador**, y que se mantenga **encendido durante 3 segundos**, transcurridos los cuales el LED se apaga

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Timer-04.png)

Lo **cargamos** y lo **probamos**. ¡Ya tenemos nuestro primer **temporizador** funcionando!

[![Click to see the youtube video](http://img.youtube.com/vi/qO2U2wcFIqA/0.jpg)](https://www.youtube.com/watch?v=qO2U2wcFIqA)

### Ejemplo 7: Pitidos de duración constante

En este ejemplo emitimos un **pitido durante 20ms** cada vez que se aprieta el **pulsador** o el **sensor de infrarrojo** detecta un objeto. Utilizamos la **salida de pulso** del temporizador para activar la **señal de 400Hz** a través de una **puerta AND** que llega al **zumbador**. En cuanto el pulso termina, la salida de la AND es 0, y se deja de escuchar

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Timer-05.png)

El pulso se envía a un **LED**, para visualizarlo. Además, se ha colocado un **spiner** para activar el **sensor de IR** y escuchar los pitidos al moverlo. El **montaje** es el siguiente:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Timer-06.png)

Lo **cargamos** y lo **probamos**. En este **vídeo** lo vemos en funcionamiento 

[![Click to see the youtube video](http://img.youtube.com/vi/NrMx54hNDXg/0.jpg)](https://www.youtube.com/watch?v=NrMx54hNDXg)

## Encadenamiento de temporizadores

La **salida tic** del los **temporizadores** se puede usar para activar otro temporizador, de forma que los podemos ir **encadenando**. Cuando termina el primer temporizador, activa el segundo, este al tercero, y así sucesivamente. Esto nos permite activar componentes secuencialmente: uno sólo se activa cuando el anterior ha terminado

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Timer-12.gif)

Veremos **dos ejemplos** de encadenamiento. Uno con **LEDs**, en los que la luz se va **propagando** de un LED al siguiente. Y otro en el que se **activan** diferentes circuitos **secuencialmente**, cada uno con una duración

### Ejemplo 8: LEDs encadenados

Haremos un circuito que encienda **3 LEDs consecutivamente**, primero uno, cuando se apague, el segundo, y cuando este se apague, se enciende el tercero. El efecto es una luz que **se propaga de un LED al siguiente**. Cada LED estará encendido **400ms**

Partimos de un circuito que ya sabemos hacer: **encender un LED** durante **400ms** al apretar un **pulsador**. Sería este: 

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Timer-8.png)

Cuando han transcurrido los 400ms, además de apagarse el LED, el timer 1 **emite un tic** por su **salida tic**, para indicar que ha terminado. Esta salida la conectamos a la **entrada start** del **siguiente temporizador**, que está conectado a **otro LED**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Timer-09.png)

Y por último encadenamos el **tercer temporiador** de la misma forma. Usamos las **salidas de pulso** para **encender** los LEDs y las **salidas tic** para **propagar** la activación al siguiente temporizador

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Timer-10.png)

Aunque hemos usado el **mismo tiempo en todos los timers**, cada uno podría tener uno diferente. **Reordenamos** un poco el circuito, y usamos un único parámetro de tiempo para todos los temporizadores. El **circuito final** es este:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Timer-07.png)

El **funcionamiento** del circuito, de forma aproximada, se muestra en esta **animación**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Timer-13.gif)

En el **montaje** colocamos los **tres LEDs** y el **pulsador**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Timer-11.png)

Lo **cargamos** y lo **probamos**. Se ve claramente el efecto de **propagación**

[![Click to see the youtube video](http://img.youtube.com/vi/JF_UE38wJ8I/0.jpg)](https://www.youtube.com/watch?v=JF_UE38wJ8I)

Este es un ejemplo muy bueno del **pensamiento espacial en el hardware**. Al apretar el botón aparece un tic que **físicamente** se va **desplazando** de un temporizador a otro. En cuanto alcanza un temporizador, se enciende el LED. Y como además el hardware funciona en **paralelo**, puede haber **varios tics viajando simultáneamente**. Esto es lo que vemos en el vídeo anterior: No es necesario a que termine de propagarse un tic para que se pueda enviar otro, sino que se pueden enviar varios

## Encadenamiento en anillo

¿Y qué ocurre si al **encadenar** temporizadores, el **último** lo conectamos de vuelta con el **primero**? Nuestro tic empezaría a recorrer el **anillo de temporizadores**, y nunca terminaría hasta que apagásemos el circuito. Es una forma de hacer un **bucle infinito** en hardware :-)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Timer-14.gif)

Si inicialmente **todos** los temporizadores están **desactivados**, no tenemos ningún tic circulando. Para **introducir tics desde fuera** y que queden atrapados en el bucle infinito, usamos una **puerta OR** en la entrada del **temporizador 1**. Recibirá tics de una **fuente externa** o del **último temporizador**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Timer-15.png)

Me encanta esta **trampa de tics**. Si un tic incauto se le ocurre entrar en el **anillo**... quedará atrapado **por toda la eternidad** muajajajajajaja. 

Con los **timers encadenados** haremosr nuestros **primeros automatismos**, que **activan secuencialmente** una serie de circuitos. Y esto lo **repiten** una y otra vez. 

### Ejemplo 9: Mi primer automatismo

Vamos a crear un circuito que realice tres **tareas** muy sencillas, una detrás de otra, y que se repitan al terminar la última. Cada tarea tiene una **duración diferente**:

| Tarea  | Duración (seg) | Descripción | Dispositivo |
|--------|----------------|-------------|--------------|
|   1    | 3              | Parpadeo a 2 Hz | LED |
|   2    | 2              | Hacer sonar una sirena    | Zumbador |
|   3    | 4              | Apertura de barrera  | Servo |

Nuestro automatismo estará **en reposo** hasta que se **apriete el pulsador**. En se momento se empieza con la **tarea 1** y se continúa con las siguientes. Cuando llega a la última, **empieza** otra vez desde el **principio**

Su **funcionamiento** se muestra en esta **animación**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Timer-16.gif)

Primero hacemos los **3 circuitos** que realizan cada **tarea**. Son independientes, con una **entrada de habilitación**, que hace que funcionen al activarla, y se desactiven en caso contrario. Estos circuitos ya los conocemos de otros ejercicios

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Timer-17.png)

Luego hacemos el **anillo de temporizadores**. Cada uno está configurado con su **propia duración**, en **segundos**. Sus **salidas p** se conectan a las **entradas de enable** de los circuitos anteriores. Cada timer con su circuito correspondiente. La **salida tic** se conectan con la **entradas** del siguiente timer

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Timer-18.png)

El **temporizador 1** tiene **dos entradas de tics**, una del **pulsador de arranque** y otra del **temporizador 3**, a través de la **puerta OR**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Timer-19.png)

Este es el **circuito completo**, con todos sus partes conectadas

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Timer-20.png)

Y este es el **montaje** para probar el circuito, con los **3 LEDs**, uno de cada tarea, el **zumbador** para la sirena y el **servo** para la barrera

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Timer-21.png)

Lo **cargamos** y lo **probamos**. En este vídeo lo vemos en **acción**:

[![Click to see the youtube video](http://img.youtube.com/vi/gK7FM6Ki__w/0.jpg)](https://www.youtube.com/watch?v=gK7FM6Ki__w)

## Generando pulsos periódicos

Los temporizadores nos permiten generar [pulsos periódicos](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-26:-Tiempo,-tics-y-temporizadores#pulsos-peri%C3%B3dicos) **muy fácilmente**. Para ello sólo hay que **conectar a la entrada del temporizador** una fuente periódica de tics: un **corazón de tics**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Pulsos-periodicos-01.png)

El **corazón de tics** es el componente que determina el **periodo (T)** y el **temporizador** la **anchura (W)**. La señal producida tiene una pinta como la siguiente. La anchura de todos los periodos es la misma

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Pulsos-periodicos-02.png)

### Ejemplo 10: LED pulsante con sonido

Este circuito genera un **sonido pulsante** como los que se escuchan en los aparámetos médicos de los hospitales que monitorizan el **corazón**. El pulso periódico también se muestra en un LED externo. Usamos un **periodo de 1400ms** y una **anchura de 50ms**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Pulsos-periodicos-03.png)

El **montaje** es muy básico: Sólo necesitamos un **LED** y un **zumbador**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Pulsos-periodicos-04.png)

Lo **cargamos** y lo **probamos**. ¡Nuestra placa vive!

[![Click to see the youtube video](http://img.youtube.com/vi/1xVw-TwCgc0/0.jpg)](https://www.youtube.com/watch?v=1xVw-TwCgc0)

### Ejemplo 11: LED con dos intensidades de brillo 

Si sacamos por un LED una **señal de 60Hz o mayor frecuencia**, no notaremos que parpadea. Nuestros cerebro se queda sólo con **su valor medio** y lo veremos encendido (cuando en realidad no lo está, se está enciendo y apagando muy rápidamente)

Vamos a fijar la **frecuencia de parpadeo** a **1Khz**. Si ahora variamos la **anchura del pulso** (W), modificamos la **potencia** transferida al LED. Cuanto **mayor** sea la **anchura** del pulso, **más brillará** el LED

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Pulsos-periodicos-06.png)

La señal superior tiene un pulso de **anchura de 900 us**, mientras que la inferior de **100 us**. La primera transmite más potencia, haciendo que el LED brille más. Este circuito genera esas dos señales, y mediante un **multiplexor** seleccionamos cuál es la que se saca por el LED

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Pulsos-periodicos-05.png)

Cuando el **pulsador no está apretado**, al LED le llega la señal de **bajo brillo** y al **apretarlo**, la de **alto brillo**. Lo **cargamos** y lo **probamos**:

[![Click to see the youtube video](http://img.youtube.com/vi/oWQqMuY4ASc/0.jpg)](https://www.youtube.com/watch?v=oWQqMuY4ASc)

Inicialmente el LED está totalmente apagado. Al encender la alimentación empieza a iluminarse con **brillo bajo**. Al apretar el pulsador lo hace con **brillo alto**

### Ejemplo 12: Servo a dos posiciones

El mismo esquema que hemos aplicado en el ejemplo 11, lo podemos usar para **generar las señales PWM** de control de un **Servo Futaba 3003** o compatible. El fabricante especifica que el **periodo es de 20ms**. Las anchuras de los pulsos son de **2250us** para ir a un extremo y **550us** para el otro

Este circuito manda el **servo a dos posiciones**, según el estado de un **botón**. El servo apunta hacia la derecha y al pulsar se mueve a la izquierda. Esto ya lo sabíamos hacer con el componente [ServoBit](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-10:-ServoBit), pero ahora vemos un poco qué hay dentro de ese componente: un **corazón de tics**,  **temporizadores** y un **multiplexor**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-26/Pulsos-periodicos-07.png)

Lo **cargamos** y lo **probamos**

[![Click to see the youtube video](http://img.youtube.com/vi/fnuEkrys3bk/0.jpg)](https://www.youtube.com/watch?v=fnuEkrys3bk)

Con esto podemos diseñar un **controlabor básico de dos posiciones** para **cualquier servo**: Sólo necesitamos conocer la **frecuencia** de la señal y los valores de las **anchuras de los pulsos**

# Conclusiones

La comunicación de **eventos** entre componentes la hacemos mediantes **tics**, que son los pulsos con la **anchura más pequeña** que podemos generar dentro de nuestro sistema. Hemos visto tres componentes **generadores de tics**: el pulsador, el sensor de infrarrojos y el corazón. Los **temporizadores** son unos elementos esenciales, que nos permiten **medir el tiempo** y emitir un **tic** cuando ha transcurrido cierto tiempo. Con ellos hemos hecho nuestros primeros **automatismos** secuenciales, además de **generar señales PWM** para controlar servos y **modular el brillo** de los LEDs

Todavía no sabemos cómo mover un servo a más de dos posiciones, o conseguir más de dos intensidades de brillo. Tampoco sabemos cómo hacer un temporizador. Necesitamos conocer algunos componentes más para lograrlo. Pero poco a poco, vamos comprendiendo los funcionamientos de los circuitos, de manera práctica


# Ejercicios propuestos (25 BitPoints)

Ver los detalles de los ejercicios y las **entregas** en el menú **Archivos/Ejemplos/2-Ejercicios** de la colección de este tutorial

**Resumen**:

* **Ejercicio 26.1** (Total **5 Bitpoints**): Barrera levantada durante 4 segundos al detectarse un IR

* **Ejercicio 26.2** (Total **5 Bitpoints**): Disparo tipo arcade en 8 LEDs

* **Ejercicio 26.3** (Total **10 Bitpoints**): Franky automatizado

* **Ejercicio 26.4** (**5 Bitpoints**). Ejercicio Libre. Premiar la creatividad. **Entregar** por redes sociales o github: Pantallazos, enlaces, vídeos, etc...

# Ejercicios entregados

## Primero

### Ejercicio 26.1
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 26.2
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 26.3
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 26.4
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()


## Segundo

### Ejercicio 26.1
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 26.2
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 26.3
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 26.4
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

## Tercero

### Ejercicio 26.1
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 26.2
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 26.3
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 26.4
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()


# Autor

* [Juan González-Gómez](https://github.com/Obijuan) (Obijuan)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/logos-urjc-gsyc-peloto-jderobot.png)

# Licencia

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/attribution-share-alike-creative-commons-license.png)

# Créditos y agradecimientos

* Icono de la casa. By Timothy Miller - https://www.iconfinder.com/iconsets/pictype-free-vector-icons, CC BY-SA 3.0, https://commons.wikimedia.org/w/index.php?curid=34829035

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
