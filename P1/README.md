# Práctica 1: Aspiradora autónoma (Basic Vacuum Cleaner)

Esta práctica pertenece a la plataforma [Robotics Academy](https://jderobot.github.io/RoboticsAcademy/exercises/MobileRobots/vacuum_cleaner) de JdeRobot. Consiste en programar el comportamiento de un robot aspiradora para que limpie la mayor superficie posible de una vivienda simulada, sin conocer el mapa de antemano y sin una estrategia de cobertura predefinida.

El reto principal es que el robot debe decidir por sí mismo cómo moverse, evitar obstáculos y no quedarse atascado, usando solo la información de sus sensores.

---

## Intentos

### Intento 1: Movimiento en espiral

📹 [P1_espiral1_robotica.mp4](P1_espiral1_robotica.mp4)

La primera estrategia fue una espiral, con la idea de barrer zonas de forma progresiva desde un punto.

**Resultado:** no funcionó. El robot no conseguía avanzar lo suficiente como para llegar a zonas nuevas de la casa, así que se quedaba limpiando siempre el mismo entorno.

---

### Intento 2: Espiral con sentido de giro fijo

📹 [P1_espiral_p2_v2.mp4](P1_espiral_p2_v2.mp4)

En esta versión eliminé la aleatoriedad en el sentido de rotación. El robot pasó a girar siempre hacia la izquierda, con una cantidad fija de movimiento.

**Resultado:** empeoró. Al ser el comportamiento totalmente predecible, resultó aún más fácil que el robot se atascara. Se ve claramente al llegar a una habitación, donde empieza a rotar de forma indefinida sin lograr salir.

---

### Intento 3: Aleatoriedad total

📹 [p1_gemarcos_aspiradora.mp4](p1_gemarcos_aspiradora.mp4)

El cambio definitivo fue aleatorizar todos los valores del movimiento, no solo el sentido de giro.

**Resultado:** funcionó. Al ser aleatorio, el robot acaba encontrando antes o después el movimiento adecuado para desatascarse. En el vídeo estuvo atascado durante bastante tiempo, pero gracias a esa aleatoriedad logró liberarse y continuar, **limpiando más del 60 % de la casa**.

---

## Conclusiones

- Una estrategia determinista y ordenada (la espiral) es frágil en entornos con obstáculos: cualquier situación no prevista puede bloquear al robot de forma permanente.
- Reducir la aleatoriedad empeoró el resultado, porque eliminó la capacidad del robot de escapar de situaciones de bloqueo.
- Introducir aleatoriedad en todos los parámetros garantiza que el robot, con tiempo suficiente, pruebe movimientos distintos hasta salir de cualquier atasco, a costa de una cobertura menos eficiente y más lenta.

> El código de la solución no se incluye en este repositorio.
