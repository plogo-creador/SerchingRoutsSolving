### Para empezar, ¿qué es un algoritmo de Profundidad?

El algoritmo de búsqueda en Profundidad es un algoritmo de búsqueda no informada que explora el espacio de estados avanzando lo más profundo posible por cada rama antes de retroceder.  
Parte del estado inicial y continúa explorando un camino hasta que alcanza el objetivo o no puede seguir avanzando, momento en el que retrocede para explorar otras ramas.

Este algoritmo utiliza una **pila (LIFO)** y es eficiente en uso de memoria, aunque no garantiza encontrar la solución más corta.

![MapaRuta1](imagenes/Búsqueda_por_profundidad.png)

---

### Consideraciones:

* Para aquellos algoritmos en los que no es relevante el coste, el orden de los operadores (movimientos) es: **arriba, abajo, izquierda, derecha**.
* Si algún algoritmo no controla los ciclos, supondremos que existen mecanismos para eliminarlos.
* **El coste del movimiento:**
    * **Vertical:** 1
    * **Horizontal:** 2

---

## Explicación de la búsqueda
Usamos un **Algoritmo LIFO (Pila)**.

**Su regla de orden:** El elemento más reciente que guardas es el primero que tienes que sacar. No puedes sacar lo que está debajo sin quitar lo que pusiste al final.

**Explicación ejemplificada:** Una pila de libros o la bandeja de entrada de documentos físicos (lo último que llega se queda arriba y es lo primero que atiendes).
---
Límite de Profundidad 5
i expande a A (4,4) [Arriba]. (Prof. 1)

A expande a B (4,3) [Izquierda]. (Prof. 2) -> B no tiene salidas válidas.

Backtrack a A, expande a C (4,5) [Derecha]. (Prof. 2)

C expande a D (3,5) [Arriba]. (Prof. 3)

D expande a E (2,5) [Arriba]. (Prof. 4)

E expande a F (2,4) [Izquierda]. (Prof. 5)

F no puede expandirse más porque el siguiente nodo (2,3) estaría en profundidad 6.

Resultado: Fracaso por corte (Cutoff).

Tipo de fracaso: Fracaso incompleto. La meta existe pero no es alcanzable dentro del límite.

Límite de Profundidad 6
Al aumentar el límite a 6, el nodo F puede expandirse hacia la izquierda para generar el nodo e (2,3).

Resultado: Éxito. La solución se encuentra justo en el límite.