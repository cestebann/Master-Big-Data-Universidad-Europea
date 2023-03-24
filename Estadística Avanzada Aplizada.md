
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

# Unidad 1. Variables y Estimadores

## Probabilidad y variables estimatorias

- Espacio muestral: Al conjunto de todos los escenarios posibles de un experimento .
- Suceso elemental: Cada uno de los posibles resultados de un experimento contenido en un espacio muestral. 
- Suceso compuesto: subconjunto del espacio muestral o una agrupación de espacios muestrales. 
- Sucesos disjuntos o mutuamente excluyentes: si pasa uno el otro no puede pasar. 
- Enfoque frecuentista de la probabilidad: cree que la probabilidad de que los sucesos elementales sucedan es igual. Cree que en la tendencia a un resultado si lo repetimos una y otra vez. 
- Enfoque axiomático: cree que los sucesos elementales no son igualmente probables de ocurrir. Considera en que la suma de todas las probabilidades de los sucesos elementales debe ser igual a 1. 
- Variable aleatoria: mide una propiedad de la 
- Variables aleatorias discretas --> función de masa 
- Variables aleatorias continuas --> función de densidad  
- Modelos probabilísticos típicos: 
	- Binomial: Dos sucesos elementales: éxito/fracaso.
	- Poisson: modelar las probabilidades un tiempo determinado 
	- Exponencial 
	- Uniforme
	-  Modelo normal: sigue el teorema central del límite. 



## Teoría de muestreo y partición de datos

- Metodología para el análisis de datos: 
	- Preparación de los datos
		- Recogida
		- Limpieza de los datos (eliminar datos duplicados, errores, campos vacíos y nulos).
		- Transformación de variables categóricas en numéricas. 
	- Análisis estadístico
		- Estadística descriptiva: Aplicamos un análisis exploratorio de datos (EDA), sin preguntarnos por la población ni hacer inferenc. 
		- Análisis estadístico: se buscan modelos que se ajusten a nuestros datos
		- Aprendizaje sobre el fenómeno
		- Creamos un modelo que sea capaz de predecir el comportamiento de una variable futura. 
Teoría de muestreo 
	- Muestra vs. Población 
		- Población -objetivo: es un subconjunto del universo que engloba a toda la población que cumple las condiciones para realizar un experimento. 
		- Muestra: una parte representativa de la población. 
	- Distribución muestral 
		- Necesitamos conocer el nivel de incertidumbre de nuestros estadísticos y para ello debemos conocer la distribución muestral
	- Parámetros vs Estadístico
		- Parámetro: es una medida descriptiva de una población
		- Estadístico: es una medida descriptiva de la muestra. 
- Inferencia estadística
	- Objetivos 
		- Obtener modelo poblacional mediante sus parámetros. 
		- Medir la exactitud del modelo obtenido y sus estimadores. 
	- Métodos de inferencia
		- Clásicos
		- Computacionales
			- Monte-Carlo
			- BootStrappping
			- Estimadores bayesianos 
Estimación paramétrica 
	- Un estimador:  Es un estadístico que se deben acercar al parámetro. 
	- Formas de evaluar un estimador: 
		- Sesgo
		- Error cuadrático medio
		- Eficiencia relativa 
		- Error estándar 
- Diferencias entre estadística clásica vs. Computacional: 
	- Tamaño de las muestras
	- Distribución de los datos (homogéneos vs. No homogéneos) 
	- Manualmente tratable vs. Computacionalmente tratable
	- Algoritmos sencillos vs. Algoritmos complicados
- Modelización: 
	- El objetivo de un modelo es explicar los datos y que sea capaz de predecir, y podamos sacar conclusiones y tomar decisiones. 
	- Debemos encontrar los parámetros que mejor representen a la población.
	- Hiperparámetros: parámetros propios del modelo. 
- Partición de datos 
	- Training sets: Entrenar el modelo (70%)
	- Validation sets: Si el modelo tiene hiperparámetros, evaluaríamos y seleccionaríamos los valores óptimos de los hiperparámetros. (15%)
	- Test sets: Se usan para probar el rendimiento de nuestro modelo con datos que no se usaron para el entrenamiento (10-20%)
- Validación cruzada (k-fold validation): 
	- Se usa para determinar el error predictivo del modelo. 
	- Consiste en dividir los datos disponibles en k particiones. En la primera iteración se utilizan k-1 particiones para entrenar el modelo y la k-esíma partición se usa para probar el modelo. En la segunda iteración utilizamosuna k-sima partición diferente a la primera iteración y se repite el proceso. Iteramos k-veces, es decir, hasta que todas las particiones hayan pasado como test sets. 
	- Este es el modelo que escogemos para seleccionar los hiperparámetros del modelo. 

## Estadística Computacional e Introducción al Aprendizaje Automático 

Los problemas de ML y aprendizaje automático se dividen en dos: 
- Supervisados: para cada valor de una variable entrada tenemos otra de salida. 
	- Predicción 
	- Clasificación 
- No supervisados: no tenemos una variable respuesta asociada
- Metodos de Monte Carlo para la inferencia: siguen una aproximación paramétrica, es decir, que los datos analizados siguen una distribución con parámetros conocidos 
	- Se basan en la generación de un gran número de muestras aleatorias, por lo que requieren de gran potencia computacional. 
- Métodos bootstrapping: Siguen una aproximación no paramétrica. No se asume que los datos siguen una distribución conocida. 
- Aprendizaje bayesiano: Se usa el teorema de Bayes para actualizar la probabilidad de una hipótesis a medida que tenemos más información o evidencias . 
- Modelan la distribución de incertidumbre de los valores de los parámetros desconocidos como si fuera una probabilidad. 
	- Es excelente para: 
		- Reconocimiento de patrones
- Funciones de pérdidas
	- También llamada función de costes, es una forma de cuantificar lo bien que funciona un modelo. 
	- Si el modelo se ajusta bien a los datos, el valor de la función de coste será bajo. 
	- La función de pérdidas es la función objetivo a minimizar por el algoritmo optimizador  en el algoritmo de ML. 
		- Funciones de pérdida para regresión 
			- Error cuadrático medio  (MSE): es la media artimética de la diferencia al cuadrado del valor real de la variable respuesta y el valor predicho. Intensifica la importancia de los valores atípicos. 
				- Error Cuadrático Medio Modificado: MSE/2
			- Error medio absoluto (MAE): Es parecido al anterior pero en lugar de la diferencia al cuadrado, es la diferencia absoluta. Es difícil calcular su derivada. 
			- Error medio absoluto suavizado (Huber loss): función a trozos, introduce un nuevo hiperparámetro. La elección de este parámetro es crítico porque determinará qué valores son outliers. 
		- Funciones de pérdida para clasificación 
			- Cross-entropy: 
				- Función usada en regresión logística
				- Se usa para problemas de clasificación binarias. 
		- Hinge Loss
			-  Se usa papra algoritmos llamados Support Vector Machine
			-  Se puede usar para problemas de clasificación categóricas

## Regresión lineal univariable
-  Minimizar la función de coste
	- Para encontrar el mínimo de una función, hay que hallar la derivada de esta e igualarla a cero. Observando la fórmula de la función de coste, vemos que tiene forma de paraboloide.
	- Existen diversos métodos para minimizar la función de coste; el más común para ML es el del descenso del gradiente
- Descenso del Gradiente
	- Empezar con un valor inicial de ( 𝜃0, 𝜃1
	- Calcular el valor de las derivadas parciales de J para dichos valores y actualizar los valores ( 𝜃0, 𝜃1 ).
	- Repetir hasta que el valor de J no varíe y hayamos encontrado su
		mínimo.
	- para los problemas de regresión lineal, la función de coste siempre tendrá forma convexa, por tanto, el algoritmo del descenso del gradiente siempre va a converger al mínimo absoluto.
