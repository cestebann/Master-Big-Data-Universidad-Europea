
Elena Igualada Villodre
Ingeniera Industrial 
Doctora en Matemáticas


4 actividades diferentes (10%)
1. Cuestionario tipo test. 
3 prácticas en Python. 


5 semanas de asignatura
Examen en marzo 


# Contenidos

- Objetivos
    - Objetivos específicos
    - Resultados de aprendizaje
- Unidad 1. Variables y Estimadores
    - Teoría de probabilidad y estadística básica
    - Técnicas de descripción y modelado de datos complejos: muestreo, training, test set
    - Introducción al aprendizaje estadístico: inferencia, aprendizaje bayesiano, función de pérdida
- Unidad 2. Modelos de Regresión y regularización
    - Regresión lineal, no lineal y logística
    - Regresión con múltiples variables
    - Regularización: ridge y lasso
    - Regresión no paramétrica: spline y kernel.
Unidad 3. Análisis y modelado avanzados
    - Árboles de decisión. Modelos gráficos probabilistas.
    - Modelado de funciones de densidad de probabilidad
    - Análisis de Series temporales
    - Optimización para grandes volúmenes de datos

# Objetivos

## Objetivos específicos
- Diseñar y aplicar algoritmos de análisis basados en sistemas e infraestructuras de almacenamiento y acceso a grandes volúmenes de datos. 

## Resultados de aprendizaje

- Comparación y contraste críticos de múltiples modelos de sistemas distribuidos y sus tecnologías habilitantes asociadas.


## Unidad 1. 

### Teoría de muestreo y partición de datos

Los objetivos que se pretenden alcanzar con este recurso son los siguientes:
- Entender los conceptos básicos de teoría de muestreo.
-  Entender los objetivos del análisis estadístico clásico o tradicional y su relación con la ciencia de datos.
-  Entender las diferencias entre estadística clásica y estadística computacional.
 - Entender la relación entre el concepto de estimación paramétrica propia de la estadística y la construcción de modelo mediante el ajuste de parámetros.
- Conocer los conceptos relativos a partición de datos y cómo y para qué usarla.

#### Introducción 

¿Qué es la ciencia de datos? La transformación de datos en concoimiento con el objetivo de dar respuestas a preguntas, sacar conclusiones y aplicarlas con un objetivo concreto. 
A nivel empresarial rata de poder ayydar a tomar decisiones basadas en datos. 
Un punto importante de la ciencia de datos es la modelización de los datos, o sea la construcción de un modelo que sea capaz de explicar los datos que  nos permita extrae conclusiones. 

Para describir los datos, en estadística se consideran modelos estocásticos que tienen en cuenta la incertidumbre debido a la aleatoriedad de los datos. Los modelos probabilísticos son ejemplos de estos modelos. 

La inferencia estadística nos proporciona herramientas para la construcción de estos modelos, como la estimación paramétrica. La inferencia clásica se basa en modelos establecidos que son matemáticamente tra tables y analizables. Asume que los datos provienen de una población con una distribución probabilística que sigue un modelo conocido. 

Cuando disponemos de grandes volúmenes de datos que además no siguen un patrón/modelo conocido, tenemos que recurrir a la estadística computacional. 

#### Metodología para el análisis de datos

1. Análisis de datos. 
    1.1 Recogida de los datos. 
    1.2 Tratamiento de los datos (campos nulos, datos duplicados, registros marginales).
2. Análisis estadístico
    2.1. Análisis exploratorio de datos (Exploratory Data Analysis, EDA)
        - Vemos la distribución de las variables
    2.2 Análisis estadístico. 
        - Medidas de descriptivas y de dispersión (media, mediana, percentiles, desviación estándar.)
        - Correlaciones
    2.3. Estadística inferencial. 
        - ¿Nuestros datos se ajustan a un modelo probabilístico? 
3. Aprendizaje sobre el fenómeno. 
    3.1. Construir el modelo. 
        - No solo queremos describir/explicar el fenómeno, queremos dar una predicción de los datos que no han formado parte del entrenamiento del modelo, para anticiparnos y tomar decisiones más acertadas. 
    3.2. Validar y probar el modelo 
    3.3. Mejorar el modelo 


![](/img/estadistica_avanzada/metodologia_analisis_datos.png)


### Teoría de muestreo 

#### Muestra vs. población 

**La población objetivo** es el conjunto total de individuos u objetos (elementos) sobre los que necesitamos recopilar cierta información. 

Normalmente es inviable recopilar la información necesaria de todos los miembros de una población, bien porque la población es demasiado
grande, o bien porque hay futuros miembros que todavía no existen (futuros componentes a fabricar). Por este motivo, normalmente se selecciona una parte de ella que sea representativa de toda la población, a la que se denomina **muestra**.

#### Tipo de muestras

- **Muestra aleatoria simple (MAS):** se elige de forma aleatoria entre todos los candidatos a ser muestra. Los elementos de la muestra son independientes entre sí. 
- **Muestra aleatoria estratificada (MAE)**: se divide a la población en estratos o niveles y se toma una MAS de cada estrato. El tamaño de la MAS en cada nivel debe ser proporcional al tamaño del estrato.

#### Parámetro vs. Estadísitico

**Un parámetro** es una medida descriptiva de una población, (o de una distribución de probabilidad); es decir, nos da información sobre la población (media, la varianza, proporciones, coeficientes de correlación). 

**Un estadístico**, en cambio, es una medida descriptiva de la muestra tomada. Es una función que depende de las variables aleatorias medidas u observadas en la muestra aleatoria tomada. Aquí van a interactuar intervalos de confianza. 

**Distribución muestral**: El valor v aa depender de la muestra, por lo tanto el estadístico va a tener un intervalo de confianza asociado. para toda la población. Para poder cuantificar di cha incertidumbre,
es necesario conocer la distribución muestral del estadístico, esto es, la densidad de probabilidad que lleva asociada.
Una vez conocida la distribución muestral del estadístico, se pueden calcular intervalos de confianza o hipótesis. 


### Inferencia estadística. 

Los objetivos son generalmente dos: 

1. Obtener un modelo poblacional mediante la estimación de sus parámetros.
2. Medir qué tan exacto es el modelo obtenido con respecto a la población. 

#### Principales métodos de inferencia

- Métodos de estimación de parámetros
    - Clásicos
    - Computacionales
-Métodos de obtención de intervalos de confianza del parámetro
- Métodos de contraste de hipótesis mediante test estadísticos

### Estimación paramétrica 

#### Definición de estimador 

Un estimador es un estadístico cuyo valor debe acercarse lo más posible al parámetro
𝜃 de la población que se quiere determinar o modelizar. Lo denotaremos como T. Un estimador se determina usando una muestra aleatoria. Su valor, por tanto, depende de la muestra aleatoria seleccionada, y por lo tanto el propio estimador es una variable aleatoria, la cual lleva asociada una distribución muestral. Pa ra poder cuantificar la precisión del estimador, se necesita conocer su distribución muestral.

Abajo tenemos un ejemplo de un estimador (la media muestral)

![](/img/estadistica_avanzada/media_muestral.png)

### Diferencias entre estadística clásica y computacional

!! Completar

## Modelización 

El objetivo de la modelización de datos es crear un modelo que sirva para explicar los datos y nos ayude a hacer predicciones, extraer conclusiones y tomar decisiones.

El aprendizaje automático nos ayuda a construir estos modelos para un gran volumen de datos.

Podemos clasificar los problemas de modelización en dos grandes grupos:
- problemas de predicción, en el que conocida una variable X queremos determinar
una variable Y, 
- y problemas de clasificación, en las que, dado un elemento, queremos determinar a qué clase pertenece.

Algunos modelos tienen asociados unos parámetros propios a los que se les da el nombre general de hiperparámetros.

La validación de un modelo consiste en ver cómo se comporta el modelo con los
datos que no han sido utilizados para entrenar. 

> La modelización consiste en encontrar los parámetros del modelo poblacional. La estadística nos ayuda a determinar la incertidumbre de los parámetros del modelo.

## Partición de datos 


### Training y test data sets
Si se disponen de grandes volúmenes de datos, lo normal es partirlos en dos o incluso en tres partes y usar una parte para entrenar el modelo (70%-80%) y otra para validación/testeo.


Conjunto de datos de validación: en el caso de que el modelo tenga hiperparámetros, una vez entrenados los posibles modelos con los distintos hiperparámetros con los datos de entrenamiento, se emplearían los datos de validación para evaluarlos y posteriormente seleccionar los valores óptimos de los hiperparámetros. Para este proceso se usa en torno al 15% de los datos disponibles. El conjunto de validación está dentro del de entrenamiento y se reserva una parte para validar. 

Conjunto de datos para el test: son los datos que se usan para evaluar el rendimiento del modelo finalmente seleccionado. Se emp lean el 10 o 20% para este proceso.

### Validación cruzada (K-fold cross-validation)

Es una herramienta que se usa para determinar el error predictivo de un modelo de predicción. Consiste en
dividir los datos disponibles en K particiones. particiones. En una primera iteración, se
ajustaría el modelo usando K 1 particiones y la restante se usaría para test. En una segunda iteración, se usarían K 1 particiones para entrenamiento y la restante (distinta a la de la primera iteración) se usaría para test. Se procedería así sucesivamente hasta que cada una de las K particiones hubiera sido usada como test. Habría que hacer por tanto K ajustes del modelo.

![](/img/estadistica_avanzada/validacion_cruzada.png)

## Unidad 1. Aprendizaje estadístico

Los problemas supervisados se pueden dividr a su vez en dos grandes gruopos: 
- Problemas de predicción. Consisten en estimar el valor de una variable dependiente, también llamada variable respuesta, sabiendo el valor de las variables de las que depende (varaibles independientes). Es por tantgo un problema de modelización en el que tenmeos que construir un modelo que describa a la variable respuesta. 

- Problemas de clasificación. 


## Regresión lineal univariable

### Introducción 

## Regresión lineal multivariable y no lineal

### Regresión lineal multivariable


#### Introducción al problema e hipótesis

> Un modelo multivariable es aquel en el que la variable respuesta depende de varias variable independientes o de entrada, también llamadas variables explicativas.

#### Normalización o tipificación 

La hipótesis del modelo de regresión lineal multivariable es:

![](/img/estadistica_avanzada/lineal.png)

Aquí, h𝜃(x) representa el valor predicho para la variable respuesta y, xi son
las variables de entrada y 𝜃i son los parámetros a estimar mediante el algoritmo de ML.

Las variables representan distintas magnitudes, por lo que su rango de valores puede ser muy distinto.

![](/img/estadistica_avanzada/normalizaci%C3%B3n.png)

 Para evitar los problemas que surgen de esto, lo que se hace es normalizar los datos, que consiste en hacer una
transformación tal que los datos queden aproximadamente en el rango entre -1 y 1. Esto se puede conseguir de varias formas, siendo lo más común restar el valor medio y dividir por un estadístico que represente la dispersión de los datos, normalmente la desviación típica, pero también se usa el rango (la diferencia entre el valor máximo y el valor mínimo). 


#### El problema de la colinealidad

Una de las condiciones para que el modelo de regresión múltiple funcione correctamente es que las variables de entrada sean independientes entre sí. Matemáticamente, esto implica que una de ellas no pueda expresarse como como combinación lineal de otras. No obstante, aunque matemáticamente sean independientes, a veces existe una gran correlación entre dos variables, y este hecho puede dar lugar a problemas de colinealidad.

La colinealidad es un efecto muy indeseable, ya que puede dar lugar a un mal ajuste del modelo, a valores de los parámetros muy inestables y a que la determinación de la importancia de cada variable de entrada sobre la de salida sea muy difícil de determinar.

Una forma sencilla de determinar si existe colinealidad es calcular la matriz de correlación de las variables de entrada, y observar si el coeficiente de correlación es muy alto para algunas de ellas. Esto no resuelve en sí el problema, pero al menos ayuda a seleccionar mejor el modelo.


## Regresión no lineal de una variable 

### Introducción e hipótesis

En muchas ocasiones, al representar los datos en un diagrama de dispersión, se aprecia claramente que los datos siguen una relación no lineal. Ésta puede ser cuadrática, cúbica, logarítmica, exponencial, etc…

Los ajustes polinómicos de alto orden son una buena manera para parametrizar la línea de tendencia. 

![](/img/estadistica_avanzada/relacion_no_lineal.png)


![](/img/estadistica_avanzada/no_lineal.png)

### Formulación del problema 

La hipótesis del modelo se podría escribir como: 

![](/img/estadistica_avanzada/no_lineal_2.png)

donde cada variable xi representa cada uno de los términos no lineales de la variable x. Por tanto, a la hora de formular el problema no hay diferencia entre el problema lineal multivariable y el problema no lineal.

![](/img/estadistica_avanzada/no_lineal_3.png)


Conviene expresar el problema en forma matricial. Sea X una matriz de tamaño [m,n+1] donde cada columna es cada una de las variables explicativas/términos no lineales, y cada fila representa un experimento
o una muestra.

## Métodos de resolución 

