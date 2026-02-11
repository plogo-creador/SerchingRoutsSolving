# Ejercicio 3: Planificación de Rutas mediante Búsqueda de Coste Uniforme (UCS)

**Objetivo:** Determinar la ruta mínima en kilómetros entre **Ourense** y **Calatayud**.
**Algoritmo:** Búsqueda de Coste Uniforme. La selección de nodos se basa exclusivamente en el coste acumulado $g(n)$, priorizando siempre el valor más bajo en la frontera.

---

## 1. Registro de Ejecución (Trazabilidad)

A continuación se detalla la evolución de la búsqueda. Los nodos en la **Frontera** se mantienen ordenados por su coste acumulado.

| Iteración | Nodo Extraído | Sucesores Generados (Coste total) | Estado de la Frontera (Nodo, Coste) |
| :--- | :--- | :--- | :--- |
| 1 | **Ourense (0)** | Ponferrada (175), Benavente (236) | `[(Ponferrada, 175), (Benavente, 236)]` |
| 2 | **Ponferrada (175)** | León (288), Benavente (300*) | `[(Benavente, 236), (León, 288)]` |
| 3 | **Benavente (236)** | Palencia (348), Valladolid (348) | `[(León, 288), (Palencia, 348), (Valladolid, 348)]` |
| 4 | **León (288)** | Osorno (409) | `[(Palencia, 348), (Valladolid, 348), (Osorno, 409)]` |
| 5 | **Palencia (348)** | Osorno (**397**), Burgos (440) | `[(Valladolid, 348), (Osorno, 397), (Burgos, 440)]` |
| 6 | **Valladolid (348)** | Aranda (443) | `[(Osorno, 397), (Burgos, 440), (Aranda, 443)]` |
| 7 | **Osorno (397)** | Burgos (456*) | `[(Burgos, 440), (Aranda, 443)]` |
| 8 | **Burgos (440)** | Soria (583), Logroño (590) | `[(Aranda, 443), (Soria, 583), (Logroño, 590)]` |
| 9 | **Aranda (443)** | Osma (501) | `[(Osma, 501), (Soria, 583), (Logroño, 590)]` |
| 10 | **Osma (501)** | Soria (**559**), Calatayud (**641**) | `[(Soria, 559), (Logroño, 590), (Calatayud, 641)]` |
| 11 | **Soria (559)** | Calatayud (650*) | `[(Logroño, 590), (Calatayud, 641)]` |
| 12 | **Logroño (590)** | (Sin mejoras) | `[(Calatayud, 641)]` |
| 13 | **Calatayud (641)** | **LLEGADA A META** | `-` |

*\*Nota: Los costes con asterisco indican que se ha encontrado un camino más largo a un nodo ya conocido, por lo que el algoritmo descarta esa rama.*

---

## 2. Análisis del Proceso de Optimización

El algoritmo UCS garantiza la optimización mediante la reevaluación constante de la frontera:

* **Poda de Caminos Ineficientes:** En la iteración 2, se generó un camino a Benavente vía Ponferrada con coste 300. Al existir ya en la frontera un camino directo desde Ourense con coste 236, la ruta más larga fue descartada automáticamente.
* **Actualización de Nodos (Osorno y Soria):** El algoritmo "corrigió" el coste de Osorno (de 409 a 397) y de Soria (de 583 a 559) al encontrar rutas secundarias más económicas durante la exploración de Palencia y Osma respectivamente.
* **Condición de Parada:** Aunque la meta (Calatayud) entró en la frontera en la iteración 10, no se dio por finalizada la búsqueda hasta que fue el nodo con menor coste total (iteración 13), asegurando que no existieran alternativas mejores.

---

## 3. Conclusión de la Ruta

**Camino Óptimo Hallado:**
Ourense $\rightarrow$ Benavente $\rightarrow$ Valladolid $\rightarrow$ Aranda $\rightarrow$ Osma $\rightarrow$ Calatayud.

**Distancia Final:** **641 km.**

---