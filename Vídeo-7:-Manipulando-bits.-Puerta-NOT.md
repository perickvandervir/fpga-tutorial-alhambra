![]()

# Vídeo

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

Haz click en la imagen para ver el **vídeo en Youtube**

# Descripción

TODO

# Colección

**Academia-Jedi-HW-07.zip**: Colección para este tutorial. Descargar e instalar 

# Contenido

* [Todo es número](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-7:-Manipulando-bits.-Puerta-NOT#todo-es-n%C3%BAmero)
* [Circuitos digitales](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-7:-Manipulando-bits.-Puerta-NOT#circuitos-digitales)
* [Elementos de un circuito digital](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-7:-Manipulando-bits.-Puerta-NOT#elementos-de-un-circuito-digital)
* [Manipulació de bits: Puerta NOT](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-7:-Manipulando-bits.-Puerta-NOT#manipulaci%C3%B3n-de-bits-puerta-not)
* [Ejemplo: LEDs Alternantes]()

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

Esta puerta tiene una **entrada** por la izquierda, por donde entra un bit, y una **salida** por la derecha por donde aparece el bit invertido

En la app **circuit scramble**, que vimos en el [tutorial 1](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-1:-Electr%C3%B3nica-digital-para-todos), la **puerta not** aparece a partir del **nivel 5**. El símbolo es diferente al usado típicamente, pero el funcionamiento es el mismo

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-07/puerta-not-02.png)

# Ejemplo: LEDs alternantes

Vamos a utilizar la **puerta NOT** para crear una **sirena luminosa** haciendo que dos leds **parpadeen alternativamente**

Partimos del circuito que ya conocemos que hace **parpadear un led** a la velocidad de 1Hz (Lo podemos cargar rápidamente desde el menú **Archivo/Ejemplos/1-Ejemplos/1-LED parpadeante**)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-07/led-alternantes-01.png)


* Añadimos otro led (Ejercicio 1 tutorial 6)
* Colocar puerta NOT
* Bit imprimible, dos caras
* "Simulación"
* Tabla de verdad
* Propuesta de símbolo 
(Meter simbolo de not en el repo de iconos de bloques)

# Ejercicios propuestos (11 BitPoints)

* **Ejercicio 1** (Total **x Bitpoints**): (TODO) **Entregar** por redes sociales, con mención a **@obijuan_cube**
  * x pantallazo del circuito (x bitpoint)
  * x Vídeo del circuito funcionando (x bitpoint)
  * Entrega adicional por Github (1 bitpoint) 

* **Ejercicio 2** (Total **x Bitpoints**): (TODO) **Entregar** por redes sociales, con mención a **@obijuan_cube**
  * x pantallazo del circuito (x bitpoint)
  * x Vídeo del circuito funcionando (x bitpoint)
  * Entrega adicional por Github (1 bitpoint) 

* **Ejercicio 3** (Total **x Bitpoints**): (TODO) **Entregar** por redes sociales, con mención a **@obijuan_cube**
  * x pantallazo del circuito (x bitpoint)
  * x Vídeo del circuito funcionando (x bitpoint)
  * Entrega adicional por Github (1 bitpoint) 


* **Ejercicio 4** (**2 Bitpoints**). Ejercicio Libre. Premiar la creatividad. **Entregar** por redes sociales o github: Pantallazos, enlaces, vídeos, etc...

# Ejercicios entregados

## Primero


## Segundo


## Tercero



# Autor

* [Juan González-Gómez](https://github.com/Obijuan) (Obijuan)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/logos-urjc-gsyc-peloto-jderobot.png)

# Licencia

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/attribution-share-alike-creative-commons-license.png)

# Créditos y agradecimientos

De Gregory Maxwell - From Image:Yin_yang.png, converted to SVG by Gregory Maxwell., Dominio público, https://commons.wikimedia.org/w/index.php?curid=364239

# Enlaces

* [Repositorio con las colecciones de la Academia Jedi de Hardware](https://github.com/Obijuan/Academia-Jedi-Hw)

# FAQs

* **¿Dónde puedo conseguir la placa Icezum Alhambra?**

Pueden conseguir una desde [Alhambrabits](https://alhambrabits.com/buy/)

* **¿Cómo aprendo a manejar github?**

Hay mucha información en internet. En su momento hice este Tutorial: [Github y FreeCAD](http://www.iearobotics.com/wiki/index.php?title=Tutorial:_Github_y_Freecad) para enseñar a manejarlo. Los ejemplos están hechos con ficheros de FreeCAD, sin embargo, lo que se enseña es genérico. También vale para las entregas de los ejercicios del tutorial de Electrónica digital para makers



