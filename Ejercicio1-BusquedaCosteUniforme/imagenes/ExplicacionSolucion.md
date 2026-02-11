# Ejercicio 1: Búsqueda de Coste Uniforme

En este apartado se detalla la resolución del **Ejercicio 1** utilizando el algoritmo de búsqueda de coste uniforme. 

## 1. Configuración del Algoritmo
* **Tipo de búsqueda:** FIFO (Búsqueda por coste uniforme).
* **Prioridad de expansión (Orden):** 
    1.  ↑ (Arriba): Coste 1
    2.  ↓ (Abajo): Coste 1
    3.  ← (Izquierda): Coste 2
    4.  → (Derecha): Coste 2

Extrae el nodo con menor coste acumulado $g(n)$.

| Nodo | Movimiento | Coste Paso | $g(n)$ Total |
| :--- | :--- | :--- | :--- |
| `i` | - | 0 | 0 |
| `A` | Arriba | 1 | 1 |
| `B` | Abajo | 1 | 1 |
| `D` | Derecha (desde A) | 2 | 3 |
| `G` | Arriba (desde D) | 1 | 4 |
| `I` | Arriba (desde G) | 1 | 5 |
| `K` | Izquierda (desde I)| 2 | 7 |
| `e` | Izquierda (desde K)| 2 | **9** |
