# Hito 3 – Control e Integración

## Descripción de la lógica de control
El programa se desarrolló en Siemens LOGO! para controlar el movimiento de una cortina automática utilizando distintos sensores. La idea principal es que la cortina pueda subir y bajar de forma controlada, pero también que el sistema se detenga si ocurre alguna situación de seguridad.

El sistema puede iniciar su funcionamiento cuando el sensor inductivo detecta una condición de activación, pero solo si el sensor magnético superior detecta el imán. Esto se hizo para asegurarse de que la cortina realmente está en la posición superior antes de comenzar el ciclo.

Durante el funcionamiento, el movimiento de la cortina se controla con dos salidas: una para bajar el motor y otra para subir. Además, se utilizan tres sensores magnéticos (arriba, medio y abajo) para saber en qué posición se encuentra la cortina en todo momento y así evitar que el motor siga moviéndose cuando ya llegó a su límite.

Cuando la cortina llega hasta abajo y el sensor magnético inferior detecta el imán, el sistema activa un temporizador de 10 segundos. Durante ese tiempo la cortina permanece detenida y, una vez que se cumple el tiempo, el sistema activa nuevamente el motor para que la cortina vuelva a subir automáticamente.

También se añadieron condiciones de seguridad. Si el sensor óptico detecta una persona, el sistema detiene el movimiento de la cortina para evitar que alguien pueda quedar atrapado. De la misma manera, si se activa el sensor capacitivo, la cortina también se detiene.

Por último, el sistema cuenta con dos luces indicadoras: la lámpara roja se enciende mientras la cortina está en movimiento, ya sea subiendo o bajando. Cuando la cortina llega completamente abajo, se enciende la lámpara verde, indicando que el sistema se encuentra en esa posición y el temporizador está en espera antes de que la cortina vuelva a subir.

## Entradas y salidas

### Entradas
| Entrada | Tipo | Función |
|--------|------|---------|
| I1 | Sensor inductivo | Detecta la condición de activación del sistema. Solo permite iniciar el ciclo cuando el sensor magnético superior confirma que la cortina está en la posición inicial. |
| I2 | Sensor capacitivo | Funciona como paro o control de seguridad manual. Cuando se activa, el sistema detiene el movimiento de la cortina. |
| I3 | Sensor óptico | Detecta la presencia de una persona u objeto en la zona de la cortina. Si se activa durante el movimiento, el sistema detiene la cortina para evitar accidentes. |
| I4 | Sensor magnético superior | Detecta que la cortina está completamente arriba y permite que el sistema pueda iniciar el ciclo de operación. |
| I5 | Sensor magnético medio | Indica que la cortina se encuentra en una posición intermedia durante el recorrido. |
| I6 | Sensor magnético inferior | Detecta que la cortina ha llegado completamente abajo y activa el temporizador de 10 segundos antes de iniciar la subida. |

### Salidas
| Salida | Tipo | Función |
|--------|------|---------|
| Q1 | Motor | Activa el motor para bajar la cortina. |
| Q2 | Motor | Activa el motor para subir la cortina. |
| Q3 | Lámpara roja | Se enciende cuando la cortina está en movimiento, ya sea subiendo o bajando. |
| Q4 | Lámpara verde | Se enciende cuando la cortina ha llegado completamente abajo y permanece detenida durante el temporizador. |

## Esquema funcional 
![Esquema](../GIFTS/Esquemafinal.png)

## Pruebas realizadas
| Prueba              | Resultado esperado                                                                 | Resultado obtenido                                      |
|---------------------|------------------------------------------------------------------------------------|---------------------------------------------------------|
| Sensor magnético    | Encender la lámpara ANDON mientras la cortina esté a la mitad o en parada, y subir la cortina 10s después de estar en su punto más bajo | Funcionó con éxito                                      |
| Sensor Infrarrojo   | Parada de emergencia al detectar a una persona u objeto frente a la cortina        | El sensor detectó con éxito cualquier acercamiento y detuvo el motor |
| Sensor Capacitivo   | Parada de emergencia al ser presionado                                             | Funcionó con éxito                                      |
| Sensor Inductivo    | Dar inicio al movimiento de la cortina                                             | Detecta con éxito objetos metálicos para dar inicio al sistema |


## Ajustes realizados
Tuvimos que realizar cambios en el código para hacer que el sensor inductivo de inicio al movimiento del motor, y que los sensores infrarrojo y capacitivo hagan paradas de emergencia.

## Evidencia de seguridad (prueba de interlocks)
Aqui poner el video

## Tabla de interlocks
| Interlock | Condición prohibida | Señales involucradas | Acción del sistema | Descripción |
|-----------|---------------------|----------------------|-------------------|-------------|
| Interlock de habilitación | Intentar mover la cortina sin habilitación del sistema | I2 (sensor inductivo), I4 (sensor magnético superior) | El motor no se activa | El sistema solo permite iniciar el ciclo cuando el sensor inductivo detecta la condición de activación y el sensor magnético superior confirma que la cortina está en la posición inicial. |
| Interlock de motores | Activar simultáneamente motor de subida y motor de bajada | Q1 (motor bajar), Q2 (motor subir) | Se bloquea una de las salidas | El sistema impide que ambos motores se activen al mismo tiempo para evitar daños mecánicos o eléctricos en el actuador. |
| Interlock de límite superior | Intentar subir cuando la cortina ya está arriba | I4 (sensor magnético superior) | Se bloquea el motor de subida | Cuando el sensor superior detecta que la cortina llegó a la altura máxima, el sistema impide seguir activando el motor de subida. |
| Interlock de límite inferior | Intentar bajar cuando la cortina ya está abajo | I6 (sensor magnético inferior) | Se bloquea el motor de bajada | Cuando la cortina alcanza la posición inferior, el sistema evita que el motor continúe bajando para prevenir daños mecánicos. |
| Interlock de seguridad por obstáculo | Bajar la cortina cuando se detecta una persona u objeto | I3 (sensor óptico) | Se detiene el movimiento | Si el sensor óptico detecta una persona u objeto durante el movimiento, el sistema detiene la cortina para evitar accidentes. |
| Interlock de paro de emergencia | Continuar el movimiento cuando se activa el paro manual | I1 (sensor capacitivo) | Se detiene inmediatamente el sistema | El sensor capacitivo funciona como un paro manual de seguridad. Cuando se activa, el sistema cancela el movimiento de la cortina para prevenir riesgos. |

## Evidencia del funcionamiento correcto de la torre de luz
![Semaforo](../GIFTS/Funcionamientosemaforo.gif)

La torre de luz permite identificar visualmente el estado de funcionamiento del sistema. La luz roja se enciende cuando la cortina está en movimiento, ya sea durante la subida o la bajada, indicando que el mecanismo se encuentra operando. Por otro lado, la luz verde se enciende cuando la cortina ha llegado completamente a la posición inferior y permanece detenida mientras se cumple el temporizador antes de iniciar nuevamente la subida.

