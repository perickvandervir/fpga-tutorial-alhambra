![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/Portada/Tut-25-portada.png)

# Vídeo

[![Click to see the youtube video](http://img.youtube.com/vi/8A910OmjUnc/0.jpg)](https://www.youtube.com/watch?v=8A910OmjUnc&list=PLmnz0JqIMEzXaeYVzf2TfTzRekPIVoljw&index=25)

Haz click en la imagen para ver el **vídeo en Youtube**

# Descripción

Para **almacenar** los bits necesitamos un nuevo componente: **el biestable**. Con estos elementos, nuestros circuitos pueden **recordar** eventos ocurridos en el  **pasado**, y no sólo en el presente. Haremos ejemplos de uso de biestables en circuitos simples, para ganar **intuición** sobre cómo utiliarlos

# Colección

[Academia-Jedi-HW-25.zip](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/Colecctions/Academia-Jedi-HW-25.zip): Colección para este tutorial. Descargar e instalar 

# Contenido

* [Introducción](#introducci%C3%B3n)
* [Eventos y notificaciones](#eventos-y-notificaciones)
  * [Ejemplo 1: Encender un LED con pulsador, sin biestable](#ejemplo-1-encender-un-led-con-pulsador-sin-biestable)
* [Biestables con Set y Reset](#biestables-con-set-y-reset)
  * [Ejemplo 2: Notificación de botón apretado](#ejemplo-2-notificaci%C3%B3n-de-bot%C3%B3n-apretado)
  * [Banderas (Flags)](#banderas-flags)
* [Ejemplos de aplicación](#ejemplos-de-aplicaci%C3%B3n)
  * [Ejemplo 3: Encender un LED con sensor IR, sin biestable](#ejemplo-3-encender-un-led-con-sensor-ir-sin-biestable)
  * [Ejemplo 4: Notificación de presencia](#ejemplo-4-notificaci%C3%B3n-de-presencia)
  * [Ejemplo 5: Sistema automático de subida y bajada de barrera](#ejemplo-5-sistema-autom%C3%A1tico-de-subida-y-bajada-de-barrera)
  * [Ejemplo 6: Caja fuerte con apertura con código](#ejemplo-6-caja-fuerte-con-apertura-con-c%C3%B3digo)
  * [Ejemplo 7: Alarma antirrobo](#ejemplo-7-alarma-antirrobo)
* [Conclusiones](#conclusiones)
* [Ejercicios propuestos (25 Bitpoints)](#ejercicios-propuestos-25-bitpoints)
* [Ejercicios entregados](#ejercicios-entregados)
  * [Josep Montoliu (Klarojms)](#josep-montoliu-klarojms)
  * [Federico Coca (@fgcoca)](#federico-coca-fgcoca)
  * [Viriato (@Srviriato)](#viriato-srviriato)
* [Autor](#autor)
* [Licencia](#licencia)
* [Créditos y agradecimientos](#cr%C3%A9ditos-y-agradecimientos)
* [Enlaces](#enlaces)
* [Preguntas frecuentes](#preguntas-frecuentes)

# Introducción

Los **circuitos digitales** realizan tres operaciones con bits: **transporte**, **manipulación** y **almacenamiento**. Los **cables** se encargan del **transporte** y los **circuitos combinacionales** de su **manipulación**. Nos falta por aprender **cómo almacenar bits**. Esto lo realizan los **biestables**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/intro-01.png)

Un biestable es el **elemento mínimo** que permite **almacenar un bit**. Almacenar los bits es **muy importante**, porque nos permite **recordar** lo que ha ocurrido en el **pasado**. Y así **tomar decisiones** sobre lo que hacer en el presente y el futuro.

Y es precisamente por esta **capacidad de recordad** que utilizaremos **este símbolo** para **representar un biestable** en Icestudio:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/intro-02.png)

Los biestables son los que guardan las **notificaciones** de lo que ocurre en nuestro circuito. Como un biestable sólo puede **almacenar 1 bit**, se usará para **registrar** sólo **1 notificación**

Aprenderemos a **manejar biestables** usando la **intuición**, y haciendo **muchos ejemplos** de su uso. La mejor manera de aprender es **practicar**. ¡Vamos a ello!

# Eventos y notificaciones

En nuestros circuitos ocurren **eventos**: pulsación de un botón, detección de un objeto por parte de un sensor IR, que dos números sean iguales, que haya transcurrido cierto tiempo, que una operación se ha terminado de realizar... 

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/intro-03.png)

Definimos **evento** como un **cambio en una señal**. Así por ejemplo, al cambiar el estado de un **pulsador** de NO estar apretado a pulsarse, aparece un **cambio de 0 a 1** en su señal. Este cambio es un **evento**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/intro-04.png)

Hay dos tipos de cambio, **de 0 a 1**, también llamado **flanco de subida**, y de **1 a 0**, denominado **flanco de bajada**. Cuando soltamos el pulsador se genera otro evento, pero esta vez el cambio de la señal es de 1 a 0 (flanco de bajada)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/intro-05.png)

Hasta ahora, los **eventos** los hemos **mostrado en LEDs**, y en otros **periféricos de salida**, como los servos. Sólo hemos visualizado el **presente**. Con los biestables podemos **registrar los eventos**, para **recordarlos**

### Ejemplo 1: Encender un LED con pulsador, sin biestable

Retomaremos el circuito "Hola mundo" para **encender un LED** al apretar **un pulsador**, del [Tutorial 9](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-9:-Pulsadores-y-entradas). 

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/intro-06.png)

Lo **cargamos** y lo **probamos**

[![Click to see the youtube video](http://img.youtube.com/vi/8UH14Mup2JU/0.jpg)](https://www.youtube.com/watch?v=8UH14Mup2JU)

Funciona como esperábamos: es un circuito muy sencillo y muy conocido. Pero vamos a fijarnos en **lo que está ocurriendo**: en el **LED** se está reflejando **lo que ocurre en el presente**, en este momento. Mirando el LED sabemos el estado del pulsador. Pero **no sabemos nada** de lo que ha ocurrido en el **pasado**. Necesitamos usar **biestables** para ello

# Biestables con Set y Reset

Los **biestables** nos permiten **registrar** los eventos y **notificarlos**. Para recordar cosas lo primero que hacemos es **registrarlas**. Es la **operación SET** de los biestables. Los móviles nos lo marcan con las **notificaciones** que vemos en la parte superior: al mirarlas sabemos que hay mensajes pendientes, que sucedieron en el pasado, y que todavía no han sido leidos

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/Biestable-RS-01.png)

La segunda operación es la de **borrado de las notificaciones**. En el caso de la lectura de mensajes en el móvil, las notificaciones desaparecen una vez que los hemos leído. Es la **operión RESET** de los biestables

Así, nuestro biestable es un circuito con **dos entradas**: Set y Reset. Una para **registrar el evento**, y la otra para **borrarlo**. Y tienen **una salida**: nos indica la **notificación**. Si está a **0** es que **no ha ocurrido el evento**. Si está a **1** es que hay **una notificación pendiente**

## Ejemplo 2: Notificación de botón apretado

Vamos a hacer un circuito para **registrar** y **notificar** el evento de **botón apretado**. Conectamos el pulsador a la **entrada SET** del biestable y la su **salida** a un **LED**: de esta forma veremos en el LED el estado del biestable: Si está **encendido** es que el **pulsador ha sido apretado** en el pasado. Si está apagado es que no se ha pulsado desde la última vez que lo borramos

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/Biestable-RS-02.png)

Es necesario conectar la **entrada de RESET** para **borrar la notificación pendiente** y volver al estado inicial. Esto lo hacemos conectándola al **pulsador interno SW1**

**Cargamos** el circuito y lo **probamos**:

[![Click to see the youtube video](http://img.youtube.com/vi/Qadxbefl4k8/0.jpg)](https://www.youtube.com/watch?v=Qadxbefl4k8)

En cuanto se **aprieta el pulsador**, el biestable **registra el evento** y se pone su **salida** a **1**. Aunque soltemos el pulsador, la notificación seguirá estando: recuerda que el **botón se ha apretado**. Como sólo tiene **memoria de 1 bit**, sólo puede recordar **un evento**, por lo que no puede distinguir si el pulsador ha sido apretado una o varias veces. Con el otro pulsador **borramos la notificación**

## Banderas (Flags)

Los **biestables con Set y Reset**, como el que hemos usado en el **ejemplo 2**, funcionan como **banderas** o **indicadores** (Conocidos como *flags* en inglés).  Es una técnica que se usa también en **programación**, donde se definen **variables** que permiten registrar la ocurrencia de un evento. Según el valor de estos flags, el programa hace una acción u otra

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/Biestable-RS-03.png)

Con la **entrada SET** ponemos la **bandera** a **1**, para señalar que ha ocurrido el evento. Con **RESET** la ponemos a **cero**. Es un comportamiento muy sencillo, pero **muy potente**, y nos permitirá hacer muchísimas cosas, como veremos en los **ejemplos de aplicación**

# Ejemplos de aplicación

Vamos a practicar el **pensamiento hardware** con biestables. Aplicaremos la misma idea del **ejemplo 2** a otros ejemplos

## Ejemplo 3: Encender un LED con sensor IR, sin biestable

Partiremos del **mismo circuito del ejemplo 1**, pero conectando un **sensor de infrarrojos** (IR) en vez de un pulsador. Tiramos un cable para mostrar el **estado del sensor** en el **LED**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/ejemploIR-02.png)

El **montaje** es el siguiente. Colocamos el **sensor IR** y el **LED externo**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/ejemploIR-01.jpg)

Lo **cargamos** y lo **probamos**. Es un ejemplo que ya conocemos. En el LED se muestra el estado **presente** del sensor. Sólo cuando hay un objeto delante del sensor, se enciende el LED. Cuando no hay nada, se apaga

[![Click to see the youtube video](http://img.youtube.com/vi/WnUfGfjhTY4/0.jpg)](https://www.youtube.com/watch?v=WnUfGfjhTY4)

## Ejemplo 4: Notificación de presencia

Añadimos un **biestable** al ejemplo anterior para **capturar el evento de objeto detectado**, y **notificarlo** en un **LED**. Ahora, el LED se enciende cuando se detecta un objeto, y permance encendido. Nos está indicando que en algún momento del **pasado**, el sensor **ha detectado** un objeto

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/ejemploIR-03.png)

En el montaje incluimos un **pulsador externo** para **rearmar** el detector y **borrar** la notificación

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/ejemploIR-04.jpg)

Lo **cargamos** y lo **probamos**

[![Click to see the youtube video](http://img.youtube.com/vi/XOACBbBHbxY/0.jpg)](https://www.youtube.com/watch?v=XOACBbBHbxY)

## Ejemplo 5: Sistema automático de subida y bajada de barrera

En el ejercicio 2 del [Tutorial 16](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/VIDEO-16:-Sensores-de-Infrarrojos-(IR)) propusimos hacer una **barrera** que se levantase cuando llegase un **vehículo**, y que se cerrase cuando no lo detectase.  Se trataba de un **circuito combinacional**, usando un único **sensor de IR**. Aunque era muy divertido, la barrera era poco funcional

Mejoraremos ese ejercicio. Incluiremos **dos sensores de IR**, que generan los eventos: **Ha llegado un vehículo** y **Vehículo ha entrado en recinto**. El **sensor 1** está colocado en **la entrada**, y detecta los **vehículos** que **quieren entrar** en el recinto. El **sensor 2** está colocado dentro del recinto, y detecta los vehículos que **han entrado** en el recinto

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/barrera-01.png)

El **funcionamiento de la barrera** es el siguiente. Cuando llega un vehículo, lo detecta el **sensor 1** y la barrera se abre. El vehículo entra. Una vez dentro, el **sensor 2** lo detecta y cierra la barrera. Se muestra en esta **animación**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/barrera-02.gif)

Queremos diseñar un **circuito controlador** que haga que la barrera se mueva de esta forma. ¿Cómo sería?

Utilizaremos un **biestble** para representar el **estado de la barrera**. Cuando esté a **1**, la barrera estará **levantada**, y cuando esté a **0** **bajada**. El **sensor 1** emite el evento "Ha llegado vehículo. Cuando esto ocurre, queremos que la barrera pase al **estado de levantada**, por lo que lo conectamos a la entrada **SET** del biestable, para registrar el evento. El **sensor 2** emite el evento "Vehículo dentro". Cuando esto ocurre hay que **bajar la barrera**, por lo que lo conectamos a la entrada de **RESET**. Por último conectamos la **salida del biestable** al **servo** que maneja la barrera. ¡Listo! Fácil, ¿no?

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/barrera-03.png)

Este es el **montaje**. En la **izquierda** se encuentra el **sensor 1**, de detección de los coches que quieren entrar. En la **derecha** el **sensor 2**, para detectar los que ya están dentro. Y en el **centro** el **serv**o que sube y baja la **barrera**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/barrera-04.png)

Lo **cargamos** y lo **probamos**. En este **vídeo** de Youtube se muestra su funcionamiento

[![Click to see the youtube video](http://img.youtube.com/vi/a9gnKUaNNQw/0.jpg)](https://www.youtube.com/watch?v=a9gnKUaNNQw)

En esta **simulación-animación** se muestra el circuito y lo que está ocurriendo en su interior mientras el vehículo se desplaza y activa los sensores de infrarrojos

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/barrera-05.gif)

## Ejemplo 6: Caja fuerte con apertura con código

Retomaremos el ejemplo de la apertura de una **caja fuerte** con un código, que ya vimos en los tutoriales [12](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-12:-Interruptores-y-pulsadores-externos), [17](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/VIDEO-17:-Puertas-l%C3%B3gicas:-OR) y el ejericio 2 del [19](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-19:-Circuitos-combinacionales)

Añadiremos un **biestable** para que **la cerradura permanezca abierta** una vez que el código sea correcto y se pulse el **botón de abrir**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/caja-fuerte-01.png)

El **panel** tiene **4 interruptores** para introducir **el código** (en binario), un **pulsador** para **abrir** la caja y otro para **cerrarla**. Hay **dos LEDs**, uno **rojo** que indica que la caja está cerrada y uno **verde** que se enciende cuando está abierta. En esta **animación** se muestra en funcionamiento

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/caja-fuerte-02.gif)

¿Cómo sería el circuito?. Lo diseñaremos por partes. Usaremos un **biestable** para almacenar el **estado de la caja**: 0-cerrada, y 1-abierta. Cuando el biestable pase a valer 1, la caja estará abierta, y se abrirá la puerta a través del servo. También se encenderá el **LED verde**. Cuando está cerrada, el **LED rojo** está encendido, el verde apagado y el servo en la posición de cerrado

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/caja-fuerte-03.png)

Ahora nos falta la otra parte del circuito. La caja se abrirá cuando se produzca un **evento de apertura de caja**. Esto se consigue cuando se producen a la vez otros dos eventos: uno de **código correcto** y otro de **pulsación del botón de abrir**. Por eso se usa una **puerta AND** que llega a la entrada **SET** del biestable

Por otro lado, el **botón de cerrar** se conecta a la entrada de **RESET del biestable**. Cada vez que se aprieta, el biestable pasa a valer **0** y se cierra la caja

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/caja-fuerte-04.png)

Para detectar el **código** usamos un **circuito combinacional** a partir de una **tabla de verdad**. Sus salidas son siempre 0 excepto cuando por los interruptores llega el **código 1010**. Modificando esta tabla cambiamos el **código de apertura**. El **circuito completo** es el siguiente:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/caja-fuerte-05.png)

Este es el **montaje del circuito**, para realizar las pruebas. Se incluyen los **4 interruptores externos**, los **dos pulsadores**, los **dos LEDs** y **un servo** que representa la **puerta de la caja**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/caja-fuerte-06.png)

Lo **cargamos** y lo **probamos**. En este **vídeo** se puede ver su **funcionamiento** en acción

[![Click to see the youtube video](http://img.youtube.com/vi/AiVJN9NTNDc/0.jpg)](https://www.youtube.com/watch?v=AiVJN9NTNDc)

En esta **simulación-animación** se muestra lo que está ocurriendo en el circuito

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/caja-fuerte-07.gif)

## Ejemplo 7: Alarma antirrobo

Diseñaremos una alarma **antirrobo** para una joyería o museo. Un **sensor de presencia** detectará que un objeto no sea robado. Si alguien se lo lleva, la **alarma se disparará** y se activarán dos **sirenas**, una acústica y otra luminosa

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/alarma-01.png)

Inicialmente la alarma está desconectada. Para ponerla en marcha, primero **colocamos el objeto a proteger** y luego apretamos el **botón de activar**. En ese momento el **LED verde** empezará a **parpadear** para indicar que está activada. En cualquier momento se puede desactivar pulsando el **botón de desactivar**

Si estando la almarma activada alguien **sustrae el objeto**, se **disparará** y empezará a sonar la sirena acústica y a parpadear el **LED rojo**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/alarma-02.gif)

¿Cómo sería el circuito?

Empezaremos por las partes que ya conocemos. Los circuitos que hacen **sonar la alarma** y **parpadear el LED** ya los conocemos. Con ellos creamos los bloques **Sirena** y **Baliza**, que están disponibles en la colección del tutorial 25, en el menú **Varios/Accesorios**

La **sirena** tiene una entrada de habilitación. Cuando se pone a **1** empieza a **sonar**. El sonido se lo componen dos señales cuadradas de **1Khz** y **2Khz**, que se alternan a la frecuencia de **4Hz**

La **baliza** también tiene una **entrada de habilitación** para hacer que funcione al activarse. Simplemente hace **parpadear el LED** conectado a su salida a la frecuencia de **2Hz**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/alarma-03.png)

Para nuestra alarma antirrobo usaremos **2 biestables**: uno para notificar que la alarma **está activada** y otro para indicar que se **ha disparado**

La **alarma se activa** si está **colocado** el objeto a proteger (el sensor detecta el objeto) y se **aprieta** el **botón de activar**. Se **desactiva** pulsando el **botón de desactivar**. El circuito que **implementa** esta parte es el siguiente:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/alarma-04.png)

La **alarma se dispara** si está **activada** y se **sustrae el objeto**, es decir, si mientras está activada el sensor de infrarrojos **deja de detectar** el objeto. Una vez disparada, se puede **apagar** con el mismo pulsador de desactivar. Esto lo **modelamos** con el siguiente circuito:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/alarma-05.png)

La **salida** de este biestable la usamos para **activar la Sirena** y **la baliza**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/alarma-06.png)

Sólo nos queda por hacer el **circuito de control del LED verde**. Cuando la alarma está **apagada**, muestra el estado del sensor de infrarrojos: se enciende si hay objeto y se apaga cuando no está. Esto nos permite saber cuándo está el objeto bien colocado. Cuando la alarma está **activada**, el LED se pone a parpadear a 1Hz. Usamos un **multiplexor de 2 a 1** seleccionado mediante el **biestable 1**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/alarma-07.png)


El **circuito completo** es el siguiente


![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/alarma-08.png)

Este es el **montaje** en el panel de corcho. El objeto a proteger es un coche de juguete :-)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/alarma-09.jpg)

Lo **cargamos** y lo **probamos**. En este **vídeo** se muestra en funcionamiento

[![Click to see the youtube video](http://img.youtube.com/vi/6yUS0LooX5Q/0.jpg)](https://www.youtube.com/watch?v=6yUS0LooX5Q)

Y en esta **animación-simulación** se pueden ver los que ocurre **dentro del circuito**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/alarma-10.gif)

# Conclusiones

Los **biestables** nos permiten que los circuitos tengan un **estado** interno. Parten de un **estado inicial** (Por ejemplo, alarma desactivada). Las **entradas** cambian este estado, almacenando unos o ceros en sus biestables. Y a partir de este estado, se generan las **salidas**. Esta es una idea **muy importante**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/conclusiones-1.png)

La combinación de biestables con circuitos combinacionales produce un nuevo tipo de circuitos llamados **secuenciales**. Con ellos podemos diseñar **Autómatas finitos**, también llamados **máquinas de estados**. Estos circuitos sirven para muchas cosas, entre ellas para implementar las **unidades de control** de los **microprocesadores**

Aunque existen **técnicas formales** para el **diseño de autómatas**, nosotros usaremos un enfoque más **informal**, que nos permita **desarrollar la intución**. Nuestros circuitos no serán los óptimos, pero serán muy intuitivos. Una vez desarrollada esta capacidad de **pensar en hardware**, nos resultará más fácil aprender las técnicas formales

# Ejercicios propuestos (25 BitPoints)

Ver los detalles de los ejercicios y las **entregas** en el menú **Archivos/Ejemplos/2-Ejercicios** de la colección de este tutorial

**Resumen**:

* **Ejercicio 25.1** (Total **5 Bitpoints**): Captando la atención de Franky

Colocar **dos sensores de infrarrojos**. Franky se quedará mirando siempre al último que se haya activado. Si se detecta algo por la derecha, girará su cuello hacia la derecha y permanecerá en esa posición. Si detecta algo por la izquierda, girará el cuello a la izquierda y permancerá en esa posición. Colocar también **dos LEDs**, uno a la derecha y otro a la izquierda. Según en la posición en la que esté mirando Franky, se iluminará uno u otro

En esta **animación** se muestra el funcionamiento pedido

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/ejercicio-1.gif)

* **Ejercicio 25.2** (Total **5 Bitpoints**):  **Alarma de presencia**

Sistema de alarma de detección de intrusos. Se usarán **dos sensores IR** para detectar la llegada de un intruso. Cuando cualquiera de los dos sensores se active, la alarma se **disparará** y empezarán a sonar dos tonos, de 1Khz y 2Khz alternativamente a la frecuencia de 4Hz, y dos LEDs parpadearán intermitentemente a 2Hz. La alarma estará sonando hasta que se **desactive**. Para su desactivación será necesario introducir una **clave de 3 bits** mediante **3 interruptores externos** y apretar el **pulsador de desactivación**. El código de desactivación es **101**

En este **vídeo de youtube** se muestra el funcionamiento pedido

[![Click to see the youtube video](http://img.youtube.com/vi/YHQ2nBD1S8s/0.jpg)](https://www.youtube.com/watch?v=YHQ2nBD1S8s)

* **Ejercicio 25.3** (Total **10 Bitpoints**): Juego: ¡Primero en pulsar!

Diseñar un circuito para jugar al juego de **primero en pulsar**, en el que **gana** el jugador que aprieta  
antes el pulsador. Hay **dos jugadores**. Cada uno tiene **un pulsador** y un **LED externos**. Cuando el **árbitro** termine de formular una pregunta, el jugador que apriete el pulsador antes ganará, y podrá reponderla. Para ello,  
el circuito debe **encender el LED del jugador que primero aprieta el pulsador**, y cuando esto ocurre, **anular el pulsador del otro jugador**. Para apagar el LED del ganador, se aprieta el **pulsador SW1**. Hay un **tercer LED** que **parpadea a 1Hz**, indicando que el circuito está **esperando** a los jugadores aprieten sus pulsadores

En este **vídeo de youtube** se muestra el funcionamiento pedido

[![Click to see the youtube video](http://img.youtube.com/vi/Ient0K6_2YY/0.jpg)](https://www.youtube.com/watch?v=Ient0K6_2YY)

* **Ejercicio 25.4** (**5 Bitpoints**). Ejercicio Libre. Premiar la creatividad. **Entregar** por redes sociales o github: Pantallazos, enlaces, vídeos, etc...


# Ejercicios entregados

## Josep Montoliu (Klarojms)

### Ejercicio 25.1

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/blob/master/Tutorial-25/klarojms/Ejercicio%201-1.png)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/XXy24nj4dTg/0.jpg)](https://www.youtube.com/watch?v=XXy24nj4dTg)

### Ejercicio 25.2

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-25/klarojms/Ejercicio%202-1.png)

* **Otra versión**, con bloques de la colección:

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-25/klarojms/Ejercicio%202-3.png)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/tFwcBCXJkew/0.jpg)](https://www.youtube.com/watch?v=tFwcBCXJkew)

### Ejercicio 25.3

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-25/klarojms/Ejercicio%203-1.png)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/yGcb-L4tnI0/0.jpg)](https://www.youtube.com/watch?v=yGcb-L4tnI0)

### Ejercicio 25.4

* **Metrónomo**

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-25/klarojms/Ejercicio%204-1.png)

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-25/klarojms/Ejercicio%204-2.png)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)](https://www.youtube.com/watch?v=KEyQu3PYaBc)


## Federico Coca (@fgcoca)

### Ejercicio 25.1
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-25/fgcoca/Ejercicio-1/Ejercicio25_1%20%E2%94%80%20P.png)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/hqcQ7XnkKlc/0.jpg)](https://www.youtube.com/watch?v=hqcQ7XnkKlc)

### Ejercicio 25.2
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-25/fgcoca/Ejercicio-2/Ejercicio25_2%20%E2%94%80%20P.png)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/8jRppUC9bfg/0.jpg)](https://www.youtube.com/watch?v=8jRppUC9bfg)

### Ejercicio 25.3
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-25/fgcoca/Ejercicio-3/Ejercicio25_3%20%E2%94%80%20P.png)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/6St0hDa0Qmc/0.jpg)](https://www.youtube.com/watch?v=6St0hDa0Qmc)

## Viriato (@SrViriato)

### Ejercicio 25.1
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-25/Viriato/Ejercicio-25-1/Captura%20de%20pantalla%20-2018-08-17%2020-49-10.png)

* [Vídeo en Twitter](https://twitter.com/SrViriato/status/1030766777809231873)

### Ejercicio 25.2
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-25/Viriato/Ejercicio-25-2/Captura%20de%20pantalla%20-2018-08-18%2017-17-20.png)

* [Vídeo en Twitter](https://twitter.com/SrViriato/status/1030833012634775552)


### Ejercicio 25.3
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-25/Viriato/Ejercicio-25-3/Captura%20de%20pantalla%20-2018-08-19%2017-05-43.png)

* [Vídeo en Twitter](https://twitter.com/SrViriato/status/1030871896018116609)

### Ejercicio 25.4
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-25/Viriato/Ejercicio-25-4/Captura%20de%20pantalla%20-2018-08-17%2019-04-03.png)


# Autor

* [Juan González-Gómez](https://github.com/Obijuan) (Obijuan)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/logos-urjc-gsyc-peloto-jderobot.png)

# Licencia

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/attribution-share-alike-creative-commons-license.png)

# Créditos y agradecimientos

* Icon used on image [intro-01.png](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-25/intro-01.png) made by [Freepik](https://www.flaticon.es/autores/freepik) from [www.flaticon.com](https://www.flaticon.es/icono-gratis/carretilla-elevadora_3736)

* Dibujo Diamante: [Wikipedia](https://es.m.wikipedia.org/wiki/Archivo:Twemoji_1f48e.svg)

* Altavoz: Icono diseñados por [Freepik](http://www.freepik.com) en [www.flaticon.com](https://www.flaticon.es/). Licencia:  [Creative Commons BY 3.0](http://creativecommons.org/licenses/by/3.0/)

* Palma mano: Icono diseñados por [Freepik](http://www.freepik.com) en [www.flaticon.com](https://www.flaticon.es/). Licencia:  [Creative Commons BY 3.0](http://creativecommons.org/licenses/by/3.0/)

* Baliza luminosa: Icono diseñados por [Freepik](http://www.freepik.com) en [www.flaticon.com](https://www.flaticon.es/). Licencia:  [Creative Commons BY 3.0](http://creativecommons.org/licenses/by/3.0/)

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



