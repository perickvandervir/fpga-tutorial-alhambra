[![Click to see the youtube video](http://img.youtube.com/vi//0.jpg)]()

Haz click en la imagen para ver el **vídeo en Youtube**

(En construcción)

# Descripción

Las herramientas que usaremos en estos tutoriales son [Icestudio](https://github.com/FPGAwars/icestudio) y la placa [Icezum Alhambra](https://github.com/FPGAwars/icezum/wiki). Pero existen otras placas con **FPGAs libres** que se están desarrollando en la comunidad. La icezum Alhambra es una placa libre, y puedes ver sus tripas usando herramientas libres como [Kicad](http://kicad-pcb.org/). También puedes ver cómo están hechos sus componentes 3D y sus accesorios, con [Freecad](https://www.freecadweb.org). Es importante ser conscientes de lo que implican las tecnologías libres: **¡Acceso total a sus planos!** ¡Esto nos da un inmenso poder! Las empresas van y vienen, y con ellas sus productos. Pero **lo libre permanece**

# Contenido

* [FPGAs Libres](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-3:-La-Icezum-Alhambra-y-otras-placas-con-FPGAs-libres#fpgas-libres)
* [Placas con FPGAs libres](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-3:-La-Icezum-Alhambra-y-otras-placas-con-FPGAs-libres#placas-con-fpgas-libres)
  * [Placas soportadas por Icestudio](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-3:-La-Icezum-Alhambra-y-otras-placas-con-FPGAs-libres#placas-soportadas-por-icestudio)
  * [Otras placas no soportadas todavía](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-3:-La-Icezum-Alhambra-y-otras-placas-con-FPGAs-libres#otras-placas-no-soportadas-todav%C3%ADa)
* [La placa Icezum Alhambra](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-3:-La-Icezum-Alhambra-y-otras-placas-con-FPGAs-libres#placa-icezum-alhambra)
* [Ejercicios propuestos](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-3:-La-Icezum-Alhambra-y-otras-placas-con-FPGAs-libres#ejercicios-propuestos-10-bitpoints)
* [Ejercicios entregados](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/V%C3%ADdeo-3:-La-Icezum-Alhambra-y-otras-placas-con-FPGAs-libres#ejercicios-entregados)
* []()

# FPGAs libres

Una FPGA libre es aquella que tiene **disponible toda su documentación interna** con tal detalle que sea posible hacer herramientas software que permitan la síntesis de hardware y su carga en la FPGA. Actualmente las únicas FPGAs libres son las de la **familia ICE40 de Lattice**. Disponemos de toda la documentación gracias a **Clifford Wolf**, que hizo ingeniería inversa y creó el **proyecto Icestorm**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-03/placas-02.png)

El resto de FPGAs son privativas. Sólo las podemos usar con **el softaware proporcionado por el fabricante**, y sólo se puede hacer con ellas lo que el fabricante a decidido que se puede hacer. **No están disponibles sus detalles internos** con el detalle suficiente, ni el formato del *bitstream*. Esto hace imposible, por ejemplo, que alguien que no sea el fabricante pueda crear un software para facilitar su uso, como Icestudio. O que se pueda sintetizar hardware desde una Raspberry pi o cualquier otra plataforma diferente a la decidida por el fabricante

# Placas con FPGAs libres

Ya tenemos el software listo para diseñar circuitos digitales: **Icestudio**. Como este es un curso práctico, necesitamos una **placa real** con la que practicar. Al fin y al cabo, **¡Somos makers!** y nos gusta mancharnos las manos construyendo cosas, y aprender haciendo. La placa que usaremos será la **Icezum Alhambra**, pero existen más placas con **FPGAs libres**, que están soportadas por Icestudio

## Placas soportadas por Icestudio

Abrimos Icestudio y pinchamos en la opción **Seleccionar/Placa**

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/Tutorial-03/placas-01.jpg)

Ahí podemos ver todas las **placas** que están actualmente **soportadas** en **Icestudio 0.3.1**:

* [Icezum Alhambra](https://github.com/FPGAwars/icezum/wiki)
* [Kéfir I](http://fpgalibre.sourceforge.net/Kefir/)
* [Nandland Go Board](https://www.nandland.com/goboard/introduction.html)
* [Lattice Breakout Board](http://www.latticesemi.com/Products/DevelopmentBoardsAndKits/iCE40HX8KBreakoutBoard.aspx)
* [Lattice Icestick](http://www.latticesemi.com/icestick)
* [Icoboard 1.0](http://icoboard.org/about-icoboard.html)

### Lattice Icestick

TODO

### Lattice Breakout Board

TODO

### Kéfir I

TODO

### Nandland Go Board

TODO

### Icoboard

TODO

## Otras placas no soportadas todavía

* Mystorm BlackIce
* Olimex

# Placa Icezum Alhambra

## Descripción
  * Repo
  * Diseñador: Eladio Delgado

## Kicad

-Alhambra y kicad
  * Mostrar esquema
  * Mostrar PCB
  * Mostrar 3D

## FreeCAD
-Alhambra y Freecad
  * Componentes 3D disponibles
  * Mostrar conector micro-usb en freecad

## Accesorios 3D
-Accesorios alhambra: Soporte imprimible


# Ejercicios propuestos (10 BitPoints)

* **Ejercicio 1** (2 Bitpoints): Alhambra + kicad. 2 pantallazos  (+1 Bitpoint github)
* **Ejercicio 2**:(2 Bitpoints): Alhambra + Freecad. 1 pantallazo con la FPGA de lattice abierta (+1 Bitpoint github)
* **Ejercicio 3**:(2 Bitpoints): Impresión soporte Icezum Alhambra. Foto
* **Ejercicio 4: (Hasta 2 Bitpoints): Ejercicio libre. Premiar la creatividad

# Ejercicios entregados

# Autor

* [Juan González-Gómez](https://github.com/Obijuan) (Obijuan)

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/logos-urjc-gsyc-peloto-jderobot.png)

# Licencia

![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/attribution-share-alike-creative-commons-license.png)

# Créditos y agradecimientos

# Enlaces

# FAQs



