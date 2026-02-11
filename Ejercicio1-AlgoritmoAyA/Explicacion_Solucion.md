# 1. A* (con tabla completa g, h, f)

### Fórmulas

- \( g(n) = \text{coste acumulado} \)  
- \( h(n) = | \text{fila} - 2 | + | \text{col} - 3 | \)  
- \( f(n) = g(n) + h(n) \)  

### Tabla de desarrollo A*

| Iter | Nodo   | g | h | f | Frontera tras expansión |
|------|--------|---|---|---|------------------------|
| 0    | (4,4)  | 0 | 3 | 3 | —                      |
| 1    | (4,4)  |   |   |   | (5,4)[1,4,5], (4,5)[2,4,6] |
| 2    | (5,4)  | 1 | 4 | 5 | (4,5)[2,4,6], (6,4)[2,5,7], (5,3)[3,3,6], (5,5)[3,5,8] |
| 3    | (4,5)  | 2 | 4 | 6 | + (3,5)[3,3,6]         |
| 4    | (5,3)  | 3 | 3 | 6 | + (5,2)[5,2,7]         |
| 5    | (3,5)  | 3 | 3 | 6 | + (2,5)[4,2,6]         |
| 6    | (2,5)  | 4 | 2 | 6 | + (2,4)[6,1,7]         |
| 7    | (2,4)  | 6 | 1 | 7 | + (2,3)[8,0,8]         |
| 8    | (2,3)  | 8 | 0 | 8 | SOLUCIÓN               |

### Explicación

- A* prioriza menor \( f \).  
- Observamos que mantiene \( f \approx 6 \) durante gran parte del proceso y dirige la búsqueda hacia el objetivo.  
- Explora menos nodos que BFS.  

### Profundidad solución

5

### Coste óptimo

8
