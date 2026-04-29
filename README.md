# Fundamentos-de-Optimizacion

[English below]

Este repositorio contiene la implementación y el análisis de algoritmos fundamentales de optimización, desarrollados a lo largo de los trabajos prácticos de la asignatura.

---

## Practico 1: Búsqueda Lineal (1D)
Se exploraron métodos para localizar el mínimo de una función en un intervalo cerrado o determinar el tamaño de paso óptimo ($\alpha$).

* **Grid Search:** Un enfoque de fuerza bruta que evalúa la función en puntos equiespaciados. Es simple pero computacionalmente costoso.
* **Golden Section Search:** Un algoritmo eficiente que reduce el intervalo de incertidumbre de forma geométrica utilizando la proporción áurea ($\phi$).
* **Conclusión:** La Sección Áurea es drásticamente más rápida que la búsqueda por rejilla, siendo ideal para optimización unidimensional de funciones unimodales.

---

## Practico 2: Métodos de Descenso Acelerado (nD)
Análisis de convergencia sobre funciones cuadráticas mal condicionadas con curvas de nivel elípticas alargadas.

* **Descenso por Gradiente:** Presenta un comportamiento lento en "zigzag" debido a la gran diferencia entre los autovalores de la matriz de la función ($\kappa=50$).
* **Heavy Ball :** Introduce inercia para acelerar en zonas llanas y mitigar los rebotes del gradiente puro.
* **Nesterov :** Una versión mejorada que utiliza un gradiente "anticipado", ofreciendo una convergencia más estable y rápida.
* **Análisis de $\beta$:** Se demostró que un momentum cercano a $0.9$ optimiza la velocidad, mientras que valores muy cercanos a $1$ (como $0.99$) pueden generar oscilaciones excesivas y retrasar la estabilidad.

---

## Practico 3: Optimización con Restricciones (Simplejo Unitario)

Se implementaron y compararon algoritmos para optimizar funciones cuadráticas sobre un simplejo unidad ($\sum x_i = 1, x_i \geq 0$).

### Algoritmos Implementados:
* **Frank-Wolfe (Conditional Gradient):** Un método que evita proyecciones costosas resolviendo un subproblema lineal en cada iteración para encontrar un vértice del conjunto admisible como dirección de descenso.
* **Gradiente Proyectado:** Utiliza un paso de gradiente estándar seguido de una proyección ortogonal sobre el simplejo unitario para garantizar la factibilidad de la solución.

### Análisis de Convergencia:
* **Comportamiento de Frank-Wolfe:** Se demostró una convergencia **sublineal**. Debido a que el punto óptimo $x^*$ se encontraba en una cara del simplejo (y no en un vértice), el algoritmo presentó un efecto de "zigzag" extremo, con una tasa de error que tiende a $1$ en las iteraciones finales.
* **Comportamiento del Gradiente Proyectado:** Mostró una convergencia **lineal** significativamente más rápida. Al poder desplazarse a través del interior del conjunto y proyectarse directamente, el ratio de error se mantuvo bajo y constante, alcanzando la precisión deseada en una fracción del tiempo.

### Conclusión:
Aunque Frank-Wolfe es computacionalmente "barato" por iteración al no requerir proyecciones, su lentitud en problemas donde el óptimo no es un vértice lo hace menos eficiente que el Gradiente Proyectado para este escenario específico.

# Fundamentals-of-Optimization

This project gathers the implementation and analysis of fundamental optimization algorithms covered during the course.

## Practico 1: Line Search (1D)
Methods were explored to locate the minimum of a function within a closed interval or to determine the optimal step size ($\alpha$).

* **Grid Search:** A brute-force approach that evaluates the function at equally spaced points. It is simple but computationally expensive.
* **Golden Section Search:** An efficient algorithm that reduces the uncertainty interval geometrically using the golden ratio ($\phi$).
* **Conclusion:** Golden Section Search is drastically faster than grid search, making it ideal for one-dimensional optimization of unimodal functions.

---

## Practico 2: Accelerated Descent Methods (nD)
Convergence analysis on poorly conditioned quadratic functions with elliptical contour lines.

* **Gradient Descent:** Exhibits slow "zigzag" behavior due to the large difference between the eigenvalues of the function's matrix ($\kappa=50$).
* **Heavy Ball :** Introduces inertia to accelerate in flat areas and mitigate the bouncing behavior of pure gradient descent.
* **Nesterov :** An improved version that uses a "look-ahead" gradient, offering more stable and faster convergence.
* **$\beta$ Analysis:** It was demonstrated that a momentum near $0.9$ optimizes speed, while values too close to $1$ (such as $0.99$) can generate excessive oscillations and delay stability.

---

## Practice 3: Constrained Optimization (Unit Simplex)

This project involved implementing and comparing algorithms for optimizing quadratic functions over a unit simplex ($\sum x_i = 1, x_i \geq 0$). 

### Implemented Algorithms:
* **Frank-Wolfe (Conditional Gradient):** An algorithm that avoids expensive projections by solving a linear subproblem in each iteration to find a vertex of the feasible set as the descent direction.
* **Projected Gradient Descent:** A method that applies a standard gradient step followed by an orthogonal projection onto the unit simplex to ensure the solution remains feasible.

### Convergence Analysis:
* **Frank-Wolfe Performance:** Simulations demonstrated **sublinear** convergence. Because the optimal point $x^*$ was located on a face of the simplex (rather than a vertex), the algorithm exhibited an extreme "zigzagging" effect, with the error ratio tending toward $1$ in the final iterations.
* **Projected Gradient Performance:** Showed significantly faster **linear** convergence. By moving through the interior of the set and projecting directly onto the boundary, the error ratio remained low and constant, reaching the desired precision in a fraction of the time.

### Conclusion:
While Frank-Wolfe is computationally "cheap" per iteration due to the lack of projection steps, its sluggishness in problems where the optimum is not a vertex makes it less efficient than Projected Gradient Descent for this specific scenario.

