# Estadística Avanzada Aplicada

Elena Igualada Villodre
    - Ingeniera Industrial 
    - Doctora en Matemáticas


4 actividades diferentes (10%)
    - 1. Cuestionario tipo test. 
    - 3. Prácticas en Python. 


5 semanas de asignatura
Examen en marzo 


# Contenido del Curso

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

# 2. Modelos de Regresión y regularización 

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
    - A veces se usa el término función de pérdida para referirse a un solo experim ent o, mientras que se deja el término función de coste para referirse al conjunto de datos. Esto es, la función de coste sería el sumatorio de las funciones de pérdidas de cada uno de los datos.
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

## Regresión multivariable y no lineal

- Un modelo multivariable es aquel en el que la variable respuesta depende de varias variable independientes o de entrada, también llamadas variables explicativas.
- Las variables representan distintas magnitudes, por lo que su rango de
valores puede ser muy distinto.
- colinealidad 
    - Una de las condiciones para que el modelo de regresión múltiple funcione correctamente es que las variables de entrada sean independientes entre sí. Cuando existe una gran correlación entre dos variables,  este hecho puede dar lugar a problemas de colinealidad.
- Regresión no lineal: A la hora de formular el problema
no hay diferencia entre el problema lineal multivariable y el problema
no lineal, ya que aplicaremos una función a las variables no lineales para transformarlas en variables lineales. 
- Coeficiente de determinación 
    - Es un estadístico que nos da una medida de la bondad del modelo ajustado por regresión. Se define como el ratio entre la variabilidad explicada por el modelo y la variabilidad total, y se denota por R2.
    - Se pueden comparar distintos modelos entre sí mediante el coeficiente de determinación de cada modelo. 
    - Cuanto mayor sea el valor de R2 mayor es la capacidad explicativa del modelo. Por tanto.

## Regresión logística
- 
- Se pueden construir modelos de clasificación binaria usando el modelo de regresión logística.
- El problema de clasificación puede verse así como un problema de predicción en el que hay que predecir la etiqueta de la variable de salida.
- Superficie de decisión: es una división del espacio, en donde cada región del espacio pertenece a una clase. 
- Métodos de optimización 
    - Máxima verosimilitud 
    - Descenso de gradiente
    - Optimización avanzada

## Regularización y selección del modelo

- El error de predicción puede descomponerse como la suma de la varianza del modelo poblacional, más el sesgo al cuadrado del modelo estimado más la varianza del modelo estimado. 
- Para que el error de predicción sea pequeño, debemos conseguir que tanto el
sesgo como la varianza del modelo sean pequeños.
- El sesgo es una medida de la diferencia entre el valor esperado de un parámetro y su valor real. Un modelo con un sesgo elevado predecirá valores muy alejados de los reales.
- La varianza nos da idea de la dispersión de nuestros datos con respecto a la media. 
- Equilibrio entre sesgo y varianza
    - Cuando un modelo produce un ajuste insuficiente de los datos, se dice que tiene un sesgo elevado y una varianza baja.
    - un modelo que está sobreajustado tiene una varianza muy alta y un sesgo normalmente bajo.
- Regularización: El método de regularización consiste en construir un modelo lineal complejo, que a priori tenga en cuenta todas las variables de entrada pero
penalizando los valores altos de los coeficientes, forzando a que varios de ellos tengan valores próximos a cero o incluso iguales a cero. 
    - Esta técnica provoca un pequeño aumento en el sesgo pero, a cambio, consigue una notable reducción en la varianza. 
    - Hay varios tipos de regularización. Algunas de las más usadas son la regularización Ridge, la Lasso y elastic net. 
    - Regularización Ridge: Es una de las formas de regularización más sencillas. Consiste en añadir un término de penalización a la función de coste, que es igual al cuadrado de la suma de los coeficientes.
    - Regularización Lasso: Este método de regularización es muy parecido al anterior, con la salvedad de que el término de penalización que se añade a la función de coste es la suma de los valores absolutos de los coeficientes del modelo.

# Análisis y modelos avanzados

## Estimación de funciones de densidad de probabilidad

- Se puede distinguir entre dos grandes grupos de estimación de funciones de densidad de probabilidad:
    - 1.Estimación paramétrica:  la función de densidad es estimada asumiendo un modelo de distribución conocido (por ej emplo, gaussiano, binomial, etc.), y utilizando los datos disponibles para ajustar los parámetros del modelo elegido. El problema será determinar dichos parámetros.
    - 2. Estimación no paramétrica o semiparamétrica: hace uso de técnicas que no hacen suposiciones (o hacen muy pocas y débiles) sobre la forma que tiene la función de densidad de probabilidad.
- métodos para calcular el error cometido:
    - el error cuadrático medio integrado o MISE (del inglés mean integrated squared error)
    -  el error medio absoluto integrado o MIAE (del inglés, mean integrated absolute error).
- ancho de bin h determina cómo de suave es la forma del histograma, por lo que recibe el nombre de parámetro de suavizado.
- Estimación por histogramas
    - Polígonos de frecuencias: son un método para estimar funciones de densidad de probabilidad, que se basan también en histogramas. La función de densidad de probabilidad se determina por interpolación lineal entre los puntos medios de cada una de las barras (o bins) del histograma. Es decir, primero se obtendrá el histograma, y luego se calculará el valor de la función de distribución en base a esta expresión. 
    - Método ASH: El método ASH (del inglés average shifted histogram) surge para tener en cuenta el origen t0. La idea detrás de este método es crear varios histogramas con igual ancho h y distinto origen t0 y promediarlos. De esta forma se consigue un estimador de la función de densidad más suave.
- Estimación Kernel: Normalmente se elige como función kernel una distribución de probabilidad conocida, siendo muy habitual elegir la normal estándar. Otro parámetro es el ancho de bin, h. 


## Análisis de series temporales 

- Una serie temporal es una sucesión de observaciones de una variable, o un conjunto de datos, que han sido recogidas de forma secuencial en distintos instantes de tiempo.
- El objetivo del análisis de series temporales es estudiar el comportamiento de la variable con respecto al tiempo para encontrar posibles patrones y para ser capaces de predecir valores futuros de dicha variable.
- El objetivo principal del análisis de una serie temporal es la predicción de valores futuros, aunque también interesa analizar la serie en busca de patrones, o para analizar las razones de posibles cambios en el tiempo.
- Representación de series temporales
    - Gráficas temporales, barras, velas
- Clasificiación de series temporales: 
    - Si la serie temporal es tal que se puede determinar exactamente un valor futuro, se dice que la serie es determinista. Si, por el contrario, el valor futuro **no se puede predecir con certeza, se dice que la serie es estocástica**.
    - Series temporales estacionarias: su media y su variabilidad se mantienen
constantes a lo largo del tiempo.
        - Siempre es deseable que las series temporales sean estacionarias porque, de esta forma, es más fácil hacer predicciones. Como la media es constante, esta puede predecirse usando todos los datos disponibles y usarse para predecir nuevas observaciones.
    - Series temporales no estacionarias: 
        - Cambios en la varianza
        - Son estacionales
        - Tienen tendencias. 
    - Análisis de series temporales: una serie temporal puede expresarse como la suma de varias componentes básicas, que son la tendencia, la estacionalidad y un término irregular o aleatorio. 
        - Componentes de una serie temporal no estacionaria: 
            - Tendencia: el cambio a largo plazo de la media
            - Estacionalidad: Pueden presentar estacionalidad. 
            - Aleatoriedad: ruido. 
        -Con el objeto de analizar la serie temporal y conocer su comportamiento a largo plazo, es necesario aislar de alguna manera la componente irregular para poder describirla con el modelo probabilístico más adecuado. 
            - Enfoque descriptivo: se estiman tanto la tendencia como la estacionalidad, quedando solo la aleatoriedad. 
            - Enfoque Box-Jenkins: Usando transformaciones y filtros se eliminan tanto la tendencia como la estacionalidad de la serie temporal. 
        - Heterocedasticidad: que la varianza aumente de forma proporcional en el tiempo.
        - Estimación de la tendencia: 
            - Relación determinista: En algunas ocasiones se puede expresar la relación entre la tendencia y el tiempo de forma lineal. 
            - Tendencia evolutiva: consiste en suponer que la tendencia evoluciona de forma suave en el tiempo y que en los intervalos cortos de tiempo se puede aproximar medias móviles. 
                - Cuanto mayor sea el orden de la media móvil mayor será el suavizado, pero se perderán más datos en el proceso. 
            - Diferenciación de la serie: Consiste en suponer que la tendencia evoluciona lentamente en el tiempo y no asumir ninguna forma determinada. 
        - Estimación de la estacionalidad: 
            - Coeficientes estacionales: se calculan como la media de las observaciones del periodo correspondiente, menos la media global de todo el periodo. 
                - Una vez calculado el coeficiente estacional, se desestacionaliza la serie restando a cada observación mensual su coeficiente estacional.
            - Diferenciación estacional: similar a la tendencia. 
    - Predicción de series 
        - Es necesario tener muchos datos. 
        - Para predecir la componente estacional, normalmente se presupone que esta no
cambia en el tiempo o lo hace de forma muy lentamente, por lo que se toma el valor de la componente estimada para el año anterior.
        - Modelo Box-Jenkins Arima
            - Son modelos de análisis y predicción útiles para variables unidimensionales que dependen del tiempo. Estos modelos se basan en la hipótesis de que los datos son estacionarios, por tanto, en el caso en que la serie no lo sea, hay que efectuar antes el análisis y las transformaciones necesarias para convertirla en aproximadamente estacionaria. Para ello se hace uso de las herramientas vistas para la tendencia y la estacionalidad.
        - modelo de alisado exponencial: Se basan en modelos paramétricos deterministas que se ajustan a la evolución de la serie. Se les dan distintos pesos a las observaciones, de forma que las observaciones más recientes tienen más peso que las más alejadas en el tiempo. Los pesos caen de forma exponencial a medida que las observaciones se hacen más viejas, de ahí su nombre
