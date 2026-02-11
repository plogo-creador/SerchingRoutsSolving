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
## Análisis de Búsqueda en Profundidad (DFS)

Se analiza el comportamiento del algoritmo con diferentes límites de profundidad, respetando estrictamente el orden de prioridad: **Arriba (↑), Abajo (↓), Izquierda (←), Derecha (→)**.

---

### Caso A: Límite de Profundidad L = 5

La traza de ejecución sigue el camino más profundo permitido por la prioridad de los operadores:

1.  **i (5,4)** expande a **A (4,4)** `[Arriba]` (Profundidad 1).
2.  **A (4,4)** expande a **B (4,3)** `[Izquierda]` (Profundidad 2).
    * **Nota:** B no tiene salidas válidas por la presencia de obstáculos y muros.
3.  **Backtrack** a **A**, expande a **C (4,5)** `[Derecha]` (Profundidad 2).
4.  **C (4,5)** expande a **D (3,5)** `[Arriba]` (Profundidad 3).
5.  **D (3,5)** expande a **E (2,5)** `[Arriba]` (Profundidad 4).
6.  **E (2,5)** expande a **F (2,4)** `[Izquierda]` (Profundidad 5).
7.  **F (2,4)** no puede expandirse más: el siguiente nodo **(2,3)** requeriría **Profundidad 6**.

**Resultados del Caso A:**
* **Resultado:** Fracaso por corte (**Cutoff**).
* **Tipo de error:** Fracaso incompleto. La meta existe en el espacio de estados, pero no es alcanzable dentro del límite de profundidad establecido.

---

### Caso B: Límite de Profundidad L = 6

Al incrementar el límite de búsqueda a 6, el algoritmo permite una expansión adicional desde el último nodo abierto en la frontera:

* Desde **F (2,4)** en el nivel 5, el algoritmo ahora puede ejecutar el operador `[Izquierda]`.
* Se genera y reconoce el nodo **e (2,3)** en el **Nivel 6**.

**Resultados del Caso B:**
* **Resultado:** Éxito.
* **Conclusión:** La solución es hallada al coincidir el límite de profundidad con el nivel en el que se encuentra el objetivo.

---