![](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/raw/master/wiki/portada/alicia-maker.jpg)

# Tutorial de Electrónica Digital para makers con FPGAs Libres

Hola! Soy obijuan, y en este **microtutorial** comenzamos el curso sobre **Electrónica digital para makers utilizando FPGAs libres**. Es un curso diferente, totalmente distinto a lo que hayas visto. El objetivo es enseñar **pensamiento hardware** de una forma **práctica**, haciendo circuitos desde el minuto 0.

## Contenido

| Vídeo | Nombre  |
|-------|---------|
| 1 | [Electrónica digital para todos](https://github.com/Obijuan/digital-electronics-with-open-FPGAs-tutorial/wiki/Video-1:-Electr%C3%B3nica-digital-para-todos)    |
| 2 | ¡Poniendo en marcha Icestudio!   |


----------------------------------------------------
## Academia Jedi de hardware

### En primer curso

### En la pre-academia

**Aspirantes** a entrar en la academia de Jedi de hardware. Número de **Bitpoints** requeridos para el ingreso: **5**

|Núm|  Nombre               |  Rango             |  BitPoints |
|------|-----------------------|--------------------|------------|
|1     | Julian Caro           | Aspirante a Cadete | 4 |
|2     | Juan Manuel Rico      | Aspirante a Cadete | 4 |
|3     | Diego Lale            | Aspirante a Cadete | 4 |
|4     | Juanillo Pillo        | Aspirante a Cadete | 4 |
|5     | Alberto Valero        | Aspirante a Cadete | 4 |
|6     | Loquox                | Aspirante a Cadete | 4 |
|7     | Jaime Laborda         | Aspirante a Cadete | 4 |
|8     | Miquel Servera        | Aspirante a Cadete | 4 |
|9     | Manuel Andújar        | Aspirante a Cadete | 4 |
|10xx  | OskarLM               | Aspirante a Cadete | 4 |
|10    | Federico Coca         | Aspirante a Cadete | 2 |
|11    | Juan A. Ramón Girón   | Aspirante a Cadete | 2 |
|12    | Unai Sanz             | Aspirante a Cadete | 2 |
|13    | Juan G. Maker         | Aspirante a Cadete | 2 |
|14    | Javi (@Seat_128)      | Aspirante a Cadete | 2 |
|15    | Andrés (@Avarez_)     | Aspirante a Cadete | 2 |
|16    | Jose Luis (@movilujo) | Aspirante a Cadete | 2 |
|17    | Luis Sobrino Fdz.     | Aspirante a Cadete | 2 |
|18    | Jordi R. Crespo       | Aspirante a Cadete | 2 |
|19    | Jorge Turiel          | Aspirante a Cadete | 2 |
|20    | Jokin Lacalle         | Aspirante a Cadete | 2 |
| Jordi Bardají         | Aspirante a Cadete | 2 |
| Javi (@JavimJavi)     | Aspirante a Cadete | 2 |
| Diego Lorenzo Balbis  | Aspirante a Cadete | 2 |
| Javier Solsona        | Aspirante a Cadete | 2 |
| Sergio Arciénaga      | Aspirante a Cadete | 2 |
| Dmayoraru             | Aspirante a Cadete | 2 |
| César García (@elsatch) | Aspirante a Cadete | 2 |



## Listado de Rangos

| Rango          |  BitPoints requeridos  |  Descripción  |
|----------------|-------------|---------------|
| **Observador** |  0          | Te gusta ojear las cosas. Todavía no te has atrevido a experimentar con circuitos digitales
| **Aspirante a cadete** |  2  | Todavía no has ingresado en la academia Jedi de hardware, pero tienes interés, y te gustaría probar
| **Cadete**    |  5  |  ¡Bienvenido a la academia Jedi de hardware! Tienes curiosidad e Interés suficiente sobre hardware y tienes Icestudio instalado. ¡Listo para aprender!
| **Cadete nivel 1** |     |
| **Cadete nivel 2** |    |
| **Cadete nivel 3** |   |
| **Aspirante a Padawan** |  |
| **Padawan** | |
| **Padawan nivel 1** | | 
| **Padawan nivel 2** | |
| **Padawan nivel 3** | |
| **Aspirante a Jedi**| |
| **Jedi iniciado** |  |
| **Jedi nivel 1** |  |
| **Jedi nivel 2** |  |
| **Jedi nivel 3** |  |
| **Aspirante a caballero jedi** | |
| **Caballero Jedi** |  |
| ... |  |

# Plantilla

## Descripción

TODO

## Explicación

TODO

## Ejercicios propuestos

TODO

## Entregas

TODO

## Ficheros

TODO

# Notas

## Vídeo 2: Instalación Icestudio 0.3
* Instalación en Linux
* Instalación en MAC
* Instalación en Windows 10
* Descargar ejemplo kitt en icezum Alhambra (o tal vez el efecto fade de los leds)

## Vídeo 3: Mi primer circuito: Encendiendo un led
* Los ctos digitales trabajan con información, que se representa con 0s y 1s
* La alimentación va aparte
* En icestudio:
  * Poner pin de salida, sin asignar
  * Convertir a pin físico y asignar a la salida D13
  * Enviar un 1 por la salida
  * Sintetizar y cargar
  * Explicación: Importante que sepan qué partes son físicas
* Ejercicio 1: Hacer un circuito que encienda el led conectado a D0

## Vídeo 4: Solución al ejercicio 1
En el vídeo hacemos el ejemplo a partir del otro, simplemente cambiando D13 por D0. Explicamos qué ocurre dentro de la FPGA
* Practicando: Conectar led a D8 y encender led (Solución no dada)

## Vídeo 5: Encendiendo 2 leds (leds en paralelo)
¿Cómo dejar 2 leds encendidos a la vez? --> Haciendo 2 circuitos. Son 2 circuitos independientes
Si desconectamos el cable de D12 y dejamos el pin al aire..¿Cómo queda el led? Indeterminado. No se debe hacer

Siempre hay que definir cómo está: 1 ó 0

* Ejercicio: Queremos dejar encendidos 3 leds, asociados a los pines de la Ahambra 0, 2 y 4. Hacer el circuito

## Vídeo 6: Solución al ejercicio 2

3 circuitos en paralelo. Recalcar la idea de circuitos en paralelo

## Vídeo 7: Los 8 leds de la Alhambra

* Introducir los 8 leds de prueba de la icezum

## Vídeo 8: Solución al ejercicio 3

Por definir

## Vídeo 9: Entrada digital

Ejercicio 9-1: Montar un cto con un pulsador que entre por D12 y un led que slga por D1
Ejercicio 9-2: Circuito que encienda los leds conectados a D0 y D1
Ejercicio 9-3: Dos circuitos en paralelo
Ejercicio 9-4: 2 circuitos. Cada pulsador enciende 4 leds

# Vídeo 10: Solución a los ejercicios

# Video 11: Servo binario: derecha / izquierda

Mostrar cómo funcionan el servo de 2 posiciones (ServoBit-X), controlado con un pulsador

Plantear ejercicios 





