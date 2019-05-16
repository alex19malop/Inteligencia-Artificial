# BÚSQUEDA NO INFORMADA
## INTRODUCIÓN
Encontrar una secuencia de operaciones que nos conducen de un estado inicial a un estado solución.
Se resuelve formando un grafo de acciones (considerando normalmente los costes de las acciones).
Los estados son hechos y las acciones son las reglas.

### Busqueda en amplitud
Se va expandiendo todo (se observan muchos nodos, demasiados diría yo).
Características:
  * **Completa**: si existe, encuentra solución.
  * **Optima**: encuentra siempre la solución menos profunda (es decir la óptima).

### Busqueda en profundidad
Se expande cada nodo al tope hasta que encuentre una solución.
Características:
  * **No completa**: No garantiza encontrar la solucion, a no ser que tenga retroceso.
  * No encuentra la solución óptima.
  * **Eficiente**: cuando la meta está alejada del estado inicial, o hay problemas de memoria.


# BÚSQUEDA HEURÍSTICA

Cuando se tiene un conocimiento parcial sobre la situación se hace uso de heurística.

## Busqueda Greedy
Es la busqueda en profundidad, pero con heurística, por lo que no tiene retroceso.
* Seleciona el mejor nodo (de dos formas):
  * Minimizar: el numero de casillas mal colocadas.
  * Maximizar: el número de casillas bien colocadas.
* **Proopiedades**:
  * **Completitud**: no tiene porque encontrar la solución.
  * **Optimalidad**: tampoco puede garantizar ser óptimo, ya que no es completo.
  * **Eficiencia**: rapido y util en general.

## A estrella
Considera costes y heuristica: f(n) = h(n) + g(n)
La función h(n) es admisible si  h(n) <= h* (n) para todo n

* **Proopiedades**:
  * **Completitud**: Si existe solución, la encuentra.
  * **Optimalidad**: si hay una solucion optima la encuentra.
  * **Eficiencia**: A* expande el numero minimo de nodos en caminos no óptimos.
