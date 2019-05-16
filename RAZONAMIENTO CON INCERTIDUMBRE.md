# RAZONAMIENTO BAYESIANO
Se usan para saber que es más probable, interesa más la relación entre probabilidades que los números exactos.
* El formalismos de las incertidumbres

# MODELOS DE MARKOV
Un modelo de Markov es un razonamiento probabilistico que depende del tiempo. Por ejemplo llueve hoy, llueve mañana...
Podríamos decir que es una estructura de razonamiento temporal.
Se necesita la probabilidad de transición y la probabilidad inicial: 
* X1 --> X2 --> X3 --> X4 --> ...
* P(X1), P(Xt|Xt-1)

* La suposición de Markov supone que cada estado en el tiempo t solo depende del estado anterior t-1

## MODELOS OCULTOS DE MARKOV (HMM)
No se puede conocer el valor de Xt, pero existen variables asociadas llamadas observaciones(sensores, evidencias) que si que podemos saber. Estas observaciones solo dependen del estado X y el tiempo t.
Para describir un HMM necesitamos saber:
* P(X0), P(Xt|Xt-1), P(Et|Xt)

## TAREAS DE INFERENCIA
* **Filtrado**: *"Dado que he visto al compañero con paraguas tres días, ¿qué probabilidad hay de que esté lloviendo el día 3?"*
* **Prediccion**: *"Dado que he visto al compañero con paraguas tres días, ¿qué probabilidad hay de llueva pasado mañana?"*
* **Suavizado**: *"Dado que he visto al compañero con paraguas tres días, ¿qué probabilidad hay de ayer lloviera?"*
* **Explicación más probable**: *"Dado que he visto al compañero con paraguas tres días, ¿cuál es la secuencia de tiempos más probable para esos tres días?"*

# PROCESOS DE DECISIÓN DE MARKOV
Usar probabilidades para escoger las mejores acciones.

Están definidos por:
* Conjunto de estados (incluidos el estado inicial y el estado meta).
* Acciones A(s) aplicables a un estado s con coste C(a).
* Modelo de transposicion probabilistico Pa(s'|s) = probabilidad de que la acción a aplicada en s lleve al estado s'.


