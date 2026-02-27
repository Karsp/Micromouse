# Estructura del Mapa y Memoria

Para representar el laberinto de 8x8 o de 16x16 casillas, utilizamos una **matriz extendida** que contempla tanto las celdas transitables (nodos) como los muros intermedios.

## Estructura de la Matriz
La matriz se inicializa considerando que entre cada celda "caminable" existe una posición que representa el muro. 

### Estados de las Celdas:
* **Pasillos (Nodos):**
    * `0`: Sin descubrir.
    * `1, 2, ...n`: Número de veces que el robot ha transitado por la celda.
    * `-1`: Bloqueado/Callejón confirmado.
* **Muros:**
    * `[ ]` (Vacío): Camino abierto.
    * `[#]` (Lleno): Obstáculo físico detectado.
    * `[0]` (Desconocido): Pendiente de exploración.

### Notes


![MapNotes](https://github.com/user-attachments/assets/94e3267b-8e86-45b4-a223-bf6bbde086f1)


## Lógica de Desplazamiento
El robot se desplaza virtualmente de 2 en 2 posiciones en la matriz. Antes de realizar un movimiento físico, el sistema consulta el estado del "muro" situado en la posición intermedia ($n+1$) para verificar si la transición es posible.

> **Nota de implementación:** Al iniciar, se pre-cargan los muros perimetrales y las esquinas (nodos inaccesibles por diseño de la matriz) como estados `[#]` para optimizar el cálculo de rutas.
