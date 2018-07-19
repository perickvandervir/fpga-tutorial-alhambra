![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/Portada/Tut-23-portada.png)

# Vídeo

(En construcción...)

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

Haz click en la imagen para ver el **vídeo en Youtube**

# Descripción

Las **colecciones de Icestudio** nos permiten **organizar** los bloques y los ejemplos. Con ellas podemos estructurar lo que queremos enseñar, mostrando sólo lo que es relevante. Aprenderemos a **modificarlas** y **crearlas** desde cero

# Colección

[Academia-Jedi-HW-23.zip](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/Collections/Academia-Jedi-HW-23.zip): Colección para este tutorial. Descargar e instalar 

# Contenido

* [Introducción](#introducci%C3%B3n)
* [Carpeta de datos de Icestudio](#carpeta-de-datos-de-icestudio)
  * [GNU/Linux](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-23:-Mi-primera-colecci%C3%B3n#gnulinux)
  * [Windows 10](#windows-10)
  * [Mac](#mac)
* [Colecciones](#colecciones)
  * [Ejemplo 1: Duplicando una colección](#ejemplo-1-duplicando-una-colecci%C3%B3n)
  * [Estructura de las colecciones](#estructura-de-las-colecciones)
  * [README](#readmemd)
    * [Ejemplo 2: Cambiando el readme](#ejemplo-2-cambiando-el-readme)
  * [Ejemplos de la colección](#ejemplos-de-la-colecci%C3%B3n)
    * [Ejemplo 3: Añadiendo un ejemplo](#ejemplo-3-a%C3%B1adiendo-un-ejemplo)
    * [Ejemplo 4: Añadiendo un ejemplo en un sub-menú](#ejemplo-4-a%C3%B1adiendo-un-ejemplo-en-un-sub-men%C3%BA)
  * [Bloques de la colección](#bloques-de-la-colecci%C3%B3n)
    * [Ejemplo 5: Añadiendo un menú](#ejemplo-5-a%C3%B1adiendo-un-men%C3%BA)
    * [Ejemplo 6: Añadiendo un bloque nuevo](#ejemplo-6-a%C3%B1adiendo-un-bloque-nuevo)
    * [Ejemplo 7: Añadiendo un sub-menú](#ejemplo-7-a%C3%B1adiendo-un-sub-men%C3%BA)
* [Creando una colección nueva desde cero](#creando-una-colecci%C3%B3n-nueva-desde-cero)
  * [Plantilla coleccion-zero](#plantilla-coleccion-zero)
  * [Utilidad icm](#utilidad-icm)
    * [Instalación](#instalaci%C3%B3n)
    * [Creando una colección](#creando-una-colecci%C3%B3n)
    * [Actualizando la documentación y la traducción](#actualizando-la-documentaci%C3%B3n-y-la-traducci%C3%B3n)
* [Distribuyendo colecciones](#distribuyendo-colecciones)
* [Editando bloques de una colección](#editando-bloques-de-una-colecci%C3%B3n)
  * [Ejemplo 8: Creando un corazón de 2Hz](#ejemplo-8-creando-un-coraz%C3%B3n-de-2hz)
* [¡Comparte tus bloques!](#comparte-tus-bloques)
* [Ejercicios propuestos (20 Bitpoints)](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-23:-Mi-primera-colecci%C3%B3n#ejercicios-propuestos-20-bitpoints)
* [Ejercicios entregados](#ejercicios-entregados)
* [Autor](#autor)
* [Licencia](#licencia)
* [Enlaces](#enlaces)
* [Preguntas frecuentes](#preguntas-frecuentes)

# Introducción

Las **colecciones de Icestudio** nos permiten **organizar** los bloques y los ejemplos. Con ellas podemos estructurar lo que queremos enseñar, mostrando sólo lo que es relevante. Un ejemplo de uso son estos tutoriales, donde hay una colección por cada vídeo, en la que se añaden los nuevos **bloques** que se verán, los **ejemplos** de uso, los **ejercicios propuestos** y las **soluciones** a los ejercicios del tutorial anterior

Las colecciones están pensadas para que cada uno las **adapte** a lo que necesita. Por ejemplo se podrían crear colecciones para cada **proyecto**, o colecciones donde se recopilan los problemas de tal libro de electrónica digital, o bibliotecas de componentes...

Pero lo más importante es que **las colecciones se pueden compartir**. De esta forma, entre todos, podemos **reutilizar** el trabajo de los demás, **aprender**, **mejorarlo** y contribuir al incremento del **patrimonio tecnológico de la humanidad**

# Carpeta de datos de Icestudio

Cuando se instala **Icestudio**, se crea una **carpeta de datos**, dentro de nuestra **carpeta de usuario**, donde se almacenan las **preferencias**, las **colecciones** instaladas, el entorno de **python** y las **herramientas** necesarias para sintetizar los circuitos (Toolchain)

La ruta exacta depende del **sistema operativo** que estemos usando. Dentro de ella encontrarmos tres carpetas: **apio**, **collections**, **venv**, y el fichero de configuración **profile.json**

## GNU/Linux

 En el caso las máquinas **GNU/Linux**, la carpeta de datos está en nuestro **home**, con el nombre **.icestudio**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/Icestudio-data-01.png)

**¡Importante!** En Linux los directorio que empiezan con un punto están **ocultos** por defecto (no se ven). Para poder veerlos hay que activar la opción **Mostrar ficheros ocultos** en el navegador de archivos, o pulsar directamente  **Control-H**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/Icestudio-data-02.gif)

Una forma **muy cómoda** de acceder es añadiendo un **marcador**. Así sólo tenemos que pinchar en la carpeta **.icestudio** que aparece en la **barra de la izquierda**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/Icestudio-data-03.gif)

## Windows 10

En las máquinas Windows 10 podemos encontrar el directorio de datos de Icestudio dentro de nuestra **carpeta de usuario**, en la carpeta **.icestudio**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/Icestudio-data-04.png)

Se llega a ella pinchando en la **flechita** que apunta hacia abajo. Ahí seleccionamos el nombre de nuestro usuario

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/Icestudio-data-05.png)

Y también se puede llegar a través de la **ruta completa**:  Equipos - OS(C:) - usuarios - obijuan - .icestudio

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/Icestudio-data-06.png)

## Mac

TODO

# Colecciones

Las **colecciones instaladas** se encuentran en la **carpeta de colecciones**, que tiene el nombre **collections**. A partir de ahora la estructura de los directorio no depende del Sistema operativo, por lo que usaré pantallazos del que uso yo: **GNU/Linux/Ubuntu 18.04**

Partiremos de un Icestudio que sólo tenga instalada **una colección**: la correspondiente a este tutorial: **Academia-Jedi-HW-23**. Desde el menú **Seleccionar/Colección** lo comprobamos

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/collection-01.png)

Si ahora nos **metemos** en la carpeta collections, veremos que hay **una carpeta** con el nombre de la colección instalada: **Academia-Jedi-HW-23**. Cada vez que **instalamos** una colección en icestudio, se descomprimirá en este directorio. Así, dentro de collections existirá **una carpeta por cada colección instalada**. Como ahora sólo tenemos instalada una sola colección, sólo aparece una carpeta

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/collection-02.png)

## Ejemplo 1: Duplicando una colección

Vamos a crear **nuestra primera colección** duplicando la que ya tenemos instalada. Nos vamos a la carpeta de colecciones de icestudio y **duplicamos** la carpeta de la colección instalada (usando copy & paste por ejemplo). Luego le **cambiamos** el nombre a **test-1**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/collection-03.png)

En esta **animación** se muestra el proceso

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/collection-04.gif)

Ahora nos vamos a la ventana de **Icestudio** y pinchamos en la opción **Herramientas/Colecciones/Reload**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/collection-05.png)

Volvemos a ver las colecciones que tenemos **instaladas**, yendo a la opción **Seleccionar/Colección**. Ahí nos aparecerá la **nueva colección test-1**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/collection-06.png)

Cualquier **cambio** que hagamos dentro de la carpeta de colecciones (collections) se ***reflejará** en Icestudio. Los cambios se **actualizarán** al **arrancar** Icestudio, al **abrir una ventana nueva** o bien al darle a la opción de **Reload**

**Seleccionamos** la nueva colección **test-1**. En los siguientes ejemplos la modificaremos. Todo el proceso se resume en esta **animación**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/collection-07.gif)

## Estructura de las colecciones

Todas las colecciones tienen la **misma estructura**. Nos metemos dentro de la carpeta **test-1** para ver cómo está organizada

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/collection-08.png)

Todos los elementos son **opcionales**, salvo el fichero **package.json**. Se describen en la siguiente **tabla**


| Elemento         | Obligatorio | Descripción |
|------------------|-------------|-------------|
| **package.json** | **SI**      | **Información** sobre la colección: nombre, versión, autores, repo... Icestudio necesita este fichero para reconocerlo como una colección |
| **blocks**       | NO          | Carpeta con los **bloques** de la colección. Su contenido se muestra en la parte superior derecha del **menú de Icestudio**| 
| **examples**     | NO          | Carpeta con los **ejemplos** de la colección. Su contenido se muestra en el **menú Archivo/Ejemplos** |
|**locale**        | NO          | Carpeta con las **traducciones** a diferentes idiomas |
| **README.md**    | NO          | Información de la colección, para humanos. Su contenido se muestra en la opción **Ver/Informacón de la coleción** |
|**LICENSE**        | NO          | Fichero de texto con la **licencia** de la colección |

Esta es otra descripción, más visual

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/collection-09.png)

## README.md

El fichero **README.md** es el que se muestra cuando se pincha en la opción del menú **Ver/Información de la colección**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/collection-10.png)

Este fichero se escribe en [markdown](https://guides.github.com/features/mastering-markdown/), igual que en github (y que en los bloques de información de icestudio). Al **verlo** desde Icestudio se renderiza en una **ventana nueva**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/collection-11.png)

### Ejemplo 2: Cambiando el Readme

**Abrimos** el fichero README.md con un **editor** de texto, borramos su contenido y **escribimos** esto:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/collection-12.png)

Ahora desde **Icestudio** lo mostramos, en la opción **Ver/Información de la colección**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/collection-13.png)

Y vemos que se ha **actualizado** directamente (no hace falta usar el Reload. Esta opción directamente busca el README desde la carpeta y lo renderiza. De forma que cualquier cambio se muestra directamente al visualizarse)

## Ejemplos de la colección

La **carpeta examples** contiene todos los **ejemplos** de la colección, que se muestran desde el menú **Archivos/Ejemplos**. Los **ficheros .ice** con los ejemplos se muestran **directamente** en el menú, mientras que las **carpetas** adicionales se muestran como **sub-menúes**. De esta forma, podemos organizar los ejemplos en carpetas y se mostrarán en Icestudio mediante menúes y sub-menúes

Nos **metemos** dentro de la carpeta **examples**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/collection-15.png)

Dentro hay un ejemplo, llamado **Test.ice** y otras **tres carpetas**. Si nos vamos a **Archivo/Examples** se nos abre el menú de los ejemplo que contiene exactamente lo que hay en la carpeta examples:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/collection-14.png)

### Ejemplo 3: Añadiendo un ejemplo

Para añadir un ejemplo simplemente hay que **copiarlo en la carpeta examples**. En vez de crear un ejemplo desde 0, copiaremos el que ya exite: Test.ice y le ponemos el nombre **Test-2.ice**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/collection-16.png)

Ahora le damos a la opción **Herramientas/Colecciones/Reload** para que se actualice la colección en Icestudio. Si miramos en el menú **Archivos/Ejemplos** vemos que ha aparecido el **nuevo ejemplo Test-2**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/collection-17.png)

En esta **animación** se muestra todo el **proceso**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/collection-18.gif)

### Ejemplo 4: Añadiendo un ejemplo en un sub-menú

**Añadir** un ejemplo en un **sub-menú** es igual de sencillo. Primero creamos la carpeta que será el sub-menú. La llamamos por ejemplo **Sub-menu**. Ahí colocamos el ejemplo o ejemplos a añadir. Para hacer una prueba rápida **copiaremos** el fichero **Test-2.ice**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/collection-19.png)

Ahora **recargamos la colección** (Herramietas/Colecciones/Reload) y miramos el menú de los ejemplos. El nuevo Sub-menú con el ejemplo se encuentran ahí

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/collection-20.png)

En esta **animación** se resume el **proceso**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/collection-21.gif)

## Bloques de la colección

La **carpeta blocks** contiene todos los bloques de la colección, organizados en carpetas que son **menúes** y **sub-menúes**. Nos **metemos** dentro de blocks para echar un vistazo:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/collection-22.png)

Vemos que hay **tres carpetas**, que se corresponden con los **menúes de bloques** que hay en la parte superior derecha de Icestudio

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/collection-23.png)

En este nivel **sólo puede haber carpetas**, y no ficheros .ice con bloques. Si existieran Icestudio los ignoraría. Esto es así porque en la barra superior sólo puede haber menúes. **Dentro** de ellos es donde están los bloques

### Ejemplo 5: Añadiendo un menú

Vamos a añadir un **menú vacío** a nuestra colección. Nos metemos en la carpeta **blocks** y creamos un **directorio vacío**, llamado por ejemplo **mi_menu**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/collection-24.png)

Ahora **recargamos la colección** y veremos cómo ha aparecido el **nuevo menú** en la parte superior (tenemos que asegurarnos de que la colección test1 está seleccionada). Este menú está vacío, por lo que si situamos el ratón encima no se despliega

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/collection-25.png)

En esta **animación** se muestra el **proceso completo**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/collection-26.gif)

### Ejemplo 6: Añadiendo un bloque nuevo

Añadiremos un **bloque nuevo** en el menú que acabamos de crear. Para no crearlo desde cero, directamente **copiaremos** uno ya existente. Por ejemplo el **corazón de 1Hz** que se encuentra en el menú **Varios/Bombeo/Fijos**. Este menú se corresponde con la carpeta **.icestudio/collections/test-1/blocks/Varios/Bombeo/Fijos**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/collection-27.png)

Ahí se encuentra el componente **Corazon_1Hz.ice**. Lo copiamos a la carpeta **blocks/mi_menu** que hemos creado en el ejemplo anterior

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/collection-28.png)

**Recargamos** la colección y observamos que nos ha aparecido  el **nuevo componente**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/collection-29.png)

En esta **animación** se muestra todo el **proceso**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/collection-30.gif)

### Ejemplo 7: Añadiendo un sub-menú

Crearemos un **sub-menú**, llamado **mi_sub_menú**, dentro del menú mi_menu, y añadiremos una **copia** del corazón de 1Hz. 

Primero nos metemos dentro de la **carpeta mi_menú** y creamos la **carpeta mi_sub_menú**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/collection-31.png)

Ahora **copiamos** el corazón de 1Hz (o cualquier otro componentes que queramos probar) en esa carpeta

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/collection-32.png)

Desde Icestudio **recargamos** la colección y comprobamos que el nuevo sub-menú y el nuevo corazón aparcen

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/collection-33.png)

Todo el proceso se muestra en esta **animación**:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/collection-34.gif)

# Creando una colección nueva desde cero

Las **colecciones** las podemos **crear** fácilmente como hemos visto en los apartados anteriores: copiamos la carpeta de una ya instalada y **añadimos/borramos** ficheros y carpetas

En este apartado enseñaremos otras dos formas: una es partiendo de una **plantilla** de colección vacía, y la otra es usando la **utilidad icm**

## Plantilla Coleccion-zero 

Utilizaremos esta colección plantilla: [Coleccion-zero.zip](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/Collections/Coleccion-zero.zip) para crear una ***colección mínima vacía**

Los **pasos** a seguir son:

* **Descargar** la plantilla: [Coleccion-zero.zip](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/Collections/Coleccion-zero.zip)
* **Añadirla** a Icestudio como una colección cualquiera: **Herramientas/Colecciones/Añadir**. La seleccionamos

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/zero-01.png)

También podríamos haberla descomprimido directamente dentro de la carpeta Collections y ejecutar la opción Herramientas/Colecciones/Reload. El proceso es equivalente

* Nos metemos en la **carpeta Collections**. Vemos que está creada la **carpeta Coleccion-zero**, que acabamos de instalar

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/zero-02.png)

* **Cambiamos el nombre** de la carpeta, para llamarla como nosotros queramos. Por ejemplo **mi-zero**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/zero-03.png)

* **Recargamos** desde Icestudio. Nos vamos a **Seleccionar/Colección**. Vemos que aparece la colección con el nuevo nombre. Pero como como hemos cambiado el nombre, estará seleccionada la colección por defecto. **Seleccionamos mi-zero**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/zero-04.png)

* Ahora ya podemos **añadir** menúes, sub-menúes, bloques y ejemplos como hemos visto en los apartados anteriores

## Utilidad icm

La [utilidad icm](https://pypi.org/project/icm/) es un programa en **python**, creado por [Jesús Arroyo](https://github.com/Jesus89), que nos permite **crear** las plantillas para las colecciones así como **actualizar** su documentación

### Instalación

Se instala directamente desde el **repositorio de paquetes de python**, usando **pip install**

En los sistemas **GNU/Linux** lo más cómodo es instalarlo globalmente, para que esté accesible desde el path:

```
$ sudo pip install icm
```

Desde **Windows/Mac** se instala con:

```
pip install icm
```

Podemos comprobar que se ha **instalado correctamente** abriendo un terminal y ejecutando el **comando icm**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/icm-01.png)

En una **máquina Windows 10** se haría de la misma forma:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/icm-02.png)

### Creando una colección

Los **pasos** a seguir para **crear** una colección usando icm son los siguientes:

* **Crear un directorio con el nombre de la colección**. Se puede crear en **cualquier** sitio, NO sólo en la carpeta Collections de Icestudio

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/icm-03.png)

* Entrar en el directorio **Mi_colección**, abrir un **terminal**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/icm-04.png)

* **Ejecutar** el comando **icm create**

```
$ icm create
```

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/icm-05.png)

Esto **crea** todos los directorios y las plantillas necesarias

* Ahora ya podemos **añadir** menúes, sub-menúes, bloques y ejemplos

### Actualizando la documentación y la traducción

Cuando hemos hecho una **modificación** a la colección, como **añadir** bloques o ejemplos nuevos, o modificar alguno de los cambpos del fichero **package.json**, podemos ejecutar el **comando icm update** para generar un nuevo fichero **README.md**, así como actualizar la traducción

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/icm-06.gif)

Todas las colecciones de la** Academia Jedi de Hardware** están actualizadas con el comando **icm update**. Puedes ver el resultado desde **Ver/Información de la colección**

# Distribuyendo colecciones

Si ya tenemos una **colección creada** y queremos que otros la **usen** seguimos los siguientes pasos:

* Nos vamos al directorio donde **se encuentra** la carpeta con **nuestra colección** (puede ser en Collections o en cualquier otro directorio)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/icm-03.png)

* La **comprimimos** en **ZIP**. Desde GNU/Linux es muy fácil. Simplemente nos ponemos encima de la carpeta, le damos al botón derecho del ratón y elegimos la opción comprimir...

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/deliver-01.gif)

* ¡Ya tenemos el fichero **Mi-coleccion.zip** con nuestra colección!. Cualquiera puede añadir la colección a Icestudio desde la opción **Herramientas/Colecciones/Añadir**, pasándole este fichero 

* **Opcionalmente**, antes de crear el fichero .ZIP podemos actualizar la documentación ejecutando el comando icm update dentro de la carpeta Mi-colección. Esto nos genera un fichero README.md nuevo, que está actualizado

# Editando bloques de una colección

Existe una forma sencilla de **editar los bloques** de una colección, mediante la opción **Archivo/Bloques**. Desde ella podemos acceder a todos los bloques de la colección, igual que con el menú superior, con la diferencia de que se **abren los bloques** como un **proyecto**, y no se insertan como bloques.

### Ejemplo 8: Creando un corazón de 2Hz

Como ejemplo vamos a crear un **corazón de 2Hz** editando el de 1Hz. 

Seleccionamos la colección **Test-1** y editar el bloque del corazón de 1Hz que se encuentra en **Mi_menu/mi_sub_menu** a través de la opción **Archivo/Bloques**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/editando-01.png)

En vez de aparecer el bloque corazón de 1Hz, se nos abre su **implementación** (su interior)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/editando-02.png)

Convertirlo en un **corazón de 2Hz** es muy fácil en este ejemplo, sólo hay que cambiar el **parámetro Hz** dándole el valor **2** en vez de 1

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/editando-03.png)

También cambiamos la **información del proyecto** (icono, descripción, nombre...)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/editando-04.png)

y finalmente lo grabamos con el nombre **Corazon-2Hz** en la ruta **.icestudio/collections/test-1/blocks/mi_menu/mi_sub_menu/**, para que esté en la **colección Test-1** en el mismo menú que el de 1Hz

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/editando-05.png)

Abrimos una **ventana nueva** de icestudio y miramos en el menú **Mi_menu/Mi_sub_menu**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/editando-06.png)

Ahí está nuestro nuevo corazón. Lo **colocamos** y lo conectamos a un LED para probarlo

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/editando-07.png)

¡Nuestro nuevo bloque está funcionando! :-)

# ¡Comparte tus bloques!

Entre todos podemos **crear bloques** y **compartirlos**. Si has creado bloques, aunque sean prototipos, ***compártelos con la comunidad** para poder aprender de ellos, mejorarlos o crear otros bloques derivados

En [la wiki del repositorio icestudio-blocks](https://github.com/FPGAwars/icestudio-blocks/wiki) estamos recopilando todos los enlaces a los **recursos de Icestudio**. Es una **wiki pública**, en la que todo el mundo puede editar. Si tienes repositorios o wikis con bloques, ejemplos, o cualquier información relacionada con Icestudio, puedes añadir los enlaces y la información en esta wiki. La idea es usarla como **UN ÍNDICE**

Adicionalmente puedes añadir en [este repositorio](https://github.com/FPGAwars/icestudio-blocks) bloques y ejemplos. Cualquier bloque que hayas hecho y no sepas dónde ponerlo, este es el lugar :-)




(TODO)

# Ejercicios propuestos (20 BitPoints)

Ver los detalles de los ejercicios y las **entregas** en el menú **Archivos/Ejemplos/2-Ejercicios** de la colección de este tutorial

**Resumen**:

* **Ejercicio 23.1** (Total **5 Bitpoints**): **Colección con mis bloques**

Crear una colección desde 0 (usando la plantilla [Coleccion-zero.zip](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/Collections/Coleccion-zero.zip)), que se llame como tu apodo (en mi caso sería la colección Obijuan). Esta colección la iremos ampliando y modificando en los siguientes ejercicios. En este primero tendrás que crear un menú que se llame **Mis_bloques** y en él situar los **3 bloques** que creaste como  
ejercicios del **tutorial 21**

Este es un **ejemplo** del pantallazo a entregar:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/Soluciones/sol-23.1.png)

* **Ejercicio 23.2** (Total **5 Bitpoints**):  **Añadiendo tablas a mi colección**

Continuar con la colección creada en el ejercicio 23.1. Añadir un **nuevo menu** llamado **Tablas** que contenga **tres tablas de 3 entradas** y salidas de 5, 6 y 7 bits. Deben estar en un **sub-menú** llamado **tablas-3**    

Crearlas usando la [Fábrica de tablas](https://obijuan.github.io/iceFactory/icetable/icetable.html)

Este es un **ejemplo** del pantallazo a entregar:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/Soluciones/sol-23.2.png)


* **Ejercicio 23.3** (Total **5 Bitpoints**): Añadiendo Ejemplos a mi colección

Añadir los dos **circuitos de pruebas** de los bloques AND y de Franky que se hicieron en el **tutorial 21**. Se deben llamar **Test-and** y **Test-Franky**. Tiene que ser accesible desde el menú de **Ejemplos** de la colección

Este es un **ejemplo** del pantallazo a entregar:

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-23/Soluciones/sol-23.3.png)

* **Ejercicio 23.4** (**5 Bitpoints**). Ejercicio Libre. Premiar la creatividad. **Entregar** por redes sociales o github: Pantallazos, enlaces, vídeos, etc...

# Ejercicios entregados

## Primero

### Ejercicio 23.1
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 23.2
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 23.3
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 23.4
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()


## Segundo

### Ejercicio 23.1
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 23.2
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 23.3
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 23.4
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

## Tercero

### Ejercicio 23.1
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 23.2
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 23.3
![]()

* **Vídeo** en Youtube:

[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

### Ejercicio 23.4
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



