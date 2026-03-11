# Bitácora – Semana 3 - Max

## Tema de la semana
(Actuadores / Control)

## Actividades realizadas
Durante esta semana se finalizó el cableado completo del sistema. Se elaboró el diagrama y se realizaron las conexiones de los relés que serán utilizados para controlar la dirección de giro del motor. También se realizaron las conexiones de las lámparas LED, las cuales permiten indicar los diferentes estados del sistema.

Posteriormente, una vez completado el cableado, se desarrolló la lógica del programa en LOGO!, con el objetivo de implementar las funciones descritas en el H1. En esta etapa se configuró el funcionamiento de los sensores para que, al activarse, generen las salidas correspondientes, permitiendo el movimiento o paro del motor, así como el encendido de la lámpara industrial según las condiciones del sistema.

## Decisiones de ingeniería
| Decisión | Alternativas | Justificación |
|--------|-------------|---------------|
| Uso de relés para controlar la dirección del motor | Puente H electrónico, contactores industriales | Se eligieron relés porque permiten invertir la dirección del motor de forma sencilla y segura utilizando las salidas del PLC LOGO. |


## Problema técnico encontrado
El principal problema que encontramos fue durante la programación en LOGO ya que era la primera vez que utilizabamos este programa y no estabamos familiarizados. Un problema que surgió fue que al adaptar el programa inicial a nuestros objetivos, no supimos como realizar las modificaciones.

## Solución aplicada
Asisitimos con el profesor quien nos ayudó y explicó un poco como funciona la lógica en LOGO, nos explicó como funciona cada compuerta lógica funcionaba que habiamos visto en otra clase y como podiamos utilizar cada una para realizar las acciones que buscabamos.

## Conexión con el curso
¿Qué concepto de MR2022 aplicaste esta semana?
Esta semana aplicamos conceptos de automatización y control propios de la ingeniería mecatrónica. Se trabajó en la integración de sensores, actuadores y el controlador PLC LOGO!, además de la implementación de la lógica de control y condiciones de seguridad mediante interlocks. Esto permitió comprender cómo se integran los sistemas mecánicos, eléctricos y de control para automatizar procesos que pueden aplicarse en la industria real.

## Autoevaluación
- ⬜ Muy perdido
- ⬜ Con dudas
- ☑️ Entendiendo
- ⬜ Dominando
- 
# Bitácora – Semana 3- Claudio

## Tema de la semana
(Sensores / Actuadores / Control / HMI)

## Actividades realizadas
Describe brevemente lo que trabajó el equipo.

## Decisiones de ingeniería
| Decisión | Alternativas | Justificación |
|--------|-------------|---------------|

## Problema técnico encontrado
Describe un problema concreto.

## Solución aplicada
Explica cómo se resolvió.

## Conexión con el curso
¿Qué concepto de MR2022 aplicaste esta semana?

## Autoevaluación
- ⬜ Muy perdido
- ⬜ Con dudas
- ⬜ Entendiendo
- ⬜ Dominando

# Bitácora – Semana 3- Joel

## Tema de la semana
Controles del sistema de la cortina automatizada.

## Actividades realizadas
Esta semana trabajamos en la parte de control del sistema de la cortina utilizando el PLC LOGO. Nos enfocamos en organizar la lógica del programa para que el motor pudiera subir y bajar correctamente según las señales de los sensores. También revisamos cómo integrar los sensores dentro de la lógica del control y realizamos pruebas para verificar que el sistema respondiera como se esperaba durante el funcionamiento.

## Decisiones de ingeniería
| Decisión | Alternativas | Justificación |
|--------|-------------|---------------|
| Utilizar un sensor óptico para detectar personas | No incluir detección de presencia | Se decidió incluirlo para mejorar la seguridad y evitar que la cortina pueda cerrar si hay alguien en la zona de movimiento. |
| Agregar un sensor capacitivo como paro del sistema | No incluir paro manual | Permite detener el sistema de forma rápida si ocurre una situación inesperada. |
| Configurar la activación del sistema mediante el sensor inductivo | Activar el sistema con otro tipo de sensor o activación manual | Se eligió usar el sensor inductivo para iniciar el mecanismo porque permite detectar automáticamente una condición de activación sin intervención directa del usuario. |

## Problema técnico encontrado
Queríamos que nuestro sistema funcionara de manera diferente, específicamente que el sensor inductivo fuera el que activara el mecanismo, mientras que el óptico y el capacitivo detuvieran el funcionamiento de la cortina. Sin embargo, al modificar la lógica del programa no obteníamos el resultado que esperábamos, ya que todavía no entendíamos completamente cómo funcionaba la lógica de programación dentro del PLC.

## Solución aplicada
Acudimos con el profesor Camilo, quien nos ayudó a entender mejor la lógica de control del sistema. Gracias a su explicación pudimos reorganizar el programa y manipular correctamente la lógica hasta lograr que el sistema funcionara de la manera que esperábamos.

## Conexión con el curso
Esta semana aplicamos conceptos de control vistos en el curso, especialmente la construcción de lógica de decisión utilizando sensores y compuertas lógicas dentro de un PLC. También trabajamos en cómo estructurar un sistema de control que combine señales de activación, sensores de posición y condiciones de seguridad para controlar el comportamiento de un actuador, en este caso el motor de la cortina.

## Autoevaluación
- ⬜ Muy perdido
- ⬜ Con dudas
- ☑️ Entendiendo
- ⬜ Dominando

# Bitácora – Semana 3- Sara

## Tema de la semana
(Sensores / Actuadores / Control / HMI)

## Actividades realizadas
Describe brevemente lo que trabajó el equipo.

## Decisiones de ingeniería
| Decisión | Alternativas | Justificación |
|--------|-------------|---------------|

## Problema técnico encontrado
Describe un problema concreto.

## Solución aplicada
Explica cómo se resolvió.

## Conexión con el curso
¿Qué concepto de MR2022 aplicaste esta semana?

## Autoevaluación
- ⬜ Muy perdido
- ⬜ Con dudas
- ⬜ Entendiendo
- ⬜ Dominando

