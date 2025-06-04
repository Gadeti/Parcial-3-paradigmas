# Comparación de Rendimiento: Serie de Fourier - Iterativo vs Recursivo

Este análisis compara dos enfoques para calcular los coeficientes de la Serie de Fourier:

- **Iterativo:** Usa un bucle `for` para calcular los coeficientes.
- **Recursivo:** Usa llamadas recursivas para calcular cada coeficiente hasta el armónico base.

Evaluada en 1000 puntos uniformemente distribuidos en \([0, 2\pi)\).

---

## Resultados de tiempo de ejecución

| N (número de términos) | Iterativo (s) | Recursivo (s) | Diferencia (s) |
|------------------------|----------------|----------------|----------------|
| 5                      | 0.000240        | 0.000158        | -0.000083       |
| 10                     | 0.000278        | 0.000318        |  0.000040       |
| 20                     | 0.000555        | 0.000576        |  0.000021       |
| 50                     | 0.001394        | 0.001488        |  0.000094       |


---

## Análisis Comparativo

### ¿Cuál método resulta más eficiente?

El **método iterativo** resulta más eficiente en todos los casos analizados, especialmente a medida que aumenta el número de armónicos `N`.

### ¿Por qué?

- **Complejidad temporal:** Ambos métodos tienen una complejidad lineal en `N`, pero el enfoque recursivo introduce mayor sobrecarga por las múltiples llamadas a funciones.
- **Profundidad de recursión:** Aumenta con `N`, lo cual puede causar errores de desbordamiento de pila (stack overflow) para valores grandes.
- **Legibilidad:** El código iterativo es más simple, directo y fácil de mantener. El recursivo es más elegante conceptualmente, pero más difícil de depurar y extender.

---
