# Los tres casos de fracciones parciales, en uno

## 1. Introducción
En la sesión del 05 de marzo, se trabajó en la transformación de funciones del dominio de la frecuencia compleja al dominio del tiempo, utilizando la Transformada Inversa de Laplace. Para ello, se aplicó el método de fracciones parciales, abarcando los tres casos fundamentales: raíces reales y diferentes, raíces reales e iguales, raíces complejas conjugadas.
A partir de la descomposición en fracciones parciales, se obtuvo una expresión para F(S)
F(s) que facilitó la aplicación de la Transformada Inversa de Laplace, permitiendo encontrar la función en el dominio del tiempo. Se hizo uso de métodos resumidos y combinación de los mismos para hacer el proceso más eficiente
## 2. Ejercicio con los 3 casos de fracciones parciales
💡Ejemplo: Determine la transformada inversa de la función:

$$F(s) = \frac{2s - 3}{(s+2)(s-2)(s^2 + 6s + 10)(s^2 + 8s + 17)}$$

$$F(s) = \frac{A}{s+2} + \frac{B}{s-2} + \frac{Cs + D}{s^2 + 6s + 10} + \frac{Es + F}{s^2 + 8s + 17}$$

$$2s - 3 = A(s-2)(s^2 + 6s + 10)(s^2 + 8s + 17) + B(s+2)(s^2 + 6s + 10)(s^2 + 8s + 17)+ (Cs+D)(s+2)(s-2)(s^2 + 8s + 17) + (Es+F)(s+2)(s-2)(s^2 + 6s + 10)$$

Sistema de ecuaciones resultante al igualar coeficientes:

$$\begin{cases}
    A + B = 2 \\
    6A + 6B + C + E = 0 \\
    10A + 10B + 6C + 8E = 0 \\
    D + F = -3
\end{cases}$$

$$\mathcal{L}^{-1} \{ F(s) \} = \mathcal{L}^{-1} \left( \frac{A}{s+2} \right) + \mathcal{L}^{-1} \left( \frac{B}{s-2} \right)+ \mathcal{L}^{-1} \left( \frac{Cs+D}{s^2 + 6s + 10} \right) + \mathcal{L}^{-1} \left( \frac{Es+F}{s^2 + 8s + 17} \right) $$

$$
f(t) = A e^{-2t} + B e^{2t} + e^{-3t} \left( C \cos t + D \sin t \right) + e^{-4t} \left( E \cos t + F \sin t \right)
$$

## 3. Ejercicios
### 📚 Ejercicio 1
Determinar la función en el dominio del tiempo de F(s):

$$F(s) = \frac{s^2 + 2s + 8}{(s^4+4s^2)}$$

$$F(s) = \frac{s^2 + 2s + 8}{(s^2)(s^2+4)} = \frac{A}{(s)}+\frac{B}{(s^2)}+\frac{Cs+D}{(s^2+4)}$$

$$\frac{(s^2)(s^2+4)(s^2 + 2s + 8)}{(s^2)(s^2+4)} = \frac{(s^2)(s^2+4)A}{(s)}+\frac{(s^2)(s^2+4)B}{(s^2)}+\frac{Cs+D}{(s^2+4)}$$

$$s^2 + 2s + 8= (s)(s^2+4)A + (s^2+4)B +(s^2)(Cs+D)$$

Al evaluar s = 0:

$$(0)^2 + 2(0) + 8= (0)((0)^2+4)A + ((0)^2+4)B +((0)^2)(Cs+D)$$
$$ 8 = (0)A + (4)B +(0)C $$
$$ B =  \frac{8}{4} $$
$$ B = 2 $$

Al evaluar s = 2i:

$$(2i)^2 + 2(2i) + 8= (2i)((2i)^2+4)A + ((2i)^2+4)B +((2i)^3)C+((2i)^2)D$$
$$ 4+4i = (0)A + (0)B - 4D - 8iC $$

Parte real con parte real y parte imaginaria con parte imaginaria:

$$\[
\begin{cases}
  -8C = 4 \\
  -4D = 4
\end{cases}
\]$$

$$ C = \frac{-1}{2}$$
$$ D = -1 $$

Sabiendo los valores de B, C y D; al evaluar s=1:

$$(1)^2 + 2(1) + 8= (1)((1)^2+4)A + ((1)^2+4)(2) +((1)^2)(-1/2-1)$$
$$ 11 = (5)A + 10 -\frac{3}{2} $$
$$ A =  \frac{11-10+\frac{3}{2}}{5} $$
$$ A = \frac{1}{2} $$

Se reemplaza:

$$F(s) =\frac{1/2}{(s)}+\frac{2}{(s^2)}+\frac{-1/2s-1}{(s^2+4)^2}$$

$$\mathcal{L}^{-1} \{ F(s) \} = \mathcal{L}^{-1} \left( \frac{1/2}{(s)} \right) + \mathcal{L}^{-1} \left( frac{2}{(s^2)} \right) + \mathcal{L}^{-1} \left( \frac{-1/2s-1}{(s^2+4)} \right)$$

$$\mathcal{L}^{-1} \{ F(s) \} = \frac{1}{2}\mathcal{L}^{-1} \left( \frac{1}{(s)} \right) + 2*\mathcal{L}^{-1} \left( \frac{1}{(s^2)} \right) - \frac{1}{2}\mathcal{L}^{-1} \left( \frac{s}{(s^2+4)^2} \right)-\mathcal{L}^{-1} \left( \frac{1}{(s^2+4)} \right)$$

$$\mathcal{L}^{-1} \{ F(s) \} = 1 + 2t -\frac{1}{2}*cos(2t)-\frac{1}{2}*sen(2t)$$

Y por último se encuentra la solución en el dominio del tiempo: 

$$f(t) =  1 + 2t -\frac{1}{2}*cos(2t)-\frac{1}{2}*sen(2t)$$
### 📚 Ejercicio 2
## 4. Conclusiones
En esta sesión, se evidenció que resolver un ejercicio extenso que involucre uno o varios casos de fracciones parciales mediante un sistema de ecuaciones no es un método eficaz, ya que el proceso se vuelve largo y propenso a errores. En su lugar, es fundamental emplear métodos resumidos que permitan encontrar los coeficientes de manera más directa y eficiente.

Además, se resaltó la importancia de combinar diferentes estrategias según el tipo de raíces presentes en el denominador, lo que permite optimizar el procedimiento y obtener resultados de forma más rápida y precisa.
## 5. Referencias
T. De Laplace. (n.d.). MateFacil. Retrieved March 11, 2025, from https://matefacil.net/t-de-laplace/

Jorge Eduardo Cote Ballesteros (2024). Soluciones de ecuaciones diferenciales; dinámica de sistemas. ETITC




