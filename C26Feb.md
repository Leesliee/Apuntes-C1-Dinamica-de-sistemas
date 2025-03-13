# Optimización casos en fracciones parciales + Solución de ED, MATLAB

## 1. Introducción
En la sesión del 26 de febrero, se exploraron métodos más eficientes para determinar los coeficientes en la descomposición en fracciones parciales, facilitando el análisis de sistemas en los tres casos fundamentales: Raíces reales y diferentes, raíces reales e iguales yraíces complejas conjugadas.
Además, se hizo la introducción al concepto de la Transformada de la Derivada, una herramienta clave en la solución de ecuaciones diferenciales en el dominio de la frecuencia. Se aprendió a cómo aplicar este método para transformar ecuaciones diferenciales y posteriormente regresar al dominio del tiempo, utilizando la Transformada Inversa de Laplace.

Por último, se integró el uso de MATLAB como una poderosa herramienta para resolver ecuaciones diferenciales con condiciones iniciales. Exploramos tanto la solución analítica como la solución numérica mediante el método ODE45, permitiendo un análisis más completo.
 
## 2. Optimización para solucionar fracciones parciales
En la clase del 12 de febrero, se evidenció el caso 1: *Raíces reales y diferentes*, a continuación se presentan los dos casos restantes:
### Caso 1: raíces reales distintas
Se evalúan los factores, buscando que sean nulos y se pueda evaluar un coeficiente a la vez.
### Caso 2: raíces reales e iguales

### Caso 3: Raíces complejas conjugadas.
Se evalúan los factores respecto a las raíces complejas conjugadas buscando que ciertos coeficientes sean nulos para evaluar un coeficiente a la vez. Al llegar a la parte final se separa parte real con parte imaginaria con un sistema de ecuaciones para determinar esos coeficientes.
## 3. Solución de ED con Laplace
Para solucionar ecuaciones diferenciales con la Transformada de laplace, es fundamental tener en cuenta:
##### A. Conocimiento de las condiciones iniciales
Es imprescindible el conocimiento de las condiciones iniciales de la ecuación. La función evaluada en 0, y la derivada de orden (n-1) evaluada en 0.
##### B. Transformada de la derivada
Se hace uso de la transformada de la derivada, se reemplaza en las derivadas y se opera con los distintos factores de la ED que se quiere solucionar. A continuación se evidencia la transformada de la derivada:

$$
\mathcal{L} \{ \frac{df}{dt} \} = sF(s) - f(0)
$$

$$
\mathcal{L} \{ \frac{d^2 f}{dt^2} \} = s^2 F(s) - s f(0) - f'(0)
$$

$$
\mathcal{L} \{ \frac{d^n f}{dt^n} \} = s^n F(s) - s^{n-1} f(0) - s^{n-2} f'(0) - \dots - s f^{(n-2)}(0) - f^{(n-1)}(0)
$$
##### C. Linealidad
Se debe aplicar la transformada de Laplace a todos los términos, gracias al concepto de linealidad. Con ayuda de la transformada de la derivada, se aplica TL a todos los términos.
##### D. Despeje de la función de salida
Al aplicar la transformada de la derivada, se factoriza F(S) y se despeja, para hallar la función en el dominio de la frecencia compleja.
##### E. Aplicación de transformada de Laplace inversa
Cuando se determina F(S), se hace uso de la transformada de Laplace inversa para regresar al dominio del tiempo y determinar al fin la solución de la ED.
💡Ejemplo: Solucione la siguiente ED
## 4. Ejercicios
### 📚 Ejercicio 1
### 📚 Ejercicio 2
## 5. Aplicaciones solución ED en MATLAB
### 5.1. Solución analítica
## 6. Conclusiones
Los métodos vistos en esta sesión permiten una resolución mucho más eficiente de fracciones parciales en comparación con el enfoque basado en sistemas de ecuaciones. Al simplificar el cálculo de coeficientes, se pueden abordar problemas complejos de manera más directa y estructurada, además que es posible mezclar los métodos según sea más cómodo para cada individuo; no hay un orden estricto para emplear los métodos.

Asimismo, se comprendió la importancia de la Transformada de la Derivada y su papel en la solución de ecuaciones diferenciales mediante la Transformada de Laplace. Un punto clave fue reconocer por qué es indispensable contar con condiciones iniciales al resolver una ecuación diferencial en este dominio, ya que estas permiten determinar una solución única y garantizar la correcta transformación inversa al dominio del tiempo.

Finalmente, se resaltó que existen múltiples formas de analizar el comportamiento de un sistema, tanto de manera analítica como numérica. En este contexto, MATLAB se convierte en una herramienta invaluable, facilitando la comparación entre métodos y permitiendo verificar soluciones de manera rápida y precisa.

## 7. Referencias
T. De Laplace. (n.d.). MateFacil. Retrieved March 13, 2025, from https://matefacil.net/t-de-laplace/

