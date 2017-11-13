![]()

# Vídeo

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

Haz click en la imagen para ver el **vídeo en Youtube**

# Descripción

TODO

# Colección

**Academia-Jedi-HW-06.zip**: Colección para este tutorial. Descargar e instalar 

# Contenido

* [Configurando las colecciones](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-6:-Bombeando-bits#configurando-las-colecciones)
  * [Eliminando las colecciones no usadas](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-6:-Bombeando-bits#eliminado-colecciones-no-usadas)
* [Superposición de Circuitos](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-6:-Bombeando-bits#superposici%C3%B3n-de-circuitos)
* [Ejemplo 1: Circuitos en paralelo](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-6:-Bombeando-bits#ejemplo-1-circuitos-en-paralelo)

# Configurando las colecciones

Lo primero que haremos será **instalar** la colección usada en este tutorial: **Academia-Jedi-HW-06.zip**,  y seleccionarla. Si hemos hecho el tutorial 5 y sus ejercicios, tendremos estas **colecciones instaladas**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-06/Configuracion-01.png)

Observamos que hay una opción nueva en el menú: **Bombeo**

## Eliminado colecciones no usadas

Opcionalmente podemos **eliminar las colecciones** que no vamos a usar. Yo lo hago aquí para enseñaros cómo eliminarlas, pero no es necesario hacerlo para continuar con el tutorial. Nos vamos al menú **Herramientas/Colecciones/Eliminar**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-06/Configuracion-02.png)

y nos aparecerán todas las que tenemos instaladas. Seleccionamos la que queremos eliminar, por ejemplo la de Makespace-17

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-06/Configuracion-03.png)

Nos aparece un mensaje de confirmación. Pinchamos en **OK**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-06/Configuracion-04.png)

Y sale la notificación de que la **colección ha sido eliminada**. Repetimos el proceso con el resto de colecciones salvo la que usaremos la que acabamos de instalar. El menú de las colecciones nos queda así

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-06/Configuracion-05.png)

Si tenemos colecciones intaladas no hay problema. Esto es sólo un ejemplo de borrado :-)

# Superposición de circuitos

El **pensamiento hardware** tiene dos características que le diferencian del pensamiento algorítmico:

* **Se piensa en espacio**: los circuitos ocupan un espacio físico
* **Las cosas suceden en paralelo**

Una consecuencia muy útil de esto es el poder **combinar** fácilmente **circuitos independientes**. Imaginemos que tenemos un circuito que **toca una melodía**, y otro que hace que un **robot siga la línea negra**. Los dos funcionan por separado. Si los metemos en la misma FPGA, tendremos un robot que **sigue la línea** mientras **toca música**

Esto lo podemos ver gráficamente usando el **circuito de encender** un led que ya conocemos. El **circuito 1** enciende el **LED 7**. Lo cargamos en la placa y vemos que funciona correctamente

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-06/Paralelo-01.png)

Ahora hacemos el **circuito 2**, que enciene el **LED0**. Lo cargamos en la placa y vemos que este LED se enciende
![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-06/Paralelo-02.png)

Ahora hacemos un **circuito 3** que es la **combinación** de los dos anteriores: El circuito 1 al lado del circuito 2. Encenderá **simultánemente** los leds 7 y 0

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-06/Paralelo-03.png)

A esta propiedad la llamaremos **superposición de circuitos**. Sólo es aplicable a circuitos que son **independientes**. Aplicando esta superposición, conseguimos que un circuito tenga la suma de comportamientos de sus integrantes

# Ejemplo 1: Circuitos en paralelo

Vamos a comprobar la **superposición de circuitos**. Primero abrimos el **circuito 1** desde los ejemplos, accediendo a **Archivo/Ejemplos/1-Ejemplos/1-Circuitos-Paralelo/Ejemplo-01-LED7-on**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-06/Circuitos-paralelos-01.png)

Nos aparece el **circuito 1**, que simplemente encenderá el **LED7**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-06/Circuitos-paralelos-02.png)

Lo **cargamos en la placa** para ver su funcionamiento

![](https://raw.githubusercontent.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/master/wiki/Tutorial-04/ledon-17.jpg)

**Abrimos una ventana nueva** de Icestudio, con la opción **Archivo/Nuevo**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-06/Circuitos-paralelos-03.png)

Nos aparece una ventana nueva de Icestudio, en **blanco**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-06/Circuitos-paralelos-04.png)

Abrimos el **circuito 2** desde los ejemplos, accediendo a **Archivo/Ejemplos/1-Ejemplos/1-Circuitos-Paralelo/Ejemplo-02-LED0-on**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-06/Circuitos-paralelos-05.png)

y nos aparece el **circuito 2**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-06/Circuitos-paralelos-06.png)

Ahora lo **cargamos** en la placa, y comprobamos que se enciende el **LED 0**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-06/icezum-led0.jpg)

-Copy&paste. Cargar  

TODO

# Ejemplo 2: Led parpadeante

TODO

# Ejemplo 3: LEDs parpadeando a diferentes velocidades

TODO


# Ejercicios propuestos (x BitPoints)

* **Ejercicio 1** (Total **x Bitpoints**): TODO. **Entregar** por redes sociales, con mención a **@obijuan_cube**
  * x pantallazo del circuito (1 bitpoint)
  * x Foto de la Icezum Alhambra con el circuito cargado (1 bitpoint)
  * Entrega adicional por Github (1 bitpoint) 

* **Ejercicio 2** (Total **x Bitpoints**): TODO. **Entregar** por redes sociales, con mención a **@obijuan_cube**
  * x pantallazo del circuito (1 bitpoint)
  * x Foto de la Icezum Alhambra con el circuito cargado (1 bitpoint)
  * Entrega adicional por Github (1 bitpoint) 

* **Ejercicio 3** (Total **x Bitpoints**): TODO. **Entregar** por redes sociales, con mención a **@obijuan_cube**
  * x pantallazo del circuito (1 bitpoint)
  * x Foto de la Icezum Alhambra con el circuito cargado (1 bitpoint)
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

# Enlaces

* [Repositorio con las colecciones de la Academia Jedi de Hardware](https://github.com/Obijuan/Academia-Jedi-Hw)

# FAQs

* **¿Dónde puedo conseguir la placa Icezum Alhambra?**

Pueden conseguir una desde [Alhambrabits](https://alhambrabits.com/buy/)

* **¿Cómo aprendo a manejar github?**

Hay mucha información en internet. En su momento hice este Tutorial: [Github y FreeCAD](http://www.iearobotics.com/wiki/index.php?title=Tutorial:_Github_y_Freecad) para enseñar a manejarlo. Los ejemplos están hechos con ficheros de FreeCAD, sin embargo, lo que se enseña es genérico. También vale para las entregas de los ejercicios del tutorial de Electrónica digital para makers


