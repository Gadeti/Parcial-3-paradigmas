# Tercer Parcial - Paradigmas de Programación

## Comparación de Rendimiento entre Enfoques Recursivo e Iterativo en el Cálculo de la Serie de Fourier

### Contexto
La **Serie de Fourier** permite representar funciones periódicas como combinaciones de senos y cosenos. En programación científica, los métodos para calcular estos coeficientes pueden implementarse usando **enfoques iterativos o recursivos**, cada uno con ventajas y desventajas en términos de claridad, eficiencia y consumo de memoria.

### Problema
Comparar el rendimiento computacional de dos enfoques para calcular los coeficientes de la Serie de Fourier de una función periódica evaluada numéricamente:

- **Enfoque Iterativo**: Calcula los coeficientes en un bucle `for`.
- **Enfoque Recursivo**: Calcula los coeficientes haciendo llamadas recursivas hasta alcanzar el armónico base.

### Actividades a Realizar

1. Definir una función periódica `f(t)` evaluada sobre un conjunto de `M` puntos uniformemente espaciados en el intervalo `[0, T)`.
2. Implementar dos funciones:
   - `calcular_serie_fourier_iterativa(f, t, T, N)`: Calcula los coeficientes de la Serie de Fourier usando un bucle `for`.
   - `calcular_serie_fourier_recursiva(f, t, T, N)`: Calcula los coeficientes de forma recursiva, con una función auxiliar que se llama a sí misma.
3. Calcular los coeficientes `a₀`, `aₙ`, `bₙ` para `n = 1...N` usando **integración numérica** (por ejemplo, la regla del trapecio):

   

### Cálculo de los coeficientes de la Serie de Fourier

Los coeficientes de la Serie de Fourier se calculan mediante **integración numérica**, siguiendo estas ecuaciones:



\[
a_n = \frac{2}{T} \int_0^T f(t) \cos\left(\frac{2\pi n t}{T}\right) dt
\]





\[
b_n = \frac{2}{T} \int_0^T f(t) \sin\left(\frac{2\pi n t}{T}\right) dt
\]

4. Comparar el rendimiento de ambas funciones usando:
   - **Tiempo de ejecución** (`time` o `timeit`).
   - **Consumo de memoria** (opcional, usando `memory_profiler`).
   - Graficar o tabular los resultados de **tiempo vs. número de armónicos N** para ambos métodos.

### Ejemplo de Uso

```python
import numpy as np

T = 2 * np.pi
t = np.linspace(0, T, 1000, endpoint=False)
f = np.sign(np.sin(t))  # Onda cuadrada

# Comparación
coef_iter = calcular_serie_fourier_iterativa(f, t, T, 10)
coef_recur = calcular_serie_fourier_recursiva(f, t, T, 10)

