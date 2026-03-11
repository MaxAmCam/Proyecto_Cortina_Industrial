# Hito 4 – Validación Funcional y HMI
## Objetivo del hito
Validar el funcionamiento integrado del sistema mecatrónico y la interacción con el
usuario mediante HMI.

## Estado general del sistema
Marca el estado actual del sistema:
- No funcional ⬜
- Parcialmente funcional ⬜
- Funcional con fallas ⬜
- Funcional estable ☑️
---
## Secuencia de operación validada
1. El sistema inicia en estado de reposo con la cortina en la posición superior, detectada por el sensor magnético superior.

2. El usuario acerca un objeto metálico al sensor inductivo, lo cual envía la señal de activación al PLC.

3. El PLC verifica que el sensor magnético superior esté activo, confirmando que la cortina se encuentra en su posición inicial antes de iniciar el ciclo.

4. Una vez validada esta condición, el controlador activa el motor en sentido de bajada para comenzar el movimiento de la cortina.

5. Durante el recorrido, los sensores magnéticos permiten al sistema conocer la posición de la cortina. Cuando se detecta la posición intermedia junto con el sensor superior, se activa la luz roja de la torre de señalización indicando estado de operación.

6. Mientras la cortina se encuentra en movimiento, el sistema monitorea continuamente el sensor óptico y el sensor capacitivo como condiciones de seguridad.

7. Si el sensor óptico detecta una persona u objeto, o si se activa el sensor capacitivo, el PLC detiene inmediatamente el motor.

8. Si no ocurre ninguna condición de seguridad, la cortina continúa descendiendo hasta que el sensor magnético inferior detecta el final del recorrido.

9. Al activarse el sensor inferior, el PLC detiene el motor, enciende la luz verde y activa un temporizador de 10 segundos.

10. Una vez finalizado el temporizador, el PLC activa el motor en sentido de subida hasta que el sensor magnético superior vuelve a detectarse, regresando el sistema a su estado inicial.
---
## Validación de sensores
| Sensor | Condición probada | Resultado esperado | Resultado obtenido |
|------|------------------|------------------|------------------|
| Sensor inductivo | Acercar un objeto metálico al sensor | El sistema debe iniciar el ciclo de operación de la cortina | El sensor detectó correctamente el objeto metálico y el sistema inició el movimiento |
| Sensor óptico | Colocar una mano u objeto frente al sensor | El sistema debe detener el movimiento por seguridad | El sensor detectó correctamente la presencia y el sistema se detuvo inmediatamente |
| Sensor capacitivo | Activar el sensor presionándolo | El sistema debe detener el motor como paro de emergencia | El sistema se detuvo correctamente al activar el sensor |
| Sensor magnético superior | Cortina en la posición superior | El sistema debe permitir el inicio del ciclo | El sistema solo inicia cuando la cortina está en esta posición |
| Sensor magnético medio | Cortina en la posición intermedia | El sistema debe reconocer la posición intermedia durante el recorrido | El sistema detectó correctamente la posición de la cortina |
| Sensor magnético inferior | Cortina en la posición inferior | El sistema debe detener el motor y activar el temporizador antes de la subida | El sistema detectó correctamente la posición inferior y activó el temporizador |

---
## Validación de actuadores
| Actuador | Acción | Resultado esperado | Resultado obtenido |
|--------|--------|------------------|------------------|
| Motor de la cortina | Activación del motor para bajar la cortina | La cortina debe descender hasta que se detecte la posición inferior | El motor funcionó correctamente y la cortina descendió hasta su posición inferior |
| Motor de la cortina | Activación del motor para subir la cortina | La cortina debe elevarse hasta alcanzar la posición superior | El motor elevó la cortina correctamente hasta su posición inicial |
| Torre de luz roja | Activación de la señal luminosa durante condiciones de operación | Indicar visualmente que el sistema se encuentra en estado de operación | La luz roja se encendió cuando se detectó la condición correspondiente del sistema |
| Torre de luz verde | Activación de la señal luminosa en la posición inferior | Indicar que la cortina llegó al final del recorrido y está en espera | La luz verde se encendió correctamente cuando la cortina llegó a la posición inferior |

---
## Validación del controlador (LOGO)
Describe:
- Temporizaciones
- Condiciones lógicas
- Interlocks o seguridades implementadas
---
## Fallas detectadas
Describe **máximo 3** fallas relevantes encontradas durante la validación.
---
## Ajustes realizados
| Falla | Ajuste realizado | Resultado |
|-------|------------------|-----------|
| Atascamiento en la cortina | Volteamos la cortina y corregimos fallas en la impresión 3D | La cortina funcionó correctamente |
| El LOGO! no encendía | Cambiamos el fusible | El LOGO! se encendió sin problemas |
| El HMI no cargó correctamente en el LOGO! | Volvimos a realizar la instalación | El programa funcionó de manera correcta |

---
## Preparación para demostración final
Indica qué está listo y qué falta por afinar:
- Lógica de control☑️
- HMI☑️
- Cableado☑️
- Seguridad☑️
- Evidencias (video/fotos)☑️
---
## Reflexión breve del equipo
¿Qué fue lo más crítico de esta etapa?
