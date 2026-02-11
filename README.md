# SerchingRoutsSolving
Ejercicios MIA para encontrar rutas mediante algoritmos

## Ejercicio 1

Considérese el problema de encontrar un camino, en la situación representada en la figura, desde la posición $i$ hasta la posición $e$. El NPC (*non-player character*) puede moverse de forma horizontal y vertical, un solo cuadrado en cada movimiento (cada movimiento tiene coste uno). Las zonas sombreadas impiden el paso del NPC a través de ellas.

!["Mapa ejercicio 1"](./mapa_ejercicio_1.png)


### Algoritmos a aplicar:

Aplicaremos los distintos algoritmos de búsqueda que se tratan en las sesiones del módulo para resolver el problema, en el siguiente orden:

1. Búsqueda en anchura.
2. Búsqueda en profundidad.
3. Búsqueda de coste uniforme.
4. Algoritmos **A** y **A***.

### Consideraciones:

- Para aquellos algoritmos en los que no es relevante el coste, el orden de los operadores (movimientos) es: **arriba, abajo, izquierda, derecha**.
- Si algún algoritmo no controla los ciclos, supondremos que existen mecanismos para eliminarlos.
- El **coste del movimiento**:
  - **Vertical**: 1.
  - **Horizontal**: 2.
- Para el algoritmo **A** se utilizará la **distancia Manhattan** como heurística:

$$ h(n) = {distancia \ horizontal} + {distancia \ vertical} $$

- En el ejemplo, la distancia Manhattan entre $i$ y $e$ es $4$.

### Preguntas específicas:

1. En la búsqueda en profundidad, el límite de profundidad es 5:
   - Describe qué sucede.
   - Indica el tipo de fracaso (si lo hay).
   - ¿Qué sucede si aumentamos el límite de profundidad a 6?

### Representación de la solución:

- Resuelve el problema con cada uno de los algoritmos de búsqueda propuestos.
- Indica, para cada algoritmo, cuál se aplica para extraer los nodos de la frontera.
- Escribe:
  - La evolución del conjunto de nodos frontera.
  - El conjunto de nodos explorados durante el desarrollo del algoritmo.
  - La función coste y la heurística en los algoritmos que hagan uso de ellas.
- En la figura:
  - Nombra (enumera) los nodos según el orden en que son generados (incluidos en la frontera).
- Indica:
  - Cuándo la función test objetivo determina que el nodo chequeado es la solución.
  - La profundidad en la que se encuentra la solución.
- Razona y explica qué nodos y por qué conforman la solución.
- Representa:
  - El camino que conforma la solución (con una flecha en la figura).
  - El árbol de búsquedas.

---

### Programación del algoritmo

La búsqueda A* sobre este problema está programada aquí:
["Problem solving searching A*"](https://github.com/dfleta/problem-solving-searching)

---

## Ejercicio 2

### Preguntas específicas:

### Ejercicio 2

**1. La heurística utilizada en el algoritmo A, ¿es admisible? ¿Por qué?**
Sí, es admisible porque nunca da un coste mayor al real. Al usar la distancia Manhattan, calculamos el camino más corto posible como si no hubiera obstáculos; por eso, el coste real siempre será igual o mayor que esa estimación, pero nunca menor.

**2. ¿Podemos decir que el algoritmo es A*?**
Sí, porque cumple las dos condiciones: usa la fórmula $f(n) = g(n) + h(n)$ para elegir qué nodos expandir y la heurística que usamos es admisible. Al combinar estas dos cosas, el algoritmo ya se considera A*.
