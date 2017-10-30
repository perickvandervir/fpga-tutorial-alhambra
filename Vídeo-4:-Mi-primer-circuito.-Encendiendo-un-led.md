[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

Haz click en la imagen para ver el **vídeo en Youtube**

(En construcción)

# Descripción

TODO

# Contenido

* [Un lienzo en blanco](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-4:-Mi-primer-circuito.-Encendiendo-un-led#un-lienzo-en-blanco)
* [Haciendo el circuito hola mundo](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-4:-Mi-primer-circuito.-Encendiendo-un-led#haciendo-el-circuito-hola-mundo)
  * [Bits](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-4:-Mi-primer-circuito.-Encendiendo-un-led#bits)
  * [Construyendo el circuito](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-4:-Mi-primer-circuito.-Encendiendo-un-led#construyendo-el-circuito)
  * [Probando el circuito](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-4:-Mi-primer-circuito.-Encendiendo-un-led#probando-el-circuito)
* [Analizando el circuito](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-4:-Mi-primer-circuito.-Encendiendo-un-led#analizando-el-circuito)
* [Ejercicios propuestos](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-4:-Mi-primer-circuito.-Encendiendo-un-led#ejercicios-propuestos-10-bitpoints)
* [Ejercicios entregados](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-4:-Mi-primer-circuito.-Encendiendo-un-led#ejercicios-entregados)
* [Autor](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-4:-Mi-primer-circuito.-Encendiendo-un-led#autor)
* [Licencia](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-4:-Mi-primer-circuito.-Encendiendo-un-led#licencia)

TODO


# Un lienzo en Blanco

¡Hola! Soy obijuan y en este microtutorial vamos a crear **nuestro primer circuito digital**: encenderemos un **LED**. Lo se, es muy simple. Pero lo utilizaré de excusa para explicar algunos conceptos

Vamos a crear un **circuito físico**, con existencia real, que estará dentro de la **FPGA** de la [Icezum Alhambra](https://github.com/FPGAwars/icezum/wiki), ese chip grande que está en el centro. Encenderemos los LEDs, que están en la parte superior izquierda de la placa

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-04/Alhambra-01.png)

La FPGA la podemos ver como un **lienzo en blanco**, donde pintaremos nuestro **circuito digital**. Es importante localizar exactamente dónde estará nuestro circuito, para no perder la perspectiva

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-04/Alhambra-02.png)

Para este tutorial sólo usaremos los **LEDs** de la Icezum Alhambra. En este dibujo hemos puesto sólo las **partes que nos interesan**: los LEDs, la FPGA, la placa y **los cables** que unen las patas de la FPGA con los LEDS

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-04/Alhambra-03.png)

Los **cables** entre la FPGA y los leds **están fijos**. Se encuentra en la **placa de circuito** impreso de la Icezum Alhambra. Los **LEDS** se dibujan en blanco para indicar que están **apagados**, y la FPGA también está en color blanco, para resaltar el hecho de que **no tiene ningún circuito** en su interior todavía (No está configurada)

Abrimos **Icestudio**. Es **nuestro lienzo** donde haremos los **circuitos digitales**. Se corresponde con el interior de la FPGA

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-04/Alhambra-05.png)

# Haciendo el circuito Hola Mundo

Comenzaremos con el **circuito más sencillo posible**: un circuito digital que enciende el **LED7** de la Icezum alhambra

## BITs

Los circuitos digitales trabajan con **BITs**, que son **elementos de información** que pueden estar en dos estados: **uno** o **cero**. Estos dos estados pueden representar difernetes cosas, como por ejemplo *encendido* - *apago*, *verdadero* o *falso*, *arriba* o *abajo*, *cara* o *Cruz*, *5 voltios* - *0 voltios*, el *ying* o el *yang*, *culo* o *codo* :-)

En este ejemplo usaremos el significado **1 = encendido**. Para encender el LED sólo hay que colocar un bit a 1, y hacer que salga por la pata de la FPGA correspondiente al LED 7. Para **transportar** el bit desde el interior hacia la pata usaremos un **cable**.

(Animación bit)

## Construyendo el circuito

Primero colocaremos el **bit a 1**. Nos vamos al menú superior **Bit** y pinchamos en el **1**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-04/ledon-01.png)

Nos aparecerá un **bloque azul**, con el cursor del ratón en forma de mano encima

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-04/ledon-02.png)

Lo movemos hasta una zona de la pantalla y **picamos** con el ratón. Se nos colocará el **Bit 1**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-04/ledon-03.png)

Ahora tenemos que colocar el bloque que se corresponde con la **pata** de la FPGA por donde saldrá el bit 1 al exterior. Nos vamos al menú **Básico/Salida**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-04/ledon-04.png)

Y nos aparece una ventana pidiendo el **nombre** que le queremos dar a la **salida**.

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-04/ledon-05.png)

De momento no ponemos nada, y le damos al **OK**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-04/ledon-06.png)

Colocamos el bloque a la derecha del Bit 1 y **picamos**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-04/ledon-07.png)

Ahora **tiramos el cable**. Situamos el ratón en la derecha del Bit 1 hasta que el cursor tenga forma de **cruz**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-04/ledon-08.png)

Apretamos el botón y **arrastramos**. Saldrá el cable

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-04/ledon-09.png)

Nos situamos en la parte izquierda del bloque de salida y **soltamos** el botón

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-04/ledon-10.png)

Ahora los dos bloques estarán **unidos por el cable**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-04/ledon-11.png)

Sólo nos queda **seleccionar** por qué pata de la FPGA queremos que salga el Bit a 1. Pinchamos en el **desplegable** del bloque de salida y pinchamos en **LED7**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-04/ledon-12.png)

Ahora nos aparecerá la etiqueta **LED7** en el interior del bloque de salida. **Ya tenemos nuestro circuito listo**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-04/ledon-13.png)

## Probando el circuito

Conectamos la Icezum Alhambra al ordenador y nos vamos al menú **Herramientas/Cargar**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-04/ledon-14.png)

Al apretar comienza la **síntesis** y **carga del circuito** en la FPGA. Aparece una **notificación** en la parte inferior derecha

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-04/ledon-15.png)

y al cabo de unos segundos nos aparecen **dos notificaciones** nuevas. Una **verde** para indicar que ya se ha realizado la carga y otra con los **recursos que ha ocupado el circuito**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-04/ledon-16.png)

Y ahora en la icezum Alhambra podemos ver cómo el **LED 7** está encendido

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-04/ledon-17.jpg)

# Analizando el circuito

Lo que ha sucedido al **cargar** es que el circuito hecho en Icestudio se ha **transferido a la FPGA**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-04/Alhambra-06.png)

Y este es el **circuito físico** que tenemos ahora

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-04/Alhambra-07.png)

**¡Un Chip con nuestro circuito en su interior!**. Pero tiene existencia física real. Es decir, que no es una simulación, ni hay debajo un microcontrolador que haga el trabajo. No. Es un circuito real. Es hardware puro.

El **bit a 1** está conectado a la pata de la FPGA que llega al LED 7. De esta manera, el Bit a 1 (que en realidad es una tensión de 3.3v) sale por la pata, llega al LED 7 y lo **enciende**

Es un circuito constante. El led permanecerá encendido hasta que **apaguemos** la palca. Una vez la volvamos a alimentar, la FPGA se reconfigurará y aparecerá otra vez el circuito

Si ahora **modificamos** el circuito para encender el **LED 3**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-04/Alhambra-08.png)

y volvemos a cargarlo, lo que ocurre en el interior es que la FPGA se **reconfigura** para que aparezca un **nuevo circuito** que saque el Bit a 1 por la pata correspondiente al **LED 3**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-04/Alhambra-09.png)

# Ejercicios propuestos (10 BitPoints)

* **Ejercicio 1** (2 Bitpoints): xx Sacar **2 pantallazos**, xx. Enviar las capturas por redes sociales (mención a @Obijuan_cube). Se concederá **1 Bitpoint adicional** por subirlas al [repositorio de entregas de github](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs)

* **Ejercicio 2** (2 Bitpoints): xx. Sacar **2 pantallazos**, xx. Enviar las capturas por redes sociales (mención a @Obijuan_cube). Se concederá **1 Bitpoint adicional** por subirlas al [repositorio de entregas de github](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs)

* **Ejercicio 3** (1 Bitpoint): xx. Sacar 1 pantallazo. Enviar la capturas por redes sociales (mención a @Obijuan_cube). Se concederá **1 Bitpoint adicional** por subirlas al [repositorio de entregas de github](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs)

* **Ejercicio 4** (Hasta 2 Bitpoints): Ejercicio Libre. Premiar la creatividad. Entrega por redes sociales o por github 

# Ejercicios entregados



# Autor

* [Juan González-Gómez](https://github.com/Obijuan) (Obijuan)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/logos-urjc-gsyc-peloto-jderobot.png)

# Licencia

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/attribution-share-alike-creative-commons-license.png)

# Créditos y agradecimientos

# Enlaces

# FAQs



