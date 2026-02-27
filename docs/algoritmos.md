# Lógica de Navegación y Algoritmo de Trémaux

## 1. Navegación Reactiva (Sensores)
Para mantener el robot centrado y evitar colisiones, utilizamos una lógica de decisión basada en los tres sensores de proximidad:

| Sensor Izq | Sensor Central | Sensor Der | Acción Sugerida |
| :--- | :--- | :--- | :--- |
| Libre | Bloqueado | Libre | Girar 90° (Elegir dirección según mapa) |
| Bloqueado | Bloqueado | Libre | Girar 90° Derecha |
| Libre | Libre | Bloqueado | Seguir recto (Alineación con pared izq.) |
| Bloqueado | Bloqueado | Bloqueado | Girar 180° (Callejón sin salida) |

### Control PID
Para garantizar un avance rectilíneo, implementamos un **Control PID (Proporcional, Integral, Derivativo)**. Este ajusta la velocidad diferencial de los motores basándose en la diferencia de distancia detectada por los sensores laterales, permitiendo que el robot se mantenga en el eje central del pasillo.

## 2. Resolución del Laberinto: Algoritmo de Trémaux
Dado que no contamos con un mapa previo, aplicamos el método de Trémaux (una variante de Búsqueda en Profundidad o DFS) para explorar el laberinto.

### Reglas de Implementación:
1.  **Marcado de Caminos:** Cada vez que el robot transita por un pasillo, incrementa un contador de "visitas" en nuestra matriz de memoria.
2.  **Intersecciones Nuevas:** Al llegar a un nodo no visitado, se elige cualquier dirección disponible.
3.  **Retorno:** Si el robot llega a un callejón sin salida o a una intersección donde todos los caminos nuevos están bloqueados, retrocede por el camino que tenga exactamente una marca.
4.  **Prevención de Bucles:** Nunca se debe entrar en un camino que ya tenga dos marcas (indicativo de que el camino ya fue explorado y descartado).