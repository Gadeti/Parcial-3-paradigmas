import numpy as np
import time
import matplotlib.pyplot as plt
import pandas as pd

# Parámetros
T = 2 * np.pi
t = np.linspace(0, T, 1000)
f = np.sin(t) + 0.5 * np.sin(3 * t)  # Puedes cambiar la función

# --- IMPLEMENTACIÓN ITERATIVA ---
def fourier_iterativo(f, t, T, N):
    a0 = (2 / T) * np.trapezoid(f, t)
    an = []
    bn = []
    for n in range(1, N + 1):
        coseno = np.cos(2 * np.pi * n * t / T)
        seno = np.sin(2 * np.pi * n * t / T)
        an_valor = (2 / T) * np.trapezoid(f * coseno, t)
        bn_valor = (2 / T) * np.trapezoid(f * seno, t)
        an.append(an_valor)
        bn.append(bn_valor)
    return a0, an, bn

# --- IMPLEMENTACIÓN RECURSIVA ---
def calcular_coeficientes_recursivo(f, t, T, N, n=1, an=[], bn=[]):
    if n > N:
        return an, bn
    coseno = np.cos(2 * np.pi * n * t / T)
    seno = np.sin(2 * np.pi * n * t / T)
    an_valor = (2 / T) * np.trapezoid(f * coseno, t)
    bn_valor = (2 / T) * np.trapezoid(f * seno, t)
    an.append(an_valor)
    bn.append(bn_valor)
    return calcular_coeficientes_recursivo(f, t, T, N, n + 1, an, bn)

def fourier_recursivo(f, t, T, N):
    a0 = (2 / T) * np.trapezoid(f, t)
    an, bn = calcular_coeficientes_recursivo(f, t, T, N)
    return a0, an, bn

# --- COMPARACIÓN DE TIEMPOS ---
Ns = [5, 10, 20, 50]
tiempos_iterativo = []
tiempos_recursivo = []

for N in Ns:
    inicio_i = time.time()
    a0_i, an_i, bn_i = fourier_iterativo(f, t, T, N)
    fin_i = time.time()
    tiempos_iterativo.append(fin_i - inicio_i)

    inicio_r = time.time()
    a0_r, an_r, bn_r = fourier_recursivo(f, t, T, N)
    fin_r = time.time()
    tiempos_recursivo.append(fin_r - inicio_r)

# --- GRÁFICA DE TIEMPOS ---
plt.figure(figsize=(10, 6))
plt.plot(Ns, tiempos_iterativo, label='Iterativo', marker='o')
plt.plot(Ns, tiempos_recursivo, label='Recursivo', marker='s')
plt.xlabel("N (número de términos)")
plt.ylabel("Tiempo de ejecución (segundos)")
plt.title("Comparación de tiempos: Fourier Iterativo vs Recursivo")
plt.legend()
plt.grid(True)
plt.tight_layout()
plt.show()

# --- TABLA DE COMPARACIÓN ---
df = pd.DataFrame({
    "N": Ns,
    "Iterativo (s)": tiempos_iterativo,
    "Recursivo (s)": tiempos_recursivo,
    "Diferencia (s)": [r - i for r, i in zip(tiempos_recursivo, tiempos_iterativo)]
})
print(df)
