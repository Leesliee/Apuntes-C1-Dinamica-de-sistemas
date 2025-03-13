# Transformada inversa de laplace: Fracciones parciales + MATLAB

## 1. Introducción
En la sesión del 19 de febrero, se profundizó en la descomposición en fracciones parciales, abordando los últimos dos casos de fracciones parciales: Raíces reales repetidas y raíces complejas conjugadas. Para cada caso, se desarrolló un ejemplo práctico con su respectiva solución paso a paso. Además, se incorporó el uso de MATLABcomo herramienta para facilitar el análisis de sistemas mediante la Transformada de Laplace y su inversa. También se aprendió a emplear la función residue, que permite descomponer automáticamente expresiones en fracciones parciales, optimizando el tiempo y reduciendo posibles errores en los cálculos manuales.

## 2. TL Inversa: Fracciones parciales
En la clase del 12 de febrero, se evidenció el caso 1: *Raíces reales y diferentes*, a continuación se presentan los dos casos restantes:
### Caso 2: raíces reales repetidas
En el denomidador de F(s) hay factores reales que se repiten; al igual que en el caso 1, la idea es determinar coeficientes que vayan con un denominador diferente y esta nueva función sea igual que F(s):

$$F(s) = \frac{P(s)}{Q(s)} = \frac{P(S)}{(s+p)^n}$$

$$F(s) = \frac{A}{(s+p)} + \frac{B}{(s+p)^2} + \dots + \frac{N}{(s+p)^n}

Se realizó el siguiente ejemplo en clase:

💡Ejemplo: Determine en la función del tiempo F(s).

$$F(s) = \frac{2s^2 + 6s + 5}{(s+2)(s+1)^2}$$
### Caso 3: Raíces complejas conjugadas.
En el último caso, es importante tener en cuenta la factorización. Para que este caso suceda, debe haber una expresión cuya solución no se pueda expresar con reales, sino, que se pasa al plano complejo. Para ello, se tiene en cuenta el discriminante de la ecuación cuadrática, donde:

$$d > 0 \to $$ Raíces reales y diferentes

$$d \geq 0 \to $$ Raíces reales e iguales

$$d < 0 \to $$ Raíces complejas conjugadas

En este caso, si el discriminante es menor que 0, se aplica este caso: 

$$F(s) = \frac{P(s)}{Q(s)} = \frac{P(S)}{(s^2 + b_1s + c_1)(s^2 + b_2s + c_2) \dots (s^2 + b_n s + c_n)}$$

$$F(s) = \frac{As + B}{(s^2 + b_1s + c_1)} + \frac{Cs + D}{(s^2 + b_2s + c_2)} + \dots + \frac{Ms + N}{(s^2 + b_n s + c_n)}$$

💡Ejemplo: Determine en la función del tiempo F(s).

$$F(s) = \frac{s^2 + 2s + 3}{(s^2+2s+2)(s^2+2s+5)}$$

## 3. Ejercicios
### 📚 Ejercicio 1
### 📚 Ejercicio 2
## 4. Aplicaciones TL en MATLAB
### 4.1. Transformada de Laplace
### 4.2. Transformada inversa de Laplace
### 4.3. Función residue
## 5. Conclusiones
El estudio de la descomposición en fracciones parciales y la Transformada de Laplace es fundamental en el análisis de sistemas dinámicos. Comprender estos métodos de manera manual también permite desarrollar un análisis más profundo sobre el comportamiento de los sistemas.

Sin embargo, en la práctica, es relevante el uso de herramientas como MATLAB, que no solo optimizan el tiempo de cálculo, sino que también permiten verificar si los resultados obtenidos manualmente son correctos. Funciones como residue y la implementación de la Transformada e Inversa de Laplace facilitan el análisis y diseño de sistemas.

Además, es crucial reconocer qué tipo de caso se está abordando en una descomposición en fracciones parciales. Para ello, el valor del discriminante de una ecuación cuadrática juega un papel clave, ya que permite identificar rápidamente si las raíces son reales distintas, repetidas o complejas conjugadas, agilizando así el procedimiento.

En conclusión, combinar el dominio del análisis manual con el uso de herramientas computacionales permite un enfoque más eficiente y preciso en la resolución de problemas en sistemas dinámicos.
## 11. Referencias
Agregue un subtítulo al final donde pueda p
