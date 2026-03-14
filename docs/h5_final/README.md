# Hito Final – Prototipo Funcional

## Descripción del prototipo
El prototipo desarrollado consiste en un sistema de control para una cortina automática utilizando un PLC Siemens LOGO. El sistema funciona mediante distintos sensores que detectan condiciones específicas y envían señales al controlador.

El funcionamiento inicia cuando el sensor inductivo detecta un objeto metálico, lo que activa el sistema siempre y cuando el sensor magnético superior confirme que la cortina se encuentra en la posición inicial. Una vez cumplida esta condición, el PLC activa el motor para comenzar el movimiento de la cortina.

Durante el recorrido, los sensores magnéticos permiten identificar la posición de la cortina. Cuando la cortina llega a la posición inferior, el sistema detiene el motor y activa un temporizador de 10 segundos. Después de este tiempo, el controlador activa nuevamente el motor para que la cortina suba hasta regresar a la posición superior.

El sistema también incluye condiciones de seguridad. Si el sensor óptico detecta la presencia de una persona o si el sensor capacitivo se activa, el sistema detiene inmediatamente el movimiento del motor. Además, el sistema cuenta con una torre de luz que indica el estado de operación mediante luces roja y verde.

## Evidencias
[(Link al video)](https://www.youtube.com/shorts/yC3Cw31sUlQ)

![Imagen del equipo](https://github.com/MaxAmCam/Proyecto_Cortina_Industrial/blob/bc93e771a5abd281b9d2c3f3eba4050d9089960b/docs/GIFTS/WhatsApp%20Image%202026-03-12%20at%206.19.11%20PM.jpeg)

## Validación del sistema
El sistema cumple con los requerimientos iniciales del proyecto, ya que logra integrar sensores, actuadores y un controlador programable para automatizar el movimiento de una cortina. Durante las pruebas se verificó que el sistema inicia correctamente, que el motor realiza los movimientos de subida y bajada según la lógica programada y que las condiciones de seguridad detienen el sistema cuando se detecta una persona o se activa el sensor capacitivo.

Además, el sistema demuestra una integración correcta entre el hardware y el software, logrando un funcionamiento estable después de realizar los ajustes necesarios durante las pruebas.

## Reflexión final
Uno de los principales aprendizajes de este proyecto fue comprender cómo integrar sensores, actuadores y un PLC dentro de un sistema mecatrónico real. Durante el desarrollo del proyecto se aprendió a diseñar la lógica de control, a realizar pruebas del sistema y a solucionar problemas tanto mecánicos como eléctricos.

También fue importante entender cómo pequeñas modificaciones en la lógica de control pueden afectar el comportamiento completo del sistema. Finalmente, el proyecto permitió aplicar de forma práctica los conceptos vistos en el curso y entender mejor cómo se implementan sistemas automatizados en la ingeniería.
