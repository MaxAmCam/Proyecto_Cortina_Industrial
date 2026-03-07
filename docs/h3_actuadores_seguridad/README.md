# Hito 3 – Control e Integración

## Descripción de la lógica de control
Explica la secuencia o lógica implementada en LOGO.

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
