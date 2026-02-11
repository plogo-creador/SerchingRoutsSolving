1. Búsqueda en Anchura (BFS)
Este algoritmo expande los nodos nivel por nivel. Utiliza una cola (FIFO) para la frontera.

| Paso | Nodo Expandido | Frontera (Cola de Nodos Generados) | Explorados |
| :--- | :--- | :--- | :--- |
| 0 | - | `[i]` | `[]` |
| 1 | `i(5,4)` | `[A(4,4), B(6,4)]` | `[i]` |
| 2 | `A(4,4)` | `[B(6,4), C(4,3), D(4,5)]` | `[i, A]` |
| 3 | `B(6,4)` | `[C(4,3), D(4,5), E(6,3), F(6,5)]` | `[i, A, B]` |
| 4 | `C(4,3)` | `[D(4,5), E(6,3), F(6,5)]` | `[i, A, B, C]` |
| 5 | `D(4,5)` | `[E(6,3), F(6,5), G(3,5)]` | `[i, A, B, C, D]` |
| 6 | `E(6,3)` | `[F(6,5), G(3,5), H(6,2)]` | `[i, A, B, C, D, E]` |
| 7 | `F(6,5)` | `[G(3,5), H(6,2)]` | `[i, A, B, C, D, E, F]` |
| 8 | `G(3,5)` | `[H(6,2), I(2,5)]` | `[i, A, B, C, D, E, F, G]` |
| 9 | `H(6,2)` | `[I(2,5), J(6,1)]` | `[i, A, B, C, D, E, F, G, H]` |
| 10 | `I(2,5)` | `[J(6,1), K(2,4)]` | `[i, A, B, C, D, E, F, G, H, I]` |
| 11 | `J(6,1)` | `[K(2,4), L(5,1)]` | `[i, A, B, C, D, E, F, G, H, I, J]` |
| 12 | `K(2,4)` | `[L(5,1), e(2,3)]` | **SOLUCIÓN ENCONTRADA** |

Nodos Generados: A(4,4), B(6,4), C(4,3), D(4,5), E(6,3), F(6,5), G(3,5), H(6,2), I(2,5), J(6,1), K(2,4), L(5,1).

Test Objetivo: Se activa al extraer K de la frontera y generar su vecino izquierdo (2,3), que es e.

Profundidad de la solución: 6.

Camino: i -> A -> D -> G -> I -> K -> e.