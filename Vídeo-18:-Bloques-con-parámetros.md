![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-18/Portada/Tut-18-portada.png)

# Vídeo

[![Click to see the youtube video](http://img.youtube.com/vi/9Ex0x2_ZZzQ/0.jpg)](https://www.youtube.com/watch?v=9Ex0x2_ZZzQ&index=17&list=PLmnz0JqIMEzXaeYVzf2TfTzRekPIVoljw)

Haz click en la imagen para ver el **vídeo en Youtube**

# Descripción

Hasta ahora hemos utilizado bloques específicos que hacían una función concreta. Aprenderemos a usar los **bloques genéricos**, que nos permiten crear **bloques específicos** mediante la asignación de valores a sus **parámetros**. Lo aplicaremos al manejo de tres nuevos componentes paramétricos: el **corazon**, el **servobit** y el **motorbit**. Esto nos permitirá fijar la frecuencia, el periodo, el ángulo del servo o la velocidad a valores diferentes de los establecidos por defecto

# Colección

[Academia-Jedi-HW-18.zip](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-18/Collection/Academia-Jedi-HW-18.zip): Colección para este tutorial. Descargar e instalar 

# Contenido

* [Introducción](#introducci%C3%B3n)
* [Corazón paramétrico](#coraz%C3%B3n-param%C3%A9trico)
  * [Ejemplo 1: parpadeo de un LED a 1Hz](#ejemplo-1-parpadeo-de-un-led-a-1hz)
  * [Ejemplo 2: Estableciendo la frecuencia a 4Hz](#ejemplo-2-estableciendo-la-frecuencia-a-4hz)
  * [Circuitos reales y parámetros](#circuitos-reales-y-par%C3%A1metros)
  * [Bloques fijos](#bloques-fijos)
  * [Ejemplo 3: Fijando el periodo](#ejemplo-3-fijando-el-periodo)
  * [Ejercicio 1: Tocar las notas DO,RE,MI,FA con dos switches](#ejercicio-1-tocar-las-notas-doremifa-con-dos-switches)
* [Servobit paramétrico](#servobit-param%C3%A9trico)
  * [Tabla de valores para los parámetros (PX)](#tabla-de-valores-de-los-par%C3%A1metros-px)
  * [Ejemplo 4: Cambiando las posiciones al servobit](#ejemplo-4-cambiando-las-posiciones-al-servobit)
  * [Bloques servobit fijos](#bloques-servobit-fijos)
  * [Ejercicio 2: Movimiento de un servo con ángulos pequeño y grande](#ejercicio-2-movimiento-de-un-servo-con-%C3%A1ngulos-peque%C3%B1o-y-grande)
  * [Ejemplo 5: Pinza mecánica](#ejemplo-5-pinza-mec%C3%A1nica)
* [Motorbit paramétrico](#motorbit-param%C3%A9trico)
  * [Ejemplo 6: reduciendo las velocidades de motorbit](#ejemplo-6-reduciendo-las-velocidades-de-motorbit)
  * [Ejercicio 3: Servo con dos velocidades en cada sentido](#ejercicio-3-servo-con-dos-velocidades-en-cada-sentido)
* [Ejercicios propuestos (20 Bitpoints)](#ejercicios-propuestos-20-bitpoints)
* [Ejercicios entregados](#ejercicios-entregados)
  * [Joaquín Cubillo (jcubilloarr)](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-18:-Bloques-con-par%C3%A1metros#joaqu%C3%ADn-cubillo-jcubilloarr)
* [Autor](#autor)
* [Licencia](#licencia)
* [Enlaces](#enlaces) 
* [Preguntas frecuentes](#preguntas-frecuentes)

# Introducción

Hay dos **técnicas** usadas para el diseño de **circuitos complejos**: la **composición** y la **parametrización**. Con ellas nuestros diseños estárán mejor estructurados y los podremos **reutilizar** más fácilmente. 

Mediante la **composición** construirmos bloques a partir de otros más sencillos, creando **jerarquías**. El situado en lo más alto es la **entidad superior** (*top entity*) cuyas entradas y salidas se corresponden con los **pines de la FPGA**. Los bloques intermedios se pueden **reutilizar** bien dentro del propio diseño o bien en otros

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-18/intro-1.png)

En esta **animación**, se parte la **entidad superior** de un circuito de ejemplo, y se profundiza hasta el **nivel 4**. Cada bloque superior se descompone a su vez en otros bloques en el siguiente nivel de profundidad

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-18/intro-03.gif)

La otra técnica es la creación de **bloques paramétricos**. El objetivo es diseñar **bloques genéricos**, que se puedan **especializar** por medio de la **asignación** de valores a sus **parámetros**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-18/intro-2.png)

Un ejemplo es el bloque genérico **corazón**, que veremos en el siguiente apartado, y que produce un bombeo de bits a una frecuencia genérica. Esta frecuencia se establece simplemente cambiando el valor de su parámetro

En este nos familiarizaremos con el uso de los **bloques parámetricos** y aprenderemos a **fijar sus valores**, dejando para más adelante el cómo diseñar mediante composición y parametrización

# Corazón paramétrico

Hasta ahora hemos utilizado **corazones con frecuencia fija**, para bombear bits en nuestros diseños. Hemos usado mucho los de 1Hz y 2Hz, cuyos bloques son:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-18/corazon-param-1.png)

El **bloque corazón paramétrico** es como el mostrado a continuación. Es muy parecido a los anteriores, con la diferencia de que tiene un **"cable"** en la parte superior. Es el **parámetro frecuencia**, al que le tendremos que asignar un valor (en hercios)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-18/corazon-param-2.png)

## Ejemplo 1: Parpadeo de un LED a 1Hz

Haremos un circuito para hacer parpadear el **LED0** a la frecuencia de **1Hz**, usando un **corazón paramétrico**. El componente lo encontramos en el menú **Varios/Bombeo/Corazon_Hz**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-18/corazon-param-3.png)

Nos falta por asignarle un valor al parámetro, pero **por defecto** vale **1Hz**. Esto lo podemos saber viendo la **información del bloque** que aparece cuando dejamos el puntero del ratón sobre el bloque, durante unos segundos

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-18/corazon-param-4.png)

## Ejemplo 2: Estableciendo la frecuencia a 4Hz

Para establecer una **frecuencia** diferente, en **Hz**, tenemos que dar un valor al parámetro. Para ello usaremos un elemento nuevo: el **bloque constante**, que se encuentra en **Básico/Constante**. Igual que al colocar los pines de entrada o salida, nos pide un nombre para el valor que estamos introduciendo. Lo llamaremos, por ejemplo, **HZ** para representar que es un valor en hercios. A continuación lo unimos a su parámetro mediante **un cable**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-18/corazon-param-5.gif)

Ahora ya podemos asignarle cualquier valor. Nos metemos en la caja de texto del bloque HZ y ponemos el **valor de la frecuencia**, en hercios (y usando números enteros). En este ejemplo estamos usando un valor de **4**. 

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-18/corazon-param-6.png)

Si ahora sintetizamos y **cargamos el circuito**, vemos cómo efectivamente el LED parpadea **4 veces** más rápido.  ¡Hemos probado nuestro primer **circuito paramétrico**! En este **Vídeo en Youtube** lo puedes ver en funcionamiento

[![Click to see the youtube video](http://img.youtube.com/vi/oieg43fxA80/0.jpg)](https://www.youtube.com/watch?v=oieg43fxA80)

## Circuitos reales y parámetros

Los **bloques paramétricos** son una herramienta para el **diseñador de circuitos**, pero en realidad **no** tienen **existencia física**. Es decir, que lo que se **sintetiza** en la FPGA **no** es el circuito genérico, sino el **circuito particular** que surge al utilizar el parámetro indicado.

Las **herramientas de síntesis** (invocadas por Icestudio) parten del circuito genérico, le aplican el parámetro y obtienen el **circuito particular**, que es el que se sintetiza en la FPGA

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-18/corazon-param-7.png)

Esto es importante por los siguientes motivos:

* El **"cable"** que une el parámetro con el circuito es **ficticio**. No tiene exitencia física. En la FPGA ese cable no aparecerá. Y lo mismo el parámetro. En el circuito particular NO hay parámetro

* El circuito genérico tiene un **tamaño desconocido**. Es al aplicarle el parámetro y convertirlo en particular cuando tiene un **tamaño real**. Y además, este tamaño **dependerá el parámetro**. Parámetros distintos darán lugar, en general, a circuitos particulares con tamaños distintos

## Bloques fijos

Llamamos **bloques fijos**, o **constantes** a los que **no tienen parámetros**. Por ejemplo el bloque "Corazón de 1Hz", que hemos estado usando para generar una señal de 1Hz. Es un bloque fijo, porque esta frecuencia no es un parámetro, sino que está prefijada al valor 1

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-18/corazon-param-8.png)

Los bloues fijos son muy **cómodos**. Se colocan y listo. Y **reducen la complejidad visual** del circuito. Sin embargo es muy incómodo tener que crear circuitos específicos para cada uno de estos bloques. Si por ejemplo queremos tener dos corazones de frecuencias fijas, 1 y 2Hz, tendríamos que crearnos estos dos bloques de manera independiente (duplicando el trabajo). Una opción mejor es partir del **bloque corazón genérico**, y obtener los **bloques fijos** a partir de él, mediante **composición**, asignando valores diferentes a su parámetros

Asi es como se han creado los **corazones de frecuencia fija** que se encuentra en **Varios/Bombeo/Fijos**. Para comprobarlo no hay más que hacer **doble click** en uno de ellos, para **entrar** y ver de qué otros bloques está compuesto. Lo podemos ver en esta **animación**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-18/corazon-param-9.gif)

## Ejemplo 3: Fijando el periodo

También tenemos un **corazón paramétrico** que nos permite **fijar el periodo**, en vez de la frecuencia. Está disponible en el menú **Varios/Bombeo/Corazón_seg**, y por **defecto** tiene asignado un periodo de **1 segundo**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-18/corazon-param-10.gif)

Como ejemplo, haremos **parpadear el LED0** con un periodo de **10 segundos**. Colocamos el componente **Corazon_Seg** y ponemos una **constante** con el valor de **10** para asignársela a su **parámetro**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-18/corazon-param-11.png)

Al **probar** el circuito veremos que inicialmente el LED está **apagado** durante **5 segundos**, y luego se **enciende** durante otros **5** (completando un periodo de 10 segundos). El ciclo se repite indefinidamente

## Ejercicio 1: Tocar las notas DO,RE,MI,FA con dos switches

Diseñar un circuito digital que pueda tocar **4 notas** diferentes: Do-re-mi-fa 
Las notas se seleccionan mediante *dos interruptores externos**. Al apretarse un **pulsador externo** sonará la nota seleccionada

Las **frecuencias** de las notas a tocar son:

* **Do**:  131 Hz
* **Re**:  147 Hz
* **Mi**:  165 Hz
* **Fa**:  175 Hz

Consejo: Utilizar un multiplexor 4:1

* En este **Vídeo en youtube** se muestra su funcionamiento

[![Click to see the youtube video](http://img.youtube.com/vi/vpLthAkkWCM/0.jpg)](https://www.youtube.com/watch?v=vpLthAkkWCM)

# Servobit paramétrico  

Para mover los servos a **dos posiciones** hemos estado usando el bloque **servobit-90**. Estas posiciones estaban fijadas en el propio bloque. Con el componente **servobit paramétrico** las podemos fijar a los valores que queramos. Los parámetros se denominan **P0** y **P1**, correspondientes las posiciones del servo para sus dos valores de entrada: 0 y 1 respectivamente

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-18/servobit-param-1.png)

Los dos parámetros, **P0** y **P1** (A los que nos referiremos genéricamente como **Px**) están en unidades de **micro-segundos** (μs). Cada posición se encuentra siempre entre un valor máximo **Pmax** y uno mínimo, **Pmin**, que dependen del tipo de servo.

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-18/servobit-param-2.png)

Como ya vimos al hablar del servobit, la posición del servo queda determinada por la **anchura del pulso** que se mande. Esta posición, en microsegundos, es la que usamos para dar valores a P0 y P1. En la mayoría de los servos, la **posición central** se alcanza con **pulsos de 1.5ms** (1500 μs). Si la anchura es menor, el ángulo apunta hacia la derecha, y si es mayor, a la izquieda

## Tabla de valores de los parámetros Px

En la siguiente **tabla** se resumen los valores **máximos** y **mínimos** de los parámetros para los diferentes servos. También se incluyen las posiciones **P0** y **P1** que se usan en el **servobit-90**

Es **MUY IMPORTANTE** NO dar valores mayores de PMAX ni menores de PMIN. Esto llevaría al servo a posiciones fuera de su rango, y lo podríamos dañar

| Servo               | Pmax(μs)  | Pmin(μs) |  P1(μs)  |  P0(μs)  |
|---------------------|-----------|----------|----------|----------|
|  **Futaba 3003**    |  2410     |  380     |  1670    |   820    |
|  **Emax-ES808A**    |  2550     |  580     |  2000    |  1000    |
|  **TowerPro SG-90** |  2350     |  500     |  2000    |  1000    |

## Ejemplo 4: Cambiando las posiciones al servobit

Como **ejemplo** usaremos un **servobit paramétrico** para cambiar el ángulo en un **Futaba 3003**. Primero colocamos el componente, que lo encontraremos en **Varios/Servo/Futaba3003/Servobit**. Su entrada la conectamos a un **pulsador** y la salida al servo. Comprobaremos su funcionamiento primero con los **parámetros por defecto**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-18/servobit-param-3.png)

El sevo se mueve **igual** que cuando usábamos el **servobit-90**. Ahora le añadimos los **bloques constantes** para poner valores diferentes a **P0** y **P1**, por ejemplo sus valores extermos:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-18/servobit-param-4.png)

Si **cargamos** ahora el circuito para probarlo, veremos que el arco que recorre el servo es mucho más amplio que antes

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-18/servobit-param-5.png)

## Bloques Servobit fijos

Igual que hicimos con el **corazón paramétrico**, podemos definir bloques en los que el **ángulo** entre las posiciones P0 y P1 esté **fijado**, y no haya que usar parámetros. Estos bloques están formados a partir de un **bloque genérico** al que se le han asignado unos **valores fijos**. Es el caso de los componentes Servobit-90, cuyo ángulo entre P0 y P1 se ha fijado en 90 grados

En esta **animación** vemos el interior del bloque **Servobit-90** para servos **Emax-ES08A**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-18/servobit-param-6.gif)

Todavía no sabemos cómo crear esos bloques, pero lo aprenderemos en los **tutoriales venideros**

## Ejercicio 2: Movimiento de un Servo con ángulos pequeño y grande

Diseñar un circuito digital para mover un servo a dos posiciones diferentes,  
controladas por un **pulsador**. Mediante un **interruptor externo** seleccionaremos  
entre dos modos: **ángulo pequeño** y **ángulo grande**.  En el modo ángulo pequeño,  
el servo se mueve entre dos posiciones, separadas un ángulo pequeño, menor de 90.  
En el modo ángulo grande, el servo se moverá entre sus **dos extremos**

* En este **vídeo en Youtube** se puede ver un ejemplo de funcionamiento

[![Click to see the youtube video](http://img.youtube.com/vi/uMLxEvIMIeM/0.jpg)](https://www.youtube.com/watch?v=uMLxEvIMIeM)

## Ejemplo 5: Pinza mecánica

Como ejemplo de **aplicación** de nuevo bloque **servobit paramétrico**, lo usaremos para abrir y cerrar esta [Pinza mecánica](http://www.iearobotics.com/wiki/index.php?title=Freecad:_Pinza_mecanica), imprimible en 3D, que tiene un **mecanismo paralelo** que le permite agarrar objetos

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-18/servobit-param-7.png)

Las piezas se **imprimen en 3D** y se ensamblan. La parte superior queda así:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-18/servobit-param-8.jpg)

y por la parte posterior se coloca un **micro-servo**, atornillado a la **base de la pinza**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-18/servobit-param-9.jpg)

Haremos un circuito para poder **abrir** y **cerrar** la pinza usando un **pulsador externo**. Sólo hay que colocar el servobit paramétrico y dar los **valores** adecuados a sus **parámetros**. En **P1** especificamos el valor para que la **pinza esté abierta**. Estos valores dependen de cómo hayamos colocado el servo a la pinza, y en general serán diferentes para cada pinza. En mi caso, el valor de **P1** es de **2050 μs**. En **P0** colocamos el valor para que la **pinza esté cerrada**: **1500 μs**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-18/servobit-param-10.jpg)

En este **vídeo en youtube** se muestra un **ejemplo** de funcionamiento

[![Click to see the youtube video](http://img.youtube.com/vi/lTvd8dPOzsI/0.jpg)](https://www.youtube.com/watch?v=lTvd8dPOzsI)

# Motorbit paramétrico  

Con el controlador **Motorbit** que hemos usado hasta ahora las velocidades usadas tanto para el sentido horario como el antihorario eran las máximas que podía el servo. Sin embargo, con el **motorbit paramétrico** se puede establecer velocidades menores, para cada sentido

El que usaremos es para el **servo SM-S4303R**, pero al ser parámetrico, se puede adaptar a cualquier otro servo de **rotación continua** que tenga **20ms** de periodo de señal (que son las mayoría)

El bloque parámetrico se llama igual: motorbit, y se encuentra en el mismo lugar que el anterior: en el menú **Varios/Motor/SM-S4303R/Motorbit**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-18/motorbit-param-1.png)

Tiene tres parámetros: **V0**, **V1** y **V2**. Los tres representan valores de la **anchura del pulso** en **microsegundos**, igual que en el caso del servobit (Los servos de rotación continua usan la misma señal PWM que los servos normales)

* **V0**: Anchura del pulso de la posición que hace que el **servo esté parado**. Típicamente vale **1500 microsengudos** (1.5ms)
* **V1**: Anchura del pulso de la posición en la que el servo se mueve en **sentido horario**. Para el servo **SM-S4303R**, valores mayores o iguales a **1900** hacen que se mueva en **sentido horario** a **máxima velocidad**. Valores entre **1900 y 1500** hacen que la **velocidad sea menor**
* **V2**: Anchura del pulso de la posición en la que el servo se mueve en **sentido antihorario**. Valores inferiores o iguales a **1100** hacen que el servo se mueve a la **máxima velocidad** en sentido **antihorario**. Valores entre **1500 y 1100** hacen que la velocidad sea menor (cuanto más cerca de V0 menor es la velocidad)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-18/motorbit-param-2.png)

En esta figura se representan gráficamente los **parámetros** y todos sus posibles valores para el servo **SpringRC SM4303R**. El parámetro más importante es **V0**, que determina el punto en el que el servo está **parado**. **V1** tiene **valores mayores a V0**, para hacer que el servo gire en **sentido horario**. Cuando alcanza el valor **V1max**, la velocidad es **máxima**, en este sentido. Todavía se puede seguir incrementando V1 hasta llegar a **V1limit**, pero la velocidad seguirá siendo la máxima.

Lo mismo sucede con **V2**. Su valor siempre es **menor a V0**, para hacer que gire en sentido antihorario. Cuando su valor llega a **V2min**, la velocidad es máxima, en sentido antihorario. El parámetro se puede seguir decrementando hasta alcanzar **v2limit**, pero la velocidad no variará 

## Ejemplo 6: Reduciendo las velocidades de Motorbit

Como ejemplo vamos a mover el servo de rotación continua **SpringRC SM4303R** a una **velocidad menor** de la que ya conocemos. El escenario que vamos a utilizar es el siguiente: colocremos un **interruptor externo** para establacer el sentido de giro, y un **pulsador** para mover/parar el motor

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-18/motorbit-param-3.jpg)

Primero probamos el **motorbit paramétrico** con sus **valores por defecto**, sin asignar constantes. El motor se moverá igual que en los tutoriales anteriores. El circuito es el siguiente:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-18/motorbit-param-4.png)

Ahora le damos vamos a **V1** y **V2** para **reducir la velocidad**. El parámetro **V0** de dejamos con su **valor por defecto**. Sería necesario cambiarlo si estamos usando modelos de servos diferentes. A **V1** le damos por ejemplo un valor de **1600 μs**. Como es mayor del valor de V0 (1500 μs), se moverá en **sentido horario**, y como es menor de **V1max** (1900 μs) la velocidad será menor a la máxima. Al parámetro **V2** le damos un valor de **1400 μs**, para que se mueva despacio

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-18/motorbit-param-5.png)

Al **cargarlo** en la placa, veremos que funciona igual que antes, pero las dos velocidades, la horaria y la atihorario, son **mucho menores**

## Ejercicio 3: Servo con dos velocidades en cada sentido

Diseñar un circuito digital para mover un servo de **rotación continua** con **dos  
velocidades** diferentes en cada entido. Se utilizarán **dos interruptores externos**  
uno para establecer la **velocidad**: rápida/lenta, y otro para fijar el  
**sentido de giro**: horario/antohorario. Usaremos un **pulsador externo** para que  
el motor se mueva al pulsarlo, o esté parado al soltarlo

* En este **vídeo en Youtube** se puede ver un ejemplo de funcionamiento

[![Click to see the youtube video](http://img.youtube.com/vi/M9iuAXRoF8g/0.jpg)](https://www.youtube.com/watch?v=M9iuAXRoF8g)

# Ejercicios propuestos (20 BitPoints)

Ver los detalles de los ejercicios y las **entregas** en el menú **Archivos/Ejemplos/2-Ejercicios** de la colección de este tutorial

**Resumen**:

* **Ejercicio 1** (Total **5 Bitpoints**): Notas DO-RE-MI-FA

  * El enunciado está en [este apartado](#ejercicio-1-tocar-las-notas-doremifa-con-dos-switches)

* **Ejercicio 2** (Total **5 Bitpoints**): Movimiento de un Servo con ángulos pequeño y grande

  * El enunciado está en [este apartado](#ejercicio-2-movimiento-de-un-servo-con-%C3%A1ngulos-peque%C3%B1o-y-grande)

* **Ejercicio 3** (Total **5 Bitpoints**): Servo con dos velocidades en cada sentido

  * El enunciado está en [este apartado](#ejercicio-3-servo-con-dos-velocidades-en-cada-sentido)

* **Ejercicio 4** (**5 Bitpoints**). Ejercicio Libre. Premiar la creatividad. **Entregar** por redes sociales o github: Pantallazos, enlaces, vídeos, etc...

# Ejercicios entregados

## Joaquín Cubillo (jcubilloarr)

### Ejercicio 1
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-18/jcubilloarr/1.png)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/JjcPB2LBj0U/0.jpg)](https://www.youtube.com/watch?v=JjcPB2LBj0U)

### Ejercicio 2
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-18/jcubilloarr/2.png)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/2KeGQS2FfZU/0.jpg)](https://www.youtube.com/watch?v=2KeGQS2FfZU)

### Ejercicio 3
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-18/jcubilloarr/3.png)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/yO9TQ43rwD4/0.jpg)](https://www.youtube.com/watch?v=yO9TQ43rwD4)

### Ejercicio 4
![](https://github.com/Obijuan/Entregas-Tutorial-Electronica-Digital-FPGAs/raw/master/Tutorial-18/jcubilloarr/4.png)

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi/b1j1Pc9CB_E/0.jpg)](https://www.youtube.com/watch?v=b1j1Pc9CB_E)


## Josep Klaro (klarojms)

### Ejercicio 1
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 2
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 3
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 4
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

## Tercero

### Ejercicio 1
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 2
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 3
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 4
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

