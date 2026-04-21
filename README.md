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

