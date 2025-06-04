# Tercer Parcial - Paradigmas de Programación

## Comparación de Rendimiento entre Enfoques Recursivo e Iterativo en el Cálculo de la Serie de Fourier

PS C:\Users\Labing> & C:/Users/Labing/AppData/Local/Programs/Python/Python313/python.exe "c:/Users/Labing/Downloads/serie fourier.py"
c:\Users\Labing\Downloads\serie fourier.py:9: DeprecationWarning: `trapz` is deprecated. Use `trapezoid` instead, or one of the numerical integration functions in `scipy.integrate`.
  a0 = (2 / T) * np.trapz(f, t)
c:\Users\Labing\Downloads\serie fourier.py:15: DeprecationWarning: `trapz` is deprecated. Use `trapezoid` instead, or one of the numerical integration functions in `scipy.integrate`.
  an_valor = (2 / T) * np.trapz(f * coseno, t)
c:\Users\Labing\Downloads\serie fourier.py:16: DeprecationWarning: `trapz` is deprecated. Use `trapezoid` instead, or one of the numerical integration functions in `scipy.integrate`.
  bn_valor = (2 / T) * np.trapz(f * seno, t)
c:\Users\Labing\Downloads\serie fourier.py:22: DeprecationWarning: `trapz` is deprecated. Use `trapezoid` instead, or one of the numerical integration functions in `scipy.integrate`.
  a0 = (2 / T) * np.trapz(f, t)
c:\Users\Labing\Downloads\serie fourier.py:29: DeprecationWarning: `trapz` is deprecated. Use `trapezoid` instead, or one of the numerical integration functions in `scipy.integrate`.
  an_valor = (2 / T) * np.trapz(f * coseno, t)
c:\Users\Labing\Downloads\serie fourier.py:30: DeprecationWarning: `trapz` is deprecated. Use `trapezoid` instead, or one of the numerical integration functions in `scipy.integrate`.
  bn_valor = (2 / T) * np.trapz(f * seno, t)
Iterativo: -0.000500500500500533 [np.float64(-0.0010010010010006775), np.float64(-0.0010010010010011899), np.float64(-0.0010010010010007128), np.float64(-0.0010010010010012814), np.float64(-0.0010010010010007128), np.float64(-0.0010010010010011545), np.float64(-0.0010010010010007304), np.float64(-0.0010010010010007336), np.float64(-0.0010010010010007304), np.float64(-0.001001001001001276)] [np.float64(1.2732384954398979), np.float64(-6.295791306311322e-06), np.float64(0.42441003368844166), np.float64(-1.2591707137593513e-05), np.float64(0.2546426624499534), np.float64(-1.888787202850047e-05), np.float64(0.18188401840862836), np.float64(-2.518441053356413e-05), np.float64(0.14146161674421906), np.float64(-3.148144723687959e-05)]
Recursivo: -0.000500500500500533 [np.float64(-0.0010010010010006775), np.float64(-0.0010010010010011899), np.float64(-0.0010010010010007128), np.float64(-0.0010010010010012814), np.float64(-0.0010010010010007128), np.float64(-0.0010010010010011545), np.float64(-0.0010010010010007304), np.float64(-0.0010010010010007336), np.float64(-0.0010010010010007304), np.float64(-0.001001001001001276)] [np.float64(1.2732384954398979), np.float64(-6.295791306311322e-06), np.float64(0.42441003368844166), np.float64(-1.2591707137593513e-05), np.float64(0.2546426624499534), np.float64(-1.888787202850047e-05), np.float64(0.18188401840862836), np.float64(-2.518441053356413e-05), np.float64(0.14146161674421906), np.float64(-3.148144723687959e-05)]
PS C:\Users\Labing>
