(Enlace al vídeo)

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

## Descripción

TODO

## Explicación

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/intro-01.png)

Hola! Soy obijuan, y en este microtutorial comenzamos el curso sobre **Electrónica digital para makers utilizando FPGAs libres**. Es un curso diferente, totalmente distinto a lo que hayas visto. El objetivo es enseñar **pensamiento hardware** de una forma **práctica**, haciendo circuitos desde el minuto 0.

Estamos acostumbrados al **pensamiento algorítmico**, que es el que usamos cuando programamos, por ejemplo un Arduino. Hay un elemento, el **microprocesador**, que ejecuta las **instrucciones** almacenadas en su memoria. Una detrás de otra, **secuencialmente**. Como programadores tenemos que determinar qué instrucciones usar y en qué orden para que el procesador resuelva un problema o haga lo que nosotros queremos. Pensamos en **tiempo**, y de manera **secuencial**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/intro-02.gif)

Sin embargo, en los circuitos digitales las cosas suceden en **paralelo**. El **pensamiento hardware** es **espacial**. Hay caminos físicos por los que la información pasa de un lugar a otro, y es un **pensamiento paralelo**: Las cosas suceden a la vez. Es similar a una ciudad donde hay coches que se mueven a la vez, en paralelo, siguiendo unas reglas de tráfico

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/intro-03.gif)

Los **chips digitales** son las base de la tecnología actual y se diseñan a partir de **electrónica digital** y **pensamiento hardware**. La electrónica digital es de lo que están hechos los procesadores que programamos. Conocerla nos permite no sólo entender cómo funcionan, sino crear procesadores nuevos. Chips diferentes. Arquitecturas alternativas

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/intro-04.png)

En ciencia y en ingeniería dividimos el conocimiento en **niveles**. El mundo de la electrónica digital está "por debajo" del software. En este dibujo se muestran varios niveles, donde los **átomos** están en la parte inferior y el **software** en la superior

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/intro-05.png)

Cuando trabajamos con un **Arduino** estamos en el **nivel de software** (7), de programación. Los programas se ejecutan sobre un **microprocesador** que está en el nivel inferior (Nivel 6). Los microprocesadores se diseñan con **electrónica digital** (Nivel 5), que es lo que veremos en este tutorial. Por debajo tenemos los **transistores** (Nivel 4) que están hechos a partir de **semiconductores** (Nivel 3), que son **cristales de silicio** (Nivel 2) a los que se introducen impurezas. En el último nivel tenemos los **átomos** (Nivel 1)

En este tutorial estaremos en el **nivel 5**, diseñando **circuitos digitales** de manera práctica, a los que conectaremos **sensores** y **actuadores**, y que físicamente tendrán una apariencia como esta

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/intro-06.jpg)

Este es un ejemplo de una **alarma** que se dispara cuando detecta la **presencia** de algo, a través de un sensor digital de **infrarrojos**. Cuando salta, suena una **sirena**, el **servo** empieza a oscilar y los **leds** comienzan a **parpadear** alternativamente. Cuando se aprieta el **pulsador**, la alarma se para y se rearma. Con el interruptor externo se puede encender o apagar. El circuito digital, creado en [Icestudio](https://github.com/FPGAwars/icestudio), es este

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/intro-07.png)

En muy poco tiempo serás capaz de entender perfectamente este circuito, y realizar los tuyos propios :-)

**¿Cómo se hacen los circuitos digitales?** La manera **clásica** es la siguiente. Primero se **diseña** el circuito usando los componentes de electrónica digital: puertas lógicas, biestables, registros, etc. Luego se **simula** para comprobar que está bien diseñado. Y por último hay que **construirlo físicamente**. Los elementos a usar se encuentra en el interior de los chips. El fabricante te facilita un esquema con todos los componentes que hay en lo chips que vende

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/intro-08.png)

Por ejemplo, en el chip de esta figura hay 4 puertas **NAND**, de 2 entradas. En el mapa podemos ver en qué patas del chip están las entradas de las NAND, y por dónde se conectan sus salidas

Para construir el circuito, necesitamos comprar los chips necesarios, en la tienda o por internet. Para el montaje físico, una opción es usar una **placa de entrenamiento** (protoboard):

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/intro-09.jpg)

Otra opción es **soldarte los componentes** en una placa. Con esto se consigue un prototipo que dura más y no se salen los cables

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/intro-10.png)

Y para placas ya más depuradas, se puede hacer un **PCB** prototipo, que permite hacer tiradas mayores

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/intro-11.jpg)

Sin embargo, nosotros usaremos **FPGAs libres**. Y todo será muchísimo **más fácil** y **más rápido**. Igual de ágil que el desarrollo software. **Sintetizaremos** circuitos reales en pocos segundos

Esta magia se consigue usando unos chips que se llaman **FPGAs**, que tienen en su interior **los tres elementos básicos** para realizar cualquier circuito digital: **puertas lógicas**, **cables** y **biestables**. Pero están sin conectar

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/intro-12.png)

Las FPGAs son como **chips en blanco**. Un lienzo donde podemos hacer cualquier circuito digital. Las uniones son programables, y al establecerlas, la FPGA se **configura** y nuestro circuito aparece. En cuestión de segundos. Decimos que nuestro circuito se ha **sintetizado**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/intro-13.png)

Estas uniones no son permanentes, lo que nos permite meter **muchos circuitos**. Ahora tenemos un circuito, y después podemos sustituirlo por otro circuito

Las FPGAs se conocen desde los años 80, pero era una tecnología privativa, igual que lo eran las impresoras 3D. Esto implicaba que sólo unos pocos tenían acceso a ella, y menos aún conocían sus detalles. A partir de mayo de 2015, el ingeniero austriaco [Clifford Wolf](http://www.clifford.at/) hizo ingeniería inversa de la familia **ICE40 de Lattice**, publicó toda su información ([proyecto icestorm](http://www.clifford.at/icestorm/)) y creó **el primer sintetizador libre de la historia**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/intro-14.png)

A partir de esas herramientas libres, hemos podido desarrollar otras, como Icestudio, que hacen que la síntesis del hardware, y su diseño, estén **accesibles para muchísima más gente**. Y que el aprendizaje de los circuitos digitales sea mucho más rápido y fácil

**¿Por qué aprender a hacer circuitos digitales? ¿Por qué bajar hasta el nivel de la electrónica digital?**

1. **Por aprender**. La electrónica digital son los fundamentos de nuestra sociedad del conocimiento. Internet, los vídeos, las aplicaciones, la música, las películas, los ordenadores, los móviles, las tablets... todo está hecho con electrónica digital. Los fundamentos de todo son este tipo de circuitos. Su conocimiento te da una visión muy amplia del potencial y limitaciones de nuestra sociedad digital

2. **Crear nuevos circuitos**. Conocer como funcionan las cosas a este nivel permiten a personas creativas desarrollar nuevos circuitos electrónicos, diferentes a las tendencias actuales. Nuevas arquitectura. Nuevos paradigmas. Nuevos procesadores. Es algo que desde el nivel del software no podemos hacer, ya que estamos condicionados por el hardware que hay debajo

3. **Aplicaciones más optimizadas**. El estar dos niveles por debajo del software tiene dos grandes ventajas: mayor velocidad y menor consumo. Muchas cosas se pueden hacer por software. Pero si se hacen por hardware, requerirán muchos menos recursos, con lo que consumirán menos, y podrán funcionar a velocidades mucho mayores

4. **Independencia de los fabricantes**. Al hacer un circuito digital, dependes de los chips disponibles en el mercado. Puede que al cabo de varios años, los chips que has usado ya no esté a la venta. Si estos chips los tenemos creados en una FPGA, tenemos garantizado que siempre estarán disponibles

5. **Compartir hardware**. Diseñar circuito digitales, usando FPGAs libres, nos permite compartirlos muy fácilmente, y entre todos, ir ampliando el patrimonio tecnológico de la humanidad

### Aprender construyendo

En este tutorial aprenderemos electrónica digital mediante la **construcción de circuitos desde el primer momento**. El objetivo es aprender construyendo. Y por ello usaremos **impresoras 3D** para crearnos periféricos y objetos divertidos que controlar mediante nuestros circuitos

(FOTO)

### Placa Icezum Alhambra

Existen muchas placas con las FPGAs libres ICE40 de Lattice. Nosotros en este tutorial utilizaremos la Icezum Alhambra, que está orientada a makers. Pero cualquiera de las otras serán también válidas

(FOTO)

### Patrimonio tecnológico de la humanidad

Otro de los objetivos de este tutorial es usar sólo herramientas libres, que pertenezcan al patrimonio tecnológico de la humanidad. Esto garantiza que cualquier persona del mundo, con independencia del sistema operativo que utilice, pueda reproducir todo lo enseñado en este tutorial

(Logo)

## Resolución de dudas y formulación de preguntas

Para cualquier duda o consulta, por favor, **NO** me enviéis un correo personal privado. Recibo mucho al día, y no los puedo responder. Enviad todas vuestras consultas al [grupo FPGAwars](https://groups.google.com/forum/#!forum/fpga-wars-explorando-el-lado-libre). Por un lado la respuesta a vuestras consultas será más rápida, ya que hay más gente en la comunidad. Y por otro lado, el más importante, si te ha surgido una duda, seguramente otras personas la tendrán también. Y de esta forma, la respuesta a una consulta le sirve a más gente en el futuro

(Logo FPGAwars)

Aquí podéis encontrar más información sobre FPGAwars

## Sobre las entregas de ejercicios

TODO

## Ejercicios propuestos

TODO

* Circuit Scramble (instalar, y pasar algunos niveles)

## Ficheros
TODO

## Entregas
TODO

## Autor

## Licencia

## Enlaces




