# TEMA 2: SISTEMAS DE PRODUCCIÓN
## INTRODUCCIÓN
A partir de unos hechos y unas reglas (reglas de producción), se sacan unas instancias.
Las reglas son genéricas, los hechos son los que determinan un problema concreto. Los hechos pueden variar (**sistema no monótico**).

* **Ventajas**:
  * Permiten una representación natural del conocimiento.
  * Se agrega conocimiento añadiendo más reglas.
  * No es importante saber como resolver el problema, sino para en conocer exactamente cual es el problema.
  * Simulan comportamiento humano.

* **Desventajas**:
  * Ineficientes.
  * Dificil de representar algoritmos.
  * Puede causarse encadenamiento específico, gestión de hechos contraditorios, modificar reglas existentes...

* **Base de hechos**: son afirmaciones atómicas, son una situación de partida. Si un hecho no está en la base de datos se considera **FALSO**.

* **Reglas**: condicion1 ^ condicion2 ^ ... ^ condicionN --> accion1 ^ ... ^ accionN

## PRIORIDADES

* **Motor de inferencia**:
  * Automatiza el proceso de razonamiento. Hay mecanismos de *resolución de conflictos* entre reglas. El motor de inferencia puede ser ***por prioridad***, ***más antigua***, ***más reciente***, ***más específica***, ***más genérica***, ***random***.
  * **FUNCIONAMIENTO**:
    1. *Equiparación*: cosniste en determinar que instancias de las reglas pueden ejecutarse (**conjunto conflicto**).
    2. *Resolución de conflictos*: escoje cual es la instancia que se ejecutará en el conjunto conflicto.
    3. *Ejecución*: Realiza la acción realizada por la instancia escogida.
    3. El sistema termina cuando ya no se puede seguir o cuando hay una acción que sea parar.

  * **Proceso de equiparación**:
    * **Mundo cerrado**: lo que no está en la base de datos se considera FALSO (no hay condiciones negativas).
    * **Refracción**: No se generan instancias que se hayan ejecutado ya, es decir cada instancia (regla + hechos con los que equipara), se ejecuta solo una vez.

* **Equiparación más eficiente**:
  * *Encadenamiento hacia delante*: datos --> conclusion. Pocos datos iniciales y/o muchas posibles conclusiones (razonamiento dirigido por los datos).
  * *Encadenamiento hacia atras*: datos <-- conclusion. Muchos datos inciciales, pero solo unos pocos relevantes. Razonamiento dirigido por objetivos.

* **Resolución de conflictos**: no se permite la ejecución en paralelo de varias reglas. Si hay varias se elige una estrategia:
  * **Más nuevas**: (Profundidad) las nuevas reglas (activadas más recientemente) se ejecutan antes
  * **Más antiguas**: (Amplitud) las nuevas reglas se ejecutan después
  * **Más específicas**: se ejecutan antes de las que son igual o más específicas que ellas
  * **Más generales**: se ejecutan antes que las que son igual o menos específicas
  * **Más/Menos ejecuciones**
  * **Aleatoria**: las reglas se ejecutan en orden aleatorio
  * **Dar prioridad a unas reglas y a otras no**
