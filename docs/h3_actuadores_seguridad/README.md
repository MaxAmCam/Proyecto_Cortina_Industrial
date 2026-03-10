# Hito 3 – Control e Integración

## Descripción de la lógica de control
El programa se desarrolló en Siemens LOGO! para controlar el movimiento de una cortina automática utilizando distintos sensores. La idea principal es que la cortina pueda subir y bajar de forma controlada, pero también que el sistema se detenga si ocurre alguna situación de seguridad.

El sistema puede iniciar su funcionamiento cuando el sensor inductivo detecta una condición de activación, pero solo si el sensor magnético superior detecta el imán. Esto se hizo para asegurarse de que la cortina realmente está en la posición superior antes de comenzar el ciclo.

Durante el funcionamiento, el movimiento de la cortina se controla con dos salidas: una para bajar el motor y otra para subir. Además, se utilizan tres sensores magnéticos (arriba, medio y abajo) para saber en qué posición se encuentra la cortina en todo momento y así evitar que el motor siga moviéndose cuando ya llegó a su límite.

Cuando la cortina llega hasta abajo y el sensor magnético inferior detecta el imán, el sistema activa un temporizador de 10 segundos. Durante ese tiempo la cortina permanece detenida y, una vez que se cumple el tiempo, el sistema activa nuevamente el motor para que la cortina vuelva a subir automáticamente.

También se añadieron condiciones de seguridad. Si el sensor óptico detecta una persona, el sistema detiene el movimiento de la cortina para evitar que alguien pueda quedar atrapado. De la misma manera, si se activa el sensor capacitivo, la cortina también se detiene.

Por último, el sistema cuenta con dos luces indicadoras: la lámpara roja se enciende mientras la cortina está en movimiento, ya sea subiendo o bajando. Cuando la cortina llega completamente abajo, se enciende la lámpara verde, indicando que el sistema se encuentra en esa posición y el temporizador está en espera antes de que la cortina vuelva a subir.

## Entradas y salidas
| Entrada | Tipo | Función |
|--------|------|---------|

| Salida | Tipo | Función |
|--------|------|---------|

## Pruebas realizadas
| Prueba | Resultado esperado | Resultado obtenido |
|------|------------------|------------------|

## Ajustes realizados
Describe cambios hechos tras las pruebas.

## Tabla de interlocks
| Interlock                            | Condición prohibida                                       | Señales involucradas                           | Acción del sistema                      | Descripción |
|-------------------------------------|------------------------------------------------------------|-----------------------------------------------|-----------------------------------------|-------------|
| Interlock de habilitación            | Intentar mover la cortina sin habilitación del sistema    | I1 (capacitivo), I2/I3 (sensores de detección) | El motor no se activa                   | El sistema requiere la señal de habilitación antes de iniciar el movimiento. Si se intenta activar el movimiento sin esta condición, el PLC bloquea la orden. |
| Interlock de motores                 | Activar simultáneamente motor de subida y motor de bajada | Q1 (motor bajar), Q2 (motor subir)             | Se bloquea una de las salidas           | El sistema impide que ambos motores se activen al mismo tiempo para evitar daños mecánicos o eléctricos en el actuador. |
| Interlock de límite superior         | Intentar subir cuando la cortina ya está arriba           | I4 (sensor límite superior)                    | Se bloquea el motor de subida           | Cuando el sensor superior detecta que la cortina llegó a la altura máxima, el sistema impide seguir activando el motor de subida. |
| Interlock de límite inferior         | Intentar bajar cuando la cortina ya está abajo            | I5 (sensor límite inferior)                    | Se bloquea el motor de bajada           | Cuando la cortina alcanza la posición inferior, el sistema evita que el motor continúe bajando para prevenir daños mecánicos. |
| Interlock de seguridad por obstáculo | Bajar la cortina cuando se detecta una persona u objeto   | Sensor de obstáculo                            | Se detiene la bajada y se activa alarma | Si el sensor detecta un obstáculo durante el cierre, el sistema detiene el movimiento y genera una señal de alerta para evitar accidentes. |
