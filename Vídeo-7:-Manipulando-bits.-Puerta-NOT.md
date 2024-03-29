![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-07/portada-tutorial-7.png)

# Vídeo

[![Click to see the youtube video](http://img.youtube.com/vi/xgdiBnzz4XQ/0.jpg)](https://www.youtube.com/watch?v=xgdiBnzz4XQ&index=7&list=PLmnz0JqIMEzXaeYVzf2TfTzRekPIVoljw)

Haz click en la imagen para ver el **vídeo en Youtube**

# Descripción

Los circuitos digitales realizan **tres operaciones** con los bits: **transporte**, **almacenamiento** y **manipulación**. Veremos un ejemplo de **manipulación sencilla** usando la puerta lógica **NOT**, con la que haremos que dos leds **parpadeen alternativamente**


# Colección

[Academia-Jedi-HW-07.zip](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/Contenido/Tutorial-07/Academia-Jedi-HW-07.zip): Colección para este tutorial. Descargar e instalar 

# Contenido

* [Todo es número](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-7:-Manipulando-bits.-Puerta-NOT#todo-es-n%C3%BAmero)
* [Circuitos digitales](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-7:-Manipulando-bits.-Puerta-NOT#circuitos-digitales)
* [Elementos de un circuito digital](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-7:-Manipulando-bits.-Puerta-NOT#elementos-de-un-circuito-digital)
* [Manipulación de bits: Puerta NOT](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-7:-Manipulando-bits.-Puerta-NOT#manipulaci%C3%B3n-de-bits-puerta-not)
* [Ejemplo 1: Leds parpadeando a la vez](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-7:-Manipulando-bits.-Puerta-NOT#ejemplo-1-leds-parpadeando-a-la-vez)
* [Ejemplo 2: Leds parpadeando alternativamente](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-7:-Manipulando-bits.-Puerta-NOT#ejemplo-2-leds-parpadeando-alternativamente)
* [Funcionamiento del circuito](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-7:-Manipulando-bits.-Puerta-NOT#funcionamiento-del-circuito)
* [Tabla de verdad](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-7:-Manipulando-bits.-Puerta-NOT#tabla-de-verdad)
* [Bits imprimibles en 3D](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-7:-Manipulando-bits.-Puerta-NOT#bits-imprimibles-en-3d)
* [Ejercicios propuestos (11 Bitpoints)](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-7:-Manipulando-bits.-Puerta-NOT#ejercicios-propuestos-11-bitpoints)
* [Ejercicios entregados](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-7:-Manipulando-bits.-Puerta-NOT#ejercicios-entregados)
  * [Federico Coca](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-7:-Manipulando-bits.-Puerta-NOT#federico-coca)
  * [Jorge Lobo](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-7:-Manipulando-bits.-Puerta-NOT#jorge-lobo)
  * [Ricardo Gómez (eagleman)](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-7:-Manipulando-bits.-Puerta-NOT#ricardo-g%C3%B3mez-3agl3man)
* [Autor](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-7:-Manipulando-bits.-Puerta-NOT#autor)
* [Licencia](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-7:-Manipulando-bits.-Puerta-NOT#licencia)
* [Créditos y agradecimientos](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-7:-Manipulando-bits.-Puerta-NOT#cr%C3%A9ditos-y-agradecimientos)
* [Enlaces](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-7:-Manipulando-bits.-Puerta-NOT#enlaces)
* [FAQs](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-7:-Manipulando-bits.-Puerta-NOT#faqs)

# Todo es número

Vivimos en un **mundo digital**: televisión digital, radio digital, circuitos digitales...Es la era digital ¿Pero esto qué significa? Simplemente que **TODO son números**. Toda la información que recibimos son números. Las imágenes que nos llegan por la televisión son en realidad números. Los sonidos que escuchamos son números. Las Apps que ejecutamos en nuestros móviles son números. Los documentos que enviamos por internet son ... ¡Números!

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-07/intro-01.png)

Pero es que además, gracias al [segundo teorema de Nyquist](https://es.wikipedia.org/wiki/Teorema_de_muestreo_de_Nyquist-Shannon), tenemos garantizado matemáticamente que **cualquier señal analógica se puede convertir a números** y posteriormente ser reconstruidas. De esta forma, tenemos garantizado que cualquier señal la podemos convertir a números **¡¡[Los pitagóricos](https://es.wikipedia.org/wiki/Pitag%C3%B3ricos) estarían orgullosos!!**  ¡¡Tenían razón!! :-)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-07/intro-02.jpg)

# Circuitos digitales

Los **circuitos digitales** son los que trabajan con **números**. Y sólo con números. Sólo realizan tres operaciones con los números: **Almacenar**, **transportar** y **manipular**

Estos circuitos reciben números por sus **entradas**, realizan estas operaciones, y producen otros números como **salida**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-07/intro-03.png)

Ahora bien, con la tecnología actual, los chips trabajan internamente con **bits**. Son elementos de información que sólo pueden estar en dos estados: 1 ó 0. Y se usan bits porque son muy fáciles de implementar a partir de **transistores** que se fabrican muy fácilmente y barato con **silicio**

Cualquier **número** se puede representar mediante **dígitos binarios** (bits). De esta forma podemos redefinir los chips digitales como: **Aquellos componentes que almacenan, transportan y manipulan bits**. Y sólo hacen eso

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-07/intro-04.png)

Por sus **entradas** llegan **bits**, que son manipulados, almacenados y transportados, y como **resultado** se obtienen más bits que se sacan por las **salidas**

# Elementos de un circuito digital

Cualquier **circuito digital**, por muy complejo que sea, sólo está formado por **tres elementos básicos**: Los **cables**, para transportar bits, las **puertas lógicas** para manipularlos y los **biestables** para almacenarlos

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-07/intro-05.png)

Los **cables** ya los hemos utilizado para transportar los bits desde dentro del chip hasta sus patas de salida, para **encender** los leds o hacerlos **parpadear**. Lo siguiente será aprender a manipularlos

# Manipulación de bits: Puerta NOT

La manipulación más sencilla se realiza con la **puerta NOT**, que **transforma** un **bit a 1 en 0**, y al contrario, **un bit 0 en 1**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-07/puerta-not-01.png)

Esta puerta tiene una **entrada** por la izquierda, por donde entra un bit, y una **salida** por la derecha por donde aparece el bit invertido. En esta **animación** se muestra su funcionamiento

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-07/puerta-not-anim.gif)

En la app **circuit scramble**, que vimos en el [tutorial 1](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-1:-Electr%C3%B3nica-digital-para-todos), la **puerta not** aparece a partir del **nivel 5**. El símbolo es diferente al usado típicamente, pero el funcionamiento es el mismo

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-07/puerta-not-02.png)

# Ejemplo 1: LEDs parpadeando a la vez

Haremos primero un ejemplo de **cómo hacer parpadear 2 leds a la vez**. Lo haremos con los **LEDs 0** y **7**. Ya sabemos hacerlo, y se planteó como ejercicio en el [tutorial 6](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-6:-Bombeando-bits). Lo resolveremos aquí y aprenderemos de paso a tirar **varios cables** desde la misma salida

Partimos del circuito que ya conocemos que hace **parpadear un led** a la velocidad de 1Hz (Lo podemos cargar rápidamente desde el menú **Archivo/Ejemplos/1-Ejemplos/1-LED parpadeante**)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-07/led-alternantes-01.png)

Colocamos un bloque de **salida** asociado al **LED 0**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-07/led-alternantes-02.png)

Desde la salida de un bloque es posible **sacar más de un cable**. Nos colocamos en la salida del corazón de 1Hz hasta que el cursor se ponga en **forma de cruz**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-07/led-alternantes-03.png)

Tiramos **un cable** como ya sabemos, pinchando con el botón izquierdo y arrastrando. Nos aparece un **nuevo cable**, unido al original

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-07/led-alternantes-04.png)

Nos situamos en la entrada del bloque de salida y **soltamos** el botón para **fijar el cable**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-07/led-alternantes-05.png)

Así es como queda el circuito, con un corazón conectado a los leds para que **parpadeen a la vez**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-07/led-alternantes-06.png)

El cable que acabamos de colocar se **puede mover**. Para ello nos situamos encima. Su **aspecto** cambia

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-07/led-alternantes-07.png)

Dejamos pulsado el botón izquierdo y **movemos el cable** hacia la izquierda

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-07/led-alternantes-08.png)

Soltamos el botón y ya tenemos el cable **recolocado**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-07/led-alternantes-09.png)

**Cargamos** el circuito para probarlo. Los **LEDs 0** y **7** parpadean a la vez

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-07/leds-parpadeo-fase.gif)

# Ejemplo 2: Leds parpadeando alternativamente

Vamos a utilizar la **puerta NOT** para crear una **sirena luminosa** haciendo que dos leds **parpadeen alternativamente**

Partimos del ejemplo creado anteriormente, al que también tenemos acceso desde el menú **Archivo/Ejemplos/1-Ejemplos/2-Leds-parpadeantes-igual**. Primero **eliminamos** el cable que conecta el corazón con el LED0. Para ello situamos el ratón encima del cable: nos aparece una **X roja**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-07/led-alternantes-10.png)

Nos situamos **sobre** ella

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-07/led-alternantes-11.png)

y la **apretamos**, eliminando el cable

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-07/led-alternantes-12.png)

Colocaremos una **puerta NOT**. Nos vamos al menú **Puertas/Not**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-07/led-alternantes-13.png)

Y **colocamos** la puerta a la izquierda del bloque de salida del **LED 0**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-07/led-alternantes-14.png)

Ahora **tiramos un cable** desde el corazón a la entrada de la puerta y **otro** desde su salida al LED 0

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-07/led-alternantes-15.png)

**Cargamos** el circuito en la placa, para probarlo

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-07/led-alternantes-16.gif)

Vemos cómo los leds **parpadean alternativamente**: primero uno y luego otro

# Funcionamiento del circuito

El circuito de los leds alternantes funciona de la siguiente manera: Cuando el corazón bombea un bit a 1, se transmite por el cable al **LED 7** y por el otro cable llega a la entrada de la **puerta NOT**. El bit se convierte a 0 y se saca por el **LED 0**. Por ello, el LED 7 se enciende y el LED 0 se apaga
https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-07/leds-alternantes-bits-anim.gif
![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-07/funcionamiento-leds-alternantes-01.png)

Cuando el corazón bombea un **bit 0** ocurre lo contrario. El 0 llega al **LED 7**, apagándolo, y por el otro cable llega a la puerta NOT, convirtiéndose en un 1 y encendiendo el **LED 0**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-07/funcionamiento-leds-alternantes-02.png)

El **funcionamiento completo** se muestra en esta **animación**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-07/leds-alternantes-bits-anim.gif)

# Tabla de verdad

El funcionamiento del circuito queda descrito de manera más concisa usando una **tabla de verdad**, en la que se muestra el resultado de todas sus **salidas** segun el valor del bit bombeado por el corazón

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-07/funcionamiento-leds-alternantes-03.png)

En la **columan de la izquierda** están puestos los dos valores que puede tomar el corazón: **0** y **1**. Y en las dos columnas de la derecha los valores que salen por las salidas y que llegan a los LEDs 7 y 0 respectivamente 

# Bits imprimibles en 3D

Para realizar simulaciones de los **circuitos lógicos** se puede utilizar estas [Monedas Bits](https://github.com/Obijuan/3D-parts/wiki/Monedas-Bit) imprimibles

![](https://raw.githubusercontent.com/Obijuan/3D-parts/master/2017-11-26-Printable-bits/images/Moneda-bit-1.jpg)

# Ejercicios propuestos (11 BitPoints)

Ver los detalles de los ejercicios y las entregas en el menú **Archivos/Ejemplos/2-Ejercicios** de la colección de este tutorial

**Resumen**:

* **Ejercicio 1** (Total **3 Bitpoints**): Hacer un circuito digital que haga parpadear
alternativamente los LEDs pares y los impares a una velocidad de una vez por segundo

* **Ejercicio 2** (Total **3 Bitpoints**): Hacer un circuito digital que haga parpadear
alternativamente los LEDs 3 y 4 a la velocidad de 4 veces por segundo. Los leds 0 y 1 
parpadean a la vez, una vez por segundo y los leds 7 y 6 lo hacen también una vez por
segundo pero alternativamente con los leds 0 y 1

* **Ejercicio 3** (Total **3 Bitpoints**): Hacer el circuito indicado en el enunciado de la colección, probarlo en la placa y obtener su tabla de verdad

* **Ejercicio 4** (**2 Bitpoints**). Ejercicio Libre. Premiar la creatividad. **Entregar** por redes sociales o github: Pantallazos, enlaces, vídeos, etc...

# Ejercicios entregados

## Federico Coca

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-7/fgcoca/Ejercicio-1/Ejercicio7_1.png)

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-7/fgcoca/Ejercicio-2/Ejercicio7-2.png)

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-7/fgcoca/Ejercicio-3/Ejercicio7-3.png)

## Jorge Lobo

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-07/entregas/Lobotic-1.jpg)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-07/entregas/lobotic-2.jpg)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-07/entregas/lobotic-3.jpg)

## Ricardo Gómez (3agl3man)

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-7/eagleman/Ejercicio_7.1.PNG)

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-7/eagleman/Ejercicio_7.2.PNG)

![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-7/eagleman/Ejercicio_7.3.PNG)

# Autor

* [Juan González-Gómez](https://github.com/Obijuan) (Obijuan)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/logos-urjc-gsyc-peloto-jderobot.png)

# Licencia

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/attribution-share-alike-creative-commons-license.png)

# Créditos y agradecimientos

# Enlaces

* [Repositorio con las colecciones de la Academia Jedi de Hardware](https://github.com/Obijuan/Academia-Jedi-Hw)
* [Monedas Bit imprimibles](https://github.com/Obijuan/3D-parts/wiki/Monedas-Bit)

# FAQs

* **¿Dónde puedo conseguir la placa Icezum Alhambra?**

Pueden conseguir una desde [Alhambrabits](https://alhambrabits.com/buy/)

* **¿Cómo aprendo a manejar github?**

Hay mucha información en internet. En su momento hice este Tutorial: [Github y FreeCAD](http://www.iearobotics.com/wiki/index.php?title=Tutorial:_Github_y_Freecad) para enseñar a manejarlo. Los ejemplos están hechos con ficheros de FreeCAD, sin embargo, lo que se enseña es genérico. También vale para las entregas de los ejercicios del tutorial de Electrónica digital para makers



