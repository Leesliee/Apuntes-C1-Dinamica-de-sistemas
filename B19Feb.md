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

$$F(s) = \frac{2s^2 + 6s + 5}{(s+2)(s+1)^2} = \frac{A}{(s+2)}+\frac{B}{(s+1)}+\frac{C}{(s+1)^2}$$

$$\frac{(s+2)(s+1)^2(2s^2 + 6s + 5)}{(s+2)(s+1)^2} = \frac{(s+2)(s+1)^2A}{(s+2)}+\frac{(s+2)(s+1)^2B}{(s+1)}+\frac{(s+2)(s+1)^2C}{(s+1)^2}$$

$$2s^2 + 6s + 5= (s+1)^2A + (s+2)(s+1)B +(s+2)C$$

Al evaluar s = -2:

$$ 2(-2)^2 + 6(-2) + 5= ((-2)+1)^2A + ((-2)+2)((-2)+1)B +((-2)+2)C $$
$$ 1 = (1)A + (0)B +(0)C $$
$$ A =  \frac{1}{1} $$
$$ A = 1 $$

Al evaluar s = -1:

$$ 2(-1)^2 + 6(-1) + 5= ((-1)+1)^2A + ((-1)+2)((-1)+1)B +((-1)+2)C $$
$$ 1 = (0)A + (0)B +(1)C $$
$$ C =  \frac{1}{1} $$
$$ C = 1 $$

Sabiendo que A = 1 y C = 1, si s=0:

$$ 2(0)^2 + 6(0) + 5= ((0)+1)^2(1) + ((0)+2)(0+1)(1) +((0)+2)C $$
$$ 5 = 1 + 2 + 2C $$
$$ C =  \frac{5-2-1}{2} $$
$$ C = 1 $$

Se reemplaza:

$$F(s) =\frac{1}{(s+2)}+\frac{1}{(s+1)}+\frac{1}{(s+1)^2}$$

$$\mathcal{L}^{-1} \{ F(s) \} = \mathcal{L}^{-1} \left( \frac{1}{s + 2} \right) + \mathcal{L}^{-1} \left( \frac{1}{s +1} \right) + \mathcal{L}^{-1} \left( \frac{1}{(s+1)^2} \right)$$

Y por último se encuentra la solución en el dominio del tiempo: 

$$f(t) = e^{-2t} + e^{-t} + te^{-t}$$

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
Determinar la función en el dominio del tiempo de F(s):

### 📚 Ejercicio 2
## 4. Aplicaciones TL en MATLAB
En MATLAB se puede automatizar el proceso analítico de muchas funciones, por ejemplo la transformada de Laplace, a continuación se evidencia de manera breve la manera de usar matlab y la función a emplear.
### 4.1. Transformada de Laplace
Para obtener la transformada de Laplace en función de la frecuencia compleja se puede usar de guía el siguiente fragmento de código:
```
syms t s            %Función para declarar variables simbólicas
y = *funcion dom t*
Y = laplace(y)      %Función para obtener la TL de la función y
Y = *función en el dominio s*
}
```
### 4.2. Transformada inversa de Laplace
Para obtener la función nuevamente en el dominio del tiempo viniendo de la frecuencia compleja se puede usar como guía el siguiente fragmento:
```
syms t s           %Función para declarar variables simbólicas
Y = *funcion dom S*
y = ilaplace(y)     %Función para obtener la TL inversa de la función y
y = *función en el dominio t*
}
```
### 4.3. Función residue
Para obtener las fracciones parciales en MATLAB, se usa la función residue; cuando se conocen los valores del numerador y del denominador. Se puede ver en el siguiente código:
```
numerador = [*numeradores*]                %Función para declarar variables simbólicas
denominador = conv(funcion)[coeficientes den 1],[coeficientes den 2]   %Conv: función que retorna valores de un vector 
[r,p,k]=residue(numerador, denominador)     %Se emplea la función residue
```
## 5. Conclusiones
El estudio de la descomposición en fracciones parciales y la Transformada de Laplace es fundamental en el análisis de sistemas dinámicos. Comprender estos métodos de manera manual también permite desarrollar un análisis más profundo sobre el comportamiento de los sistemas.

Sin embargo, en la práctica, es relevante el uso de herramientas como MATLAB, que no solo optimizan el tiempo de cálculo, sino que también permiten verificar si los resultados obtenidos manualmente son correctos. Funciones como residue y la implementación de la Transformada e Inversa de Laplace facilitan el análisis y diseño de sistemas.

Además, es crucial reconocer qué tipo de caso se está abordando en una descomposición en fracciones parciales. Para ello, el valor del discriminante de una ecuación cuadrática juega un papel clave, ya que permite identificar rápidamente si las raíces son reales distintas, repetidas o complejas conjugadas, agilizando así el procedimiento.

En conclusión, combinar el dominio del análisis manual con el uso de herramientas computacionales permite un enfoque más eficiente y preciso en la resolución de problemas en sistemas dinámicos.
## 6. Referencias
(N.d.-c). Retrieved March 13, 2025, from http://chrome-extension://efaidnbmnnnibpcajpcglclefindmkaj/http://canek.uam.mx/Ecuaciones/Teoria/6.Laplace/ImpSolucionEdos.pdf

Jorge Eduardo Cote Ballesteros. (2024). Transformada de Laplace, dinámica de sistemas. ETITC

T. De Laplace. (n.d.). MateFacil. Retrieved March 11, 2025, from https://matefacil.net/t-de-laplace/
