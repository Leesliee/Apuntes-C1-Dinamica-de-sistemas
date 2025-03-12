# Conceptos preliminares e introducción a TL inversa

## 1. Introducción
En esta clase, se exploraron los fundamentos de los sistemas dinámicos, comenzando por la definición de un sistema y su clasificación. Se analizó qué es un sistema dinámico y cómo su comportamiento cambia en función del tiempo (la base de la asignatura). También se discutieron los conceptos de planta y proceso, fundamentales en el análisis y control de sistemas.

Además, se abordaron las características de las ecuaciones diferenciales, que son esenciales para el modelamiento sistemas físicos, y se diferenciaron entre sistemas lineales y no lineales. Finalmente, se observó la importancia de la transformada de Laplace y su inversa, una herramienta clave para resolver ecuaciones diferenciales y comprender la respuesta temporal de los sistemas.

## 2. Conceptos base
A continuación, se evidencian los principios fundamentales a tener en cuenta durante el transcurso de la materia.

### 2.1. Sistema
>🔑 *Sistema:* Un sistema es una combinación de componentes que interactúan entre sí con el propósito de alcanzar un objetivo específico. Esta interacción puede representarse mediante reglas o relaciones matemáticas que establecen cómo las entradas del sistema afectan sus salidas.

![Figura 1](Imagenes/sistema.png)

Figura 1. Sistema

A partir de modelos matemáticos, se representa lo que ocurre en la variable de salida si se modifica la entrada del sistema. En la Figura 1 se representa de manera básica un sistema.
### 2.2. Sistema dinámico
>🔑 *Sistema dinámico:* Se le llama sistema dinámico al sistema donde la salida en el presente depende de una entrada del pasado.

A diferencia de un sistema estático, donde la salida solo depende de la entrada en curso. La dinámica de un sistema se basa en variables que varían respecto al tiempo. En pocas palabras, es un sistema que cambia a través del tiempo. 
### 2.3. Planta
>🔑 *Planta:* Es la parte física del sistema que se quiere controlar.

Usualmente es confundida con el sistema, sin embargo solo se considera la parte física del mismo; la planta puede ser reprensentada matemáticamente, a través de uno o varios sistemas.
### 2.4. Proceso
>🔑 *Proceso:* Secuencia de pasos o instrucciones para lograr un objetivo.
>
El proceso es como la "receta" de lo que se hará; aunque en control se usa frecuentemente para referirse a la _planta_, no son lo mismo. El proceso está más ligado al concepto de algoritmo que de planta.
### 2.5. Modelo dinámico
>🔑 *Modelo dinámico:* Un modelo dinámico es una expresión matemática que predecirá el comportamiento de un sistema dinámico y/o variable a lo largo del tiempo.

Básicamente un modelo dinámico busca obtener una expresión matemática, en el caso de control, que relacione una variable de interés respecto al tiempo. Como se sabe, la derivada calcula una **variación**; en este caso de una variable respecto al tiempo:

$$\frac {df(t)}{dt}$$

Tdo esto a partir del concepto de derivada, que se basa en la pendiente y el cambio de la misma de determinada función.
## 3. ED en sistemas dinámicos
Las ecuaciones diferenciales son fundamentales para modelar sistemas porque describen cómo cambian las variables en función del tiempo u otra magnitud, permitiendo representar matemáticamente fenómenos dinámicos como el movimiento, la transferencia de calor, el crecimiento poblacional o el comportamiento de circuitos eléctricos.
### 3.1. ¿Cómo luce un modelo de ED?
Al modelar sistemas, como se dijo anteriormente hay una entrada y una salida. Al modelarlo en una ED lo que varía son las constantes y las derivadas de orden n que se encuentren presentes en la ED, tanto la entrada como la salida del sistema no son números, son funciones:

$$ u(t) = a_1 \frac{d^2F}{dt^2} + a_2 \frac{dF}{dt} + a_3 F$$

Donde: a = Constantes del sistema; u = Entrada del sistema; F= Salida del sistema
### 3.2. Características de una ED
Hay diferentes tipos de ED basadas en la linealidad y variabilidad en el tiempo. La linealidad de una ecuación diferencial se refiere a que es lineal en la función incógnita y sus derivadas y la variabilidad en el tiempo se basa al cómo varía el modelo cuando transcurre el tiempo.
## 4. Clasificación de sistemas
### 4.1. Sistema lineal
>🔑 *Sistema lineal:* Se considera sistema lineal cuando satisface el principio de superposición (la respuesta a múltiples excitaciones simultáneas es igual a la suma de las respuestas individuales a cada excitación aplicada por separado) y satisface el principio de proporcionalidad (la relación entre la entrada y la salida es constante.

### 4.2. Sistema no lineal
>🔑 *Sistema no lineal:* Se considera sistema no lineal cuando no satisface el principio de superposición y tampoco satisface el principio de proporcionalidad. Su análisis es más complejo; es posible linealizarlos entorno a un punto de operación, lo que permite aplicar métodos de análisis en cierta región del sistema.
## 5. Modelamiento y validación
Al desarrollar un modelo matemático de un sistema a partir de leyes físicas, es importante considerar que siempre existirá un cierto grado de incertidumbre en los resultados obtenidos, debido a simplificaciones, suposiciones y posibles errores en los datos.

Para garantizar que el modelo obtenido represente con precisión el comportamiento del sistema real, es fundamental realizar un proceso de validación. Esto implica **comparar** la salida del modelo con la del sistema físico y evaluar si la diferencia es aceptable. En caso contrario, el modelo debe ajustarse iterativamente hasta que el error se reduzca a un nivel adecuado.

Además, la validación no solo permite mejorar la precisión del modelo, sino que también ayuda a identificar posibles limitaciones o factores no considerados.
## 6. Influencia de parámetros
Según los parámetros, hay diferentes comportamientos de un sistema:
### 6.1. Comportamiento sinusoidal
Un modelo se comporta sinusoidalmente cuando hay inexistencia de parámetros.

💡Ejemplo: Un péndulo ideal oscilando sin ningún tipo de fricción o resistencia al aire; se representaría mediante una amplitud y oscilación constante.
### 6.2. Comportamiento de decaimiento exponencial
Un modelo se comporta decayendo exponencialmente cuando existe el parámetro de disipación de energía. 

💡Ejemplo: Circuito eléctrico RC, donde la carga del capacitor disminuye con el tiempo de forma exponencial debido a la disipación de energía en la resistencia.
### 6.3. Combinados
Un modelo se comporta de forma combinada cuando el sistema tiene oscilaciones "amortiguadas", cuando el sistema tiene una resistencia o fricción que no es lo suficientemente grande como para detener las oscilaciones de inmediato, pero sí las reduce con el tiempo. 

💡Ejemplo: un péndulo oscilando en aceite. Su movimiento es inicialmente oscilatorio (sinusoidal), pero la fricción con el fluido provoca que la amplitud de las oscilaciones disminuya exponencialmente hasta detenerse.
## 7. Transformada de Laplace
>*Transformada de Laplace:* Es una transformada que convierte una función de una variable real en el dominio del tiempo a una función de variable compleja en el dominio de la frecuencia (s). 

Básicamente es una herramienta matemática utilizada para resolver ecuaciones diferenciales con condiciones iniciales. Es ampliamente aplicada en el análisis de sistemas dinámicos y circuitos eléctricos, ya que permite transformar ecuaciones diferenciales en ecuaciones algebraicas más sencillas de manejar. La transformada muestra componentes sinusoidales y exponenciales de la señal. Mediante la definición, es una integral impropia que va desde 0 hasta infinito como se evidencia en la siguiente ecuación:

$$ f(t) \to F(S) $$
$$ \mathcal{L}\{f(t)\} = F(s) = \int_0^{\infty} f(t) e^{-st} \, dt $

En la figura 2, se observa una representación un poco más gráfica:

![Figura 2](Imagenes/TL.png)

Figura 2, TL


## 4. Ejemplos
Si en algún caso pretende dar un ejemplo explicativo ya sea a través de texto o através de ecuaciones matemáticos, utilizar la palabra 'Ejemplo' seguido de una numeración consecutiva dentro de la clase. Utilice el emoji 💡 antecediendo la palabra.

## 5. Ecuaciones
Para la edición de ecuaciones debe utilizar la etiqueta '$$' al comienzo y final de la ecuación para que la ecuación quede centrada ocupando una línea. Si se quiere que la ecuación quede integrada en el texto debe utilizar la etiqueta '$' al comienzo y final de la ecuación. Las ecuaciones pueden ser editadas utilizando el código LATEX, en el siguiente enlace encuentran un editor de ecuaciones que les genera el código. http://www.alciro.org/tools/matematicas/editor-ecuaciones.jsp . Sin embargo hay muchas otras herramientas que pueden utilizar para esto.

💡**Ejemplo 1:** si se va a representar la ecuación de la ley de Ohm se puede mostrar así $R=\frac{V}{I}$ o también,

$$R=\frac{V}{I}$$

## 6. Figuras
Todas las figuras que incluya deben ser generadas por ustedes, **no utilizar las figuras de las presentaciones**. Para incluir figuras puede seguir los siguientes pasos:
* Primero escribimos ![]().
* Después escribimos, dentro de los corchetes, el texto alternativo. Este es opcional y solo entra en acción cuando no se puede cargar la imagen correctamente.
* Después escribimos, dentro de los paréntesis, la ubicación del archivo (ya sea una url o una ubicación dentro de algun folder local). Se recomienda poner las imágenes en una carpeta que se llame imágenes dentro del repositorio github para que no tengan problemas al cargar las imágenes.

💡**Ejemplo 2:**

![Figura de prueba](images/plantilla/Captura2.PNG)

Figura 1. Figura de prueba

Incluya la respectiva etiqueta a modo de descripción de la figura y mantenga numeración consecutiva para todas las figuras de la clase.

## 7. Tablas
En caso de necesitar la inclusión de tablas para organizar información se recomienda el uso de la herramienta del siguiente enlace https://www.tablesgenerator.com/markdown_tables , la cual permite organizar la información dentro de la tabla y genera el código markdown automáticamente:

💡**Ejemplo 3:** 

| **Resultado** | **x = número de intentos hasta primer éxito** |
|---------------|-----------------------------------------------|
|       S       |                       1                       |
|       FS      |                       2                       |
|      FFS      |                       3                       |
|      ...      |                      ...                      |
|    FFFFFFS    |                       7                       |
|      ...      |                      ...                      |

Tabla 1. Tabla de ejemplo

Cada tabla debe llevar la etiqueta que describa su contenido y numeración consecutiva para todas las tablas

## 8. Código
Teniendo en cuenta que el curso requiere del desarrollo de código matlab, c, c++ u otro. Si requiere incluir pequeños segmentos de código en los apuntes hágalos de la siguiente manera:

💡**Ejemplo 4:**
```
var sumar2 = function(numero) {
  return numero + 2;
}
```

## 9. Ejercicios
Deben agregar 2 ejercicios con su respectiva solución, referentes a los temas tratados en cada una de las clases. Para agregar estos, utilice la etiqueta #, es decir como un nuevo título dentro de la clase con la palabra 'Ejercicios'. Cada uno de los ejercicios debe estar numerado y con su respectiva solución inmediatamente despues del enunciado. Antes del subtitulo de cada ejercicio incluya el emoji 📚

## 10. Conclusiones
Agregue unas breves conclusiones sobre los temas trabajados en cada clase, puede ser a modo de resumen de lo trabajado o a indicando lo aprendido en cada clase

## 11. Referencias
Agregue un subtítulo al final donde pueda poner todas las referencias consultadas incluyendo el origen o fuente de los ejercicios planteados. Tambien dentro del texto referencie los textos o artículos consultados y las figuras y tablas dentro de la explicación de las mismas.
