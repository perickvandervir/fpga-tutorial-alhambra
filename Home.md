# Tutorial de Electrónica Digital con FPGAs Libres

Aprende Electrónica Digital, de una forma **muy intuitiva** y fácil

## Introducción

TODO

##

# Notas

## Vídeo 1: Electrónica digital para todos
* Introducción al tutorial
* Herramientas libres usadas: icestudio
* Ejemplos de cosas que haremos
* Hardware que usaremos: Icezum Alhambra + sensores + placas periféricas
* FPGAwars --> cualquier pregunta ahí

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







