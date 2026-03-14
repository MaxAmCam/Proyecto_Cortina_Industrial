# Proyecto Mecatrónico – MR2022

## Problema
En esta situación problema se busca automatizar una cortina de uso industrial utilizada en un lugar donde circulan personas y vehículos de carga. La cortina puede tener diferentes dimensiones de ancho y altura, además de estar fabricada con hule termoformado y barras metálicas en la parte inferior para mantener la tensión, todo esto hace que la cortina tenga un peso elevado. Debido a esto, el sistema debe ser capaz de mover la cortina de forma controlada y segura.

La automatización debe permitir que la cortina se enrolle hasta una altura determinada y en un tiempo específico, el cual se debe poder ajustarse desde una interfaz de operación dentro de un rango de 5 a 10 segundos. También se necesita que la altura máxima de la cortina y los tiempos de espera se puedan configurarse desde la interfaz. El sistema tiene que ser capaz de operar tanto en modo manual como en modo automático, además se debe considerar que existen diferentes tipos de usuarios con permisos distintos. Algo fundamental es la seguridad, ya que durante el movimiento de bajada se debe detectar la presencia de personas u objetos para evitar accidentes y garantizar que su funcionamiento sea seguro.

## Arquitectura del sistema
![Diagrama del sistema](docs/GIFTS/Bloques.png)

## Componentes utilizados
Se utilizan los siguientes sensores:
- Sensor inductivo LJ12A3-4-Z/BX (NPN-NO) — detección mediante campo electromagnético. Señal digital NPN normalmente abierto.
- Sensor capacitivo LJ18A3-B-Z/BX (NPN-NO) — detección por variación de capacitancia. Señal digital NPN normalmente abierto.
- Sensor óptico infrarrojo E3F-DS30P1 (PNP-NO) — detección por radiación infrarroja reflejada. Señal digital PNP normalmente abierto.
- Sensor magnético FESTO SME-8M-DS-24V-K-2,5-OE — detección de campo magnético. Señal digital 24 VDC.

El sistema también integra los siguientes componentes:
- Siemens LOGO
- Relés
- Motor DC 24 V
- Torre de luces

## Lógica de control
![Diagrama del sistema](docs/GIFTS/Esquemafinal.png)

El control del sistema fue implementado mediante un PLC Siemens LOGO! utilizando un diagrama de bloques (FBD). En este esquema se integran las señales de los sensores de entrada para controlar el movimiento de una cortina industrial automatizada.

Los sensores magnéticos permiten detectar las posiciones superior, media e inferior de la cortina, mientras que el sensor inductivo habilita el funcionamiento del sistema. El sensor óptico actúa como un elemento de seguridad, deteniendo el movimiento si detecta la presencia de una persona u objeto cercano. Además, se implementa un sensor capacitivo que funciona como paro manual del sistema.

La lógica incluye interlocks de seguridad que impiden condiciones peligrosas, como activar simultáneamente el movimiento de subida y bajada del motor o intentar mover la cortina cuando ya se encuentra en un límite de recorrido. Las salidas del sistema controlan el motor en ambas direcciones mediante relés y activan lámparas LED que indican el estado del sistema.

## Resultados de pruebas
| Elemento probado | Condición de prueba | Resultado esperado | Resultado obtenido |
|------------------|---------------------|--------------------|--------------------|
| Sensor inductivo | Acercar un objeto metálico al sensor | Iniciar el ciclo de operación de la cortina | El sensor detectó correctamente el objeto metálico y el sistema inició el movimiento |
| Sensor óptico | Colocar una mano u objeto frente al sensor durante el movimiento | Detener la cortina por seguridad | El sensor detectó correctamente la presencia y el sistema se detuvo inmediatamente |
| Sensor capacitivo | Activar el sensor manualmente | Detener el sistema como paro de emergencia | El sistema se detuvo correctamente al activar el sensor |
| Sensor magnético superior | Colocar la cortina en la posición superior | Permitir el inicio del ciclo | El sistema solo inició cuando la cortina estaba en la posición superior |
| Sensor magnético medio | Llevar la cortina a la posición intermedia | Detectar la posición intermedia y activar la señal correspondiente | El sistema detectó correctamente la posición intermedia |
| Sensor magnético inferior | Llevar la cortina a la posición inferior | Detener la cortina y activar el temporizador de subida | El sistema detectó correctamente la posición inferior y activó el temporizador |
| Motor DC | Ejecutar el ciclo completo de bajada y subida | Mover la cortina de forma controlada en ambos sentidos | El motor realizó correctamente los movimientos de bajada y subida |
| Torre de luz roja | Operación del sistema en la condición programada | Indicar estado de operación | La luz roja se encendió correctamente cuando se cumplió la condición programada |
| Torre de luz verde | Llegada de la cortina a la posición inferior | Indicar estado de espera en posición inferior | La luz verde se encendió correctamente al llegar a la posición inferior |


## Video demo y foto del equipo
[(Link al video)](https://www.youtube.com/shorts/yC3Cw31sUlQ)

![Imagen del equipo](https://github.com/MaxAmCam/Proyecto_Cortina_Industrial/blob/bc93e771a5abd281b9d2c3f3eba4050d9089960b/docs/GIFTS/WhatsApp%20Image%202026-03-12%20at%206.19.11%20PM.jpeg)

## Equipo


Joel Alejandro Soto Muñoz

Sara Gabriela Díaz Rayas

Claudio Daniel Gómez Zermeño

Max Emiliano Amezcua Camacho
