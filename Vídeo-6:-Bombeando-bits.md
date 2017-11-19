![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-06/portada-T06.png)

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
* [Ejemplo 2: Led parpadeante](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-6:-Bombeando-bits#ejemplo-2-led-parpadeante)
* [Pensamiento Hardware VS pensamiento Algorítmico](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-6:-Bombeando-bits#pensamiento-hardware-vs-pensamiento-algor%C3%ADtmico)
  * [Led parpadeante con pensamiento algorítmico](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-6:-Bombeando-bits#led-parpadeante-con-pensamiento-algor%C3%ADtmico)
    * [Pregunta reto](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-6:-Bombeando-bits#pregunta-reto)
  * [Led parpadeante con pensamiento hardware](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-6:-Bombeando-bits#led-parpadeante-con-pensamiento-hardware)
* [Ejemplo 3: Leds parpadeando a diferentes velocidades](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-6:-Bombeando-bits#ejemplo-3-leds-parpadeando-a-diferentes-velocidades)

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

Pinchando con el botón izquierdo y **arrastrando** el ratón seleccionamos el circuito completo

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-06/Circuitos-paralelos-07.png)

Al **sortar** el bóton, todos sus componentes quedan seleccionados

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-06/Circuitos-paralelos-08.png)

Nos vamos a la opción **Editar/Copiar** para copiar el circuito

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-06/Circuitos-paralelos-09.png)

Nos vamos a la otra ventana, donde está el **circuito 1**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-06/Circuitos-paralelos-10.png)

Y le damos a la opción **Editar/Pegar**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-06/Circuitos-paralelos-11.png)

Nos aparece el circuito que habíamos copiado, **superpuesto** con el actual

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-06/Circuitos-paralelos-12.png)

Lo **recolocamos** para que se vean bien los dos circuitos

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-06/Circuitos-paralelos-13.png)

y lo **cargamos** en la placa

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-06/icezum-led0-led7.jpg)

Ahora los **dos leds están encendidos**. Este circuito lo hemos creado poniendo dos circuitos **independientes en paralelo**, para mostrar un ejemplo "hola mundo" del **principio de superposición**. En tutoriales venideros aplicaremos este principio a circuitos más complejos

# Ejemplo 2: Led parpadeante

Hasta ahora hemos hecho circuitos donde los bits eran constantes.  En este ejemplo haremos que un **LED** se **encienda** y se **apague** continuamente, con periodo de **un segundo**

Partiremos el ejemplo anterior, al que eliminamos los comentarios de texto y el bit 1 superior. Los bloques se **eliminan** seleccionándos y pulsando la tecla **Supr** o **Delete**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-06/ledp-01.png)

Queremos que el **LED7 parpadee** y que el **LED0** se quede **encendido**

Para hacer que parpadee el LED tenemos que **bombear** bits. Hay que enviar la secuencia de bits 1 - 0 - 1 - 0 ... Eso lo conseguimos con el bloque corazón

Nos vamos al menú **Bombeo** y seleccionamos el **Corazón de 1Hz**. 

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-06/ledp-02.png)

Es un corazón que **bombea bits** a un ritmo de **un bit 1 por segundo**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-06/ledp-03.png)

Al **cargarlo** en la placa obtendremos esto:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-06/ledp-03.gif)

# Pensamiento hardware vs pensamiento algorítmico

El ejemplo de hacer **parpadear un LED** es un clásico. Vamos a analizar cómo se aborda usando el **pensamiento algorítmico** y el **pensamiento hardware**

## Led parpadeante con pensamiento algorítmico

Cuando queremos hacer que **parpadee el LED de Arduino**, usamos este programa

```C
void setup() {
  pinMode(LED_BUILTIN, OUTPUT);
}

void loop() {
  digitalWrite(LED_BUILTIN, HIGH);
  delay(500);                      
  digitalWrite(LED_BUILTIN, LOW); 
  delay(500);
}
```
Hay un **procesador** (cpu), que **ejecuta** las instrucciones de una en una. Primero configura el **pin** para que sea de **salida** (LED_BUILTIN) y luego se entra en el **bucle principal**, que se repite todo el tiempo. 

Las instrucciones que se ejecutan en el **bucle principal** son:

* **Escribir un 1** en el pin de salida para **encender** el led
* Esperar durante medio segundo
* **Escribir un 0** en el pin para apagar el led
* Esperar durante medio segundo

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-06/arduino-anim-01.gif)

### Pregunta reto

El **pensamiento algorítmico** es **muy potente**, pero hay cosas sencillas que son difíciles de implementar con este pensamiento. Aquí lanzo esta pregunta para pensar sobre ello: 


**¿Cómo podemos hacer para que dos leds parpadeen a diferentes velocidades con pensamiento algorítmico?** ¿Y tres leds con velocidades diferentes? ¿Y 10? 

Por supuesto esto es algo que se puede hacer, pero no es trivial ni inmediato para alguien que está empezando. Se requieren **conocimientos avanzados** para entender cómo hacerlo

## Led parpadeante con pensamiento hardware

Para hacer parpadear un led con **pensamiento Hardware** el enfoque es distinto. No pensamos en las instrucciones que hay que darle a un procesador, sino que nos **centramos directamente en los bits** y es un **pensamiento espacial**.

Hay que enviar físicamente una tira de bits, a 1 y a 0. Es decir, hay que **bombear bits**, que se **desplazan** por el **cable** hasta que salgan fuera del chip y lleguen al led. Se muestra gráficamente en este **animación**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-06/bombeo-animation.gif)

Con el **pensamiento hardware** es **muy fácil** responder a la pregunta de cómo hacer que parpadeen dos o más leds a diferentes velocidades. Sólo hay que poner en **paralelo circuitos** con corazones que **bombeen bits** a diferentes velocidades

# Ejemplo 3: LEDs parpadeando a diferentes velocidades

Hacer que varios leds parpadeen a **diferentes velocidades** con pensamiento hardware es muy sencillo. Sólo hay que **poner en paralelo** otro corazón, que bombee bits a una velocidad diferente

Haremos que el **LED 0** parpadee a una velocidad de **4 veces por segundo**, mientras que el **LED 7** lo hará **una vez por segundo**

Partimos del circuito del ejemplo anterior, y añadimos un **corazón de 4Hz** desde el menú **Bombeo/Corazón 4Hz**

(Foto)

**Eliminamos** el bit 1 constante de la parte inferior y lo **sustituimos por el nuevo corazón**. Tiramos el cable para conectarlo al pin de salida LED 0

(foto)

Y lo cargamos:

(animación)


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


