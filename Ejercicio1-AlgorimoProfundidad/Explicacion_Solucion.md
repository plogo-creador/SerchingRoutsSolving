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



### Esquema: E={} F={} T(i)= F

* **E={}:** Se refiere a los nodos ya explorados.
* **F={}:** Se refiere a los nodos de frontera (aún no explorados).
* **T(x):** Se refiere al nodo actual del que vamos a descubrir sus fronteras.
* **= F o = T:** Se refiere a si ha encontrado el nodo objetivo. En este caso "e", tiene dos variaciones: **F** (False) o **T** (True).

---

### Búsqueda de **e1**

E={} F={**i**} T(i)= F  
E={i} F={A, **B**} T(B)= F  
E={i, B} F={A, C, **D**} T(D)= F  
E={i, B, D} F={A, **C**} T(C)= F  
E={i, B, D, C} F={A, **E**} T(E)= F  
E={i, B, D, C, E} F={A, F, **G**} T(G)=