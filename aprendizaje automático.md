
Profesor: David Díaz Vico

# Contenido del Curso


- Unidad 1. Introducción al aprendizaje automático
    - Introducción al aprendizaje automático
    - Aplicación de la IA al entorno empresarial.
    - Principales proveedores de IA.
    - Procesos del aprendizaje automático
- Unidad 2. Aprendizaje Supervisado
    - Métodos de predicción lineal
    - Métodos simbólicos
    - Fundamentos de Deep Learning
    - Problemas del aprendizaje predictivo
- Unidad 3. Otras técnicas de Aprendizaje
    - No Supervisado - Agrupamiento
    - No Supervisado – Reducción de dimensiones
    - Sistemas de Recomendación
    - Aprendizaje de métricas y ordenaciones
- Unidad 4. Evaluación del aprendizaje
    - Conceptos de Evaluación.
    - Evaluación del aprendizaje supervisado
    - Cálculo de medidas de efectividad del aprendizaje supervisado
    - Shap Values
    - Evaluación del aprendizaje no supervisado
- Unidad 5. Análisis de textos y contenidos multimedia
    - Análisis semántico y sentimientos.
    - Clasificación de imágenes con ML ‘clásico’
    - Introducción a Pytorch.
    - Detección de imágenes con Deep learning
- Unidad 6. Ética de la Inteligencia Artificial
    - Directrices éticas para el desarrollo de modelos de IA
    - Detección de sesgos
    - Ejemplos de dilemas éticos

# Unidad 1. Introducción al aprendizaje automático

## Objetivos

- Automatizar tareas que normalmente realizan seres humanos
- Tradicionalmente con sistemas expertos (IA basada en conocimiento)
- Ahora con Aprendizaje Automático (IA basada en datos)

## Conceptos Básicos

- Datos (D)
- Algoritmo de entrenamiento (t) (el optimizador)
- Modelo (M)

t:D --> M

## Tipos de Aprendizaje Automático 

- Aprendizaje supervisado
    - Clasificación 
    - Regresión 
    - Clasificación /regresión ordinal 
    - Selección /transformación de variables
- Aprendizaje no supervisado 
    - Clustering 
    - Selección / transformación de variables
- Aprendizaje semi-supervisado 
- Aprendizaje por refuerzo (no entra)
- Aprendizaje motivacional (no entra)

### Según el modelo 
- Modelos paramétricos (con aprendizaje basado en modelos)
    - Lineales
    - No lineales
- Modelos no paramétricos (aprendizaje basado en instancias)
    - Vecinos 
    - Procesos gaussianos
- Modelos semi-paramétricos 
    - Árboles de decisión 
    - Métodos kernel 

### Según el algoritmo de entrenamiento 

- Directorios/batch (solución analítica)
- Iterativos/ online (solución numérica)

## Funciones de pérdida y métricas

- Funciones de pérdida
    - Se minimizan durante el entrenamiento del modelo 
    - Log-loss/cross-entropy para clasificación 
    - MSE para regresión 
- Métricas
    - Se aplican una vez entrenado el modelo para determinar si es útil para el negocio. 
    - Accuracy (precisión, recall, F1), AUC, para clasificación
    - MCE, MAE, R2, para regresión. 

- ¿por qué es alta la función de pérdidas?
    - Error de estimación (dato)
        - Datos escasos, incorrectos, missing values, datos marginales, maldición de la dimensionalidad (error por tener muchas variables), etc. 
    - Error de aproximación (modelo)
        - Modelo no suficientemente expresivo para el problema 
        - Modelo demasiado complejo para la cantidad de datos disponible.
    - Error de optimización (algoritmo de entrenamiento)
        - Entrenamiento insuficiente (underfit)
        - Entrenamiento excesivo (overfit)
        
## Metodologías
- NO hay que tomárselas como guías que hay que seguir al pie de la letra. 
- pretenden estandarizar la práctica del análisis de datos. Son orientativas, no siempre se siguen al pie de la letra. 
- Unas son más amplias que otras, pero en general coinciden en lo básico. 

Las más conocidas son: 
- KDD (Knowledge Discovery from Data)
- SEMMA (Sample, Explore, Modify, Model, Assessment)
- CRISP-DM (CRoss-Industry Standard Process for Data Mining)

![](/img/aprendizaje_automatico/metodologia.png)

# Principales proveedores de IA y casos de éxito 

- IBM 
- Amazon 
- Microsoft 
- Google 

## IBM 
- Cloud computing, computación cuántica, consultoría
- Watson
    - Responde a preguntas en lenguaje natural (DeepQA)
    - Adquisición de contenido de fuentes estructuradas y no estructuradas
    - Clasificación, detección de relación entre entidades. 
    - Generación, puntuación y ranking de hipótesis. 

## Amazon 
- Marketplace 
- Cloud Computing (AWS)
- Alexa 

## Microsoft 
- Sistema operativo, ofimática. 
- Cloud Computing (Azure)
- Cortana 

## Google 
- Buscador, correo, Maps, Android
- Cloud Computing (Google Cloud)
- Asistente Google

##  Herramientas 

### Python 
- Lenguaje de propósito general y alto nivel 
- Interpretado y con tipado dinámico, lo que agiliza el protipado y facilita el trabajo interactivo. 
- Tiene gran cantidad de librerías de código libre: 
    - NumPy
    - SciPy
    - Scikit-learn 

### Anaconda / Miniconda
- Distribución de Python más extendida

## Práctica

- KneighborClassifier(n_neighbors=3)


7/03/23

### Aplicaciones

#### Sector financiero
- Asistentes virtuales (banca online)
- Valoración de riesgo de crédito 
- Detección de fraude y blanqueo de capitales
- Asesoría de inversiones, seguros, etc. 

#### Sector industrial
- Automatización de cadenas de producción 
- Coche autónomo 
- Gestión de stocks y demandas
- Ayuda en los diagnósticos


### Ingeniería de características

#### La maldición de la dimensionalidad
- Al aumentar la dimensionalidad de los datos, el volumen que ocupan crece exponencialmente y estos se hace más dispersos en el espacio, lo cual dificulta el entrenamiento de modelos de Aprendizaje Automático que generalicen correctamente

En la imagen de abajo vemos cómo cambia el espacio muestral cuando aumentamos el número de variables explicativas. Como consecuencia nuestros modelos pueden predecir erróneamente.

![](/img/aprendizaje_automatico/aumento_dimensionalidad.png)

#### Principio de Parsimonia / navaja de Okham 

"En igualda de condiciones, la expllicación más sencilla suele ser la más probable". 

En Aprendizaje Automático: "cuantas menos variables utilice el modelo (y por lo tanto menos hiperparámetros), mejor."

#### Mejora en las predicciones

Los resultados con un mismo modelo y algoritmo de entrenamiento pueden mejorar mucho si se utilizan las las cracterísticas correctas. 

Por ejemplo , un modelo lineal puede ser capaz de resolver problemas no lineales si se le suministran las características apropiadas, construidas manualmente como funciones no lineales de las características apropiadas, construidas manualmente como funciones no lineales de las características originales. 

#### Selección de variables

Se trata de seleccionar el subconjunto de variables que sea más adecuado para resolver el problema. 

Algunas técnicas habituales son: 
- Eliminación de variables con poca varianza. 
- Uso de tests estadísticos univariantes (chi cuadrado)
- Eliminación recursiva de variables, métodos wrapper, etc.  (es un método muy costoso porque selecciona las mejores variables para producir el modelo más efectivo al probar todas las variables).

``` python 

from sklearn.datasets import make.classification 
```

#### Transformación de variables
En este caso en lugar de seleecionar un subconjunto de variables se generan variables nuevas, "sintéticas", a partir de las originales, esperando que sean más útiles para resolver el problema. 

La técnica general más habitual es el análisis de componentes principales (PCA), aunque hay muchos métodos específicos para transformación de texto, imágenes, etc. 

- Principal Component Analysis: Realiza una proyección de los datos originales en un espacio de dimensión menor en el que se maximiza la varianza. Las nuevas variables son combinaciones lineales de las originales. No utiliza la variable target, es una técnica no supervisada.

- Linear Discriminant Analysis (solo clasificación): Realiza una proyección de los datos originales en un espacio de dimensión menor en el que se maximiza la separabilidad. Las nuevas variables son combinacviones lineales de las originales. 

![](/img/aprendizaje_automatico/lda.png)


### Práctica 


14/03/23

# 2. Aprendizaje Supervisado 


## Modelos Lineales

![](/img/aprendizaje_automatico/modelo_lineal.png)

Los modelos lineales funcionan muy bien para predecir variables que se pueden modelizar con una variable explicativa. 


### Ventajas
- Eficaces (resuelven problemas usando pocas variables paramétricas)
    - Los modelos lineales son el claro ejemplo de un modelo paramétrico: son modelos que al entrenarse guardan información del proceso en variables internas, y al momento de predecir sobre unas variables desconocidas utilizan esos parámetros. 
- Rápidos al predecir
- Interpretalbes (un parámetro pro cada variable de entrada indicando su relevancia).
- Estables (cambios pequeños en las variables de entrada suponen cambios pequeños en los parámetros al entrenar.)

### Desventajas
- Poder expresivo limitado por su naturaleza lineal. 

### Modelos Lineales: Regresión Lineal 

![](/img/aprendizaje_automatico/regresion_lineal.png)


y = variable a predecir
y con gorro = predicción del modelo. 
x= variable explicativa o independiente.
m = parámetro interno del modelo que se perfecciona durante el entrenamiento
b = parámetro interno del modelo que se llama sesgo (bias) o intercepto. 

Hipótesis
- Linealidad: La variable respuesta es combinación lineal de las variables independientes. 
- Ausencia de multicolinealidad: no hay colinealidad entre las variables independientes. 
- Homocedasticidad: la varianza de los residuos (errores) es constante entre observaciones. 
- Ausencia de autocorrelación en los errores: los errores no están correlacionados entre observaciones. 

#### Solución directa 

Ordinary Least Squares:Estamos buscando el parámetro que dé el mínimo error. 

![](/img/aprendizaje_automatico/se.png)

En esta solución no puede haber dependencias lineales entre las variables (hipótesis 2), porque de lo contrario no podremos calcular la función inversa. 

Este modelo no podría aplicarse para datasets grandes. 


##### ¿Qué quiere decir que el sistema sea capaz de aprender?
- No debería necesitar que un humano codifique el conocimiento.
- Debería aprender únicamente observando los datos.
- El aprendizaje debería ser acumulativo. 


#### Solución iterativa: solución aproximada

![](/img/aprendizaje_automatico/solucion_iterativa.png)


#### Regularización 

![](/img/aprendizaje_automatico/regularizacion.png)


![](/img/aprendizaje_automatico/regularizacion_2.png)

peso=parámetros

##### Variables categóricas
- Los modelos lineales funcionan únicamente con datos numéricos. 
- Las variables categóricas deben ser transformadas a codificación one-hot (codifica cada categoría como una combinación de 0s y 1s.)


### Modelos Lineales: Regresión logística

![](/img/aprendizaje_automatico/regresion_logistica.png)

![](/img/aprendizaje_automatico/regresion_logistica_2.png)

![](/img/aprendizaje_automatico/regresion_logistica_3.png)

## Práctica 1

- Es un problema de clasificación binaria, donde debeos hacer un modelo de supervisión de clasificación binaria (debe clasificar a los clientes entre propensos a contrar y no propensos a contatar.)

``` bash
conda env create -f <nombre del fichero>
# luego de crear el entorno con sus dependencias lo activamos
conda activate <nombre del entorno>
#ahora vamos a utilizar jupyter notebooks dentro del entorno, para ello aplicamos este código
python -m ipykernel install --user --name nombre_del_kernel --display-name "Nombre del kernel"
#Reemplaza nombre_del_kernel con el nombre que deseas dar al kernel de Python dentro del entorno virtual y Nombre del kernel con el nombre que deseas que aparezca en Jupyter Notebook.
#por último ya ejecutamos jupyter notebook 
jupyter notebook
```

28/03/23

## Máquinas de Vector De Soporte

### Linear SVC (Support Vector Classifier)

Más que cambiar el modelo, lo que hace este modelo es cambiar la forma en que se entrena. 

A partir de ahora siempre vamos a estar hablando de métodos iterativos (ya que el método directo es muy costoso.)

![](/img/aprendizaje_automatico/linear_svc.png)

La idea de este modelo es ser estricto a la hora de escoger cuál solución nos quedamos, y es donde entra el concepto de margen, y aquí es donde entramos a definri el margen de separación. 

![](/img/aprendizaje_automatico/linear_svc_2.png)

La recta H1 es mala. En cambio, las rectas H2 y H3 clasifican perfectamente el dataset. Pero el H3 tiene un margen de separación más grande que H2, que están deterinados por los vectores de soporte (la distancia mínima a un punto). 

De acuerdo a este modelo, la recta H3 es la solución más robusta ya que cuando incorporemos datos de test, es probable que se acerquen a la frontera y el modelo que tenga el mayor margen de separación es el que menos errores va a cometer y por ende va a cometer menos errores de clasificación. 

![](/img/aprendizaje_automatico/linear_svc_3.png)

![](/img/aprendizaje_automatico/linear_svc_4.png)

![](/img/aprendizaje_automatico/linear_svc_5.png)

Es como una regresión logística pero con una función de coste distinta. Gracias a ello conseguimos un modelo lineal con un margen de separación máximo. 


### Linear SVR (Support Vector Regrresion)

En este modelo queremos conseguir que todos los puntos estén contenidos en un ancho de tubo estrecho. 

![](/img/aprendizaje_automatico/svr_1.png)
![](/img/aprendizaje_automatico/svr_2.png)


## Modelos Kernel

- Los modelos lineales tienen muchas virtudes, pero su expresividad está muy limitada por su naturaleza lineal. 

- Por suerte, existe un truco matemático para hacer questos modelos funcionen en un espacio de dimensiónn muy alto o incluso infinito, en el cual los problemas de clasificación son siempre linealmente separables y los problemas de regresión siempre se pueden resolver con una forma lineal, evitando tener que realizar operaciones matemáticas extremadamente costosas en dicho espacio de alta dimensión. Es el llamado "truco del kernel". 
- Para ello, es necesario que el modelo pueda expresarse en términos de x=xxt en lugar de Z. Las SVM cumplen esta condición. 
- Sin embargo, estos métodos tienen un coste de entrenamiento y de predicción muy superior al de sus contrapartidas lineales, y su uso está limitado a datasets pequeños. 

![](/img/aprendizaje_automatico/kernel.png)

Este es un modelo bastante potente pero no es óptimo para datasets grandes ya que puede ser muy lento. A raíz de esto, han surgido las redes neuronales. No obstante, este no deja de ser es un modelo muy potente. 


## Modelos Naive Bayes

Este es un modelo que en la práctica no se suele utilizar y funciona estrictamente para problemas de clasificación. 

![](/img/aprendizaje_automatico/naive_bayes.png)
![](/img/aprendizaje_automatico/naive_bayes_2.png)


### Práctica 
https://ml-playground.com/


11/04/23

## Redes Neuronales Artificiales

### Limitaciones del modelo lineal

Problemas no linealmente separables: Si el problema no es linealmente separable, un modelo lineal no es suficientemente expresivo como para resolverlo.

Las redes neuronales resuelven esta limitación que tienen los modelos lineales.

### Componentes del error

1. Estimación: determinado por el tamaño y la calidad de los datos. 
2. Aproximación: determinado por la expresividad del modelo.
3. Optimización: determinado por el método de entrenamiento. 

Ahora mismo, los modelos lineales tienen problemas de aproximación que las redes neuronales sí son capaces de resolver. 

### Inspiración biológica

> Red neuronal artificial: “Paradigma de aprendizaje y procesamiento automático inspirado en la forma en que
funciona el sistema nervioso biológico. Se trata de un sistema de interconexión de neuronas
que colaboran entre sí para producir un estímulo de salida.”

![](/img/aprendizaje_automatico/neurona_naturall.png)

![](/img/aprendizaje_automatico/neurona_artificial.png)

![](/img/aprendizaje_automatico/neurona_artificial_2.png)

![](/img/aprendizaje_automatico/neurona_artificial_3.png)

![](/img/aprendizaje_automatico/neurona_artificial_4.png)

Como podemos ver, el perceptrón es un modelo lineal. No hay nada nuevo hasta ahora. 
La parte innovadora no es en el concepto del perceptrón, sino en el conjunto de perceptrones. El modelo que se utiliza actualmente es el de perceptrón multicapa. 
En la imagen tenemos 3 variables de entrada (círculos rojos, no son neuronas).
Tenemos 4 neuronas o 4 unidades en una capa oculta y una capa de salida de dos neuronas, tenemos una capa de dos dimensiones. 
Solo podemos conectar cada capa con la siguiente. 

- X = variables de entrada
- W1 = pesos (hiperparámetros) de las neuronas de la capa oculta
- W2 = pesos de las neuronas de la capa de salida. 
- F1 = Función de activación de la capa oculta. 
- F2 = Función de activación de la capa de salida

¿por qué ya no nos vale el método del descenso del gradiente? 


![](/img/aprendizaje_automatico/neurona_artificial_5.png)

#### Back-propagation

Tenemos una fase hacia adelante donde calculamos la activación desde la entrada hasta la salida. 
A partir de eso, calculamos la activación de la salida. 

### Teorema de Aproximación Universal

![](/img/aprendizaje_automatico/teorema_aproximacion_universal.png)

Este teorema nos dice qué se puede resolver con una red neuronal y qué no se puede resolver con una red neuronal. 

### El perceptrón Multicapa

- Cuanto más ancho y profundo es un perceptrón multicapa, más expresivo es. 
- Vamos a verlo con más detalle con algunos problemas de clasificación binaria en el plano. 

### Dificultades

- Mínimos locales más frecuentes cuantas más capas y unidades tiene el modelo
- Sobreajuste si el modelo es demasiado expresivo y no hay muchos datos

![](/img/aprendizaje_automatico/redes_neuronales.png)


El early stopping nos dice el número máximo de iteraciones. 
Una iteración es una época. 
Los datos de validación evalúan el error por cada época o iteración. 

![](/img/aprendizaje_automatico/early_stopping.png)

### Deep Learning

18/04

![](/img/aprendizaje_automatico/representation_learning.png)

El Deep Learning consiste en redes neuronales con muchas capas. Básicamente, los modelos de Deep learning van creando representaciones de los datos, una tras otra cada vez más sofisticadas, cada una a partir de la anterior.
Y llega un momento que la representación es tan buena que el problema ya es muy fácil de resolver. Lo que pretenden es ahorrar buena parte (no todo, porque siempre hay que siempre hay que preparar un poco los datos), del ETL (del procesamiento previo de los datos antes de de alimentar con ellos al modelo predictivo), pues tradicionalmente se ha hecho de forma manual, lo que es el Feature Engineering. Pues esto con el Deep learning.



#### Representation Learning 

![](/img/aprendizaje_automatico/representation_learning_2.png)


#### ¿Por qué no añadir más y más capas para conseguir mejores resultados?

A medida que pasa por más capas de la red neuronal, la información mejora, pero con 3 o 4 capas comienzan a surgir problemas.

##### Vanishing Gradient
- Desvanecimiento del gradiente. El gradiente se refiere al gradiente de la función de error respecto a los parámetros de la red, que es lo que en el método de back-propagation se va calculando capa a capa desde la salida hacia la entrada.
- Se observó es que este gradiente en las capas más cercanas a la salida de la red tenía un módulo grande al comienzo pero al entrenar el modelo de iteración a iteración, a medida que se iba propagando a través de las capas hacia la entrada de la red, el gradiente sigue haciendo cada vez más pequeño: se iba desvaneciendo el gradiente.
Durante el back-propagation entonces,  si el gradiente es muy pequeño, las capas no se entrenan porque los valores de sus parámetros apenas varían de iteración en iteración. 


###### Causas del vanishing gradient 

1. EL uso de funciones de pérdidas inapropiadas: en regresión, MSE y en clasificación cross-entropy. Aunque es el menor de los problemas porque hoy en día se sabe qué función de pérdida se debe utilizar para el tipo de modelo de aprendizaje (predicción o clasificación)
2. Función de activación escogida: 
    - Las funciones de activación tradicionales están acotadas y se saturan fácilmente. 
    - Esto hace que al apilar muchas capas el gradiente de la función de error tiende a 0. Las capas ya no pueden entrenar más.
    - Si el gradiente es muy pequeño, el entrenamiento es muy lento. 
    - Uno de los problemas es la función de activación que se estaba usando que era la función sigmoide (tiene asíntotas horizontales en los extremos)
    - Por lo tanto, se introdujo una nueva función que se llama ReLU, que es muy fácil de computar. Como beneficio es que podemos tener más ciclos de entrenamiento. 
3. Inicialización de los pesos de las neuronas: 
    - Tradicionalmente en una red neuronal los pesos se inicializan aleatoriamente, lo que se hacía para generar esos valores aleatorios iniciales era una distribución uniforme en un intervalo que venía determinado por el número de neuronas que tenía cada capa. Por ejemplo, si estoy inicializando una capa de 10 neuronas, pues levanto una distribución uniforme con los intervalos definidos en función de esas 10 unidades.
    - Glorot y Bengio demostraron en el paper *Understanding the difficulty of training deep feedforward neural networks*" que para conseguir que el gradiente de la función de error, se mantenga en unas magnitudes más o menos constantes, capa a capa, hay que tener en cuenta no solo el tamaño de la propia capa que se está inicializando, sino también el tamaño de la siguiente capa (aquella donde le llega el error) y además, la función de activación que se usa en las capas. En función de ya no solo las unidades de la capa, sino en función de estas 3 cosas, la incialización del back propagation funciona muchísimo mejor. 


![Función relu](/img/aprendizaje_automatico/relu.png)


![Función sigmoide](/img/aprendizaje_automatico/funcion_sigmoide.png)


Cuando se abordan estos 3 puntos el vanishing gradient deja de ser un problema. No obstante, cuando tenemos una gran cantidad de datos, otro problema puede surgir. 


##### Internal Covariate Shift
- Los modelos lineales y las redes neuronales necesitan entradas estandarizadas para entrenarse correctamente con métodos basados en descenso por gradiente. 
- Las capas ocultas reciben las activaciones de las capas previas no estandarizadas
    - Si estandarizas las variables te quitas el problema en la primera capa pero la primera capa transforma los datos con una función de activación que devuelve una salidas con rangos muy heterogéneos: unas serán muy grandes, otras serán muy pequeñas.
    - Estandarizar la variable solo te resuelve el problema en el primer nivel. 
- Esto produce los problemas de convergencia que teníamos al entrenar una regresión sin variables estandarizadas.

**¿Cómo se debe resolver esto?**

Se hace una estandarización, capa por capa por por mini-batches durante el entrenamiento, o sea, las activaciones de cada capa se estandarizan con cada mini batch de datos. Esta es una técnica que en general no suele hacer falta, pero puede ser un problema en una red neuronal muy grande.

##### Recomendaciones al crear un modelo de Deep Learning: inicalización, activación y regulación

- Se debe inicializar los pesos con una distribución que produzca gradientes del error
grandes y de la misma magnitud en todas las capas
- Hay que utilizar funciones de activación que no saturen tan fácilmente como las
clásicas
- Se deben utilizar técnicas de regularización basadas en ruido y normalizar batches
de datos entre las capas ocultas (batch-normalization para evitar el internal covariate shift y también técnicas basadas en ruido para evitar sobreajustes, como el dropout, que es una técnica de regularización que desactiva aleatoriamente durante el entrenamiento unidades en la capa. Como consecuencia, el modelo tiene el entrenamiento más complicado para evitar el sobreajuste y que cada una de las neuronas sean "útiles" sin confiar  que las demás vayan a serlo, ya que si desactivamos una neuronas, el modelo debe ser consistente para procesar la información con la la misma calidad de aprendizaje que con las neuronas activadas). 


![](/img/aprendizaje_automatico/convolucion.png)


### Datos espaciales y redes convolucionales 

Las redes convolucionales están adaptados para una estructura espacial o en forma de rejilla (imágenes por ejemplo). El orden de las columnas de la matriz sí importa. 

Un modelo clásico no entiende que pueda haber un orden en las columnas (una neurona simple, un árbol de decisión). Le da igual que las columnas vengan en un orden u otro. 

![](/img/aprendizaje_automatico/redes_convolucionales.png)

![](/img/aprendizaje_automatico/convolucionales-2.png)

Ejemplo de una red convolucional

![](/img/aprendizaje_automatico/convolucionales-3.png)

Las redes neuronales no solo aplican para imágenes o videos sino también para cualquier dato que esté en forma de rejilla (datos meteorológicos)

### Datos temporales y redes recurrentes 

Los datos temporales pueden ser los datos bursátiles, donde las filas tienen un orden cronológico por timestamp. 

¿Cómo consiguen la memoria las neuronas recurrentes para saber que lo que están recibiendo son datos con estructura temporal? Bueno, pues la forma básica de neuronas recurrente es simplemente coger una neurona y hacerle una, una conexión de realimentación.

Le da a la neurona una memoria muy corta. 

![](/img/aprendizaje_automatico/redes_recurrentes_2.png)

Ejemplos de información que funcionan bien con redes recurrentes son: videos, lenguaje natural, etc. 


![](/img/aprendizaje_automatico/redes_recurrentes.png)

###  Transformers y NLP

![](/img/aprendizaje_automatico/nlp_transformer.png)

### Resumen 

Funciona bien en los problelmas en los que: 
- Los datos tienen estructura espacial o temporal. 
- El conjunto de datos es grande. 

Ejemplos: 
- Imágenes (convolucional)
- Video (convolucional y recurrente)
- Procesamietno de voz (recurrente)
- Lenguaje natural (recurrente o transformer)
- Series temporales (recurrente)

### Librerías

- Keras (es como Scikit-learn pero más complicado)
- Torch / PyTorch
- Las GPU ayudan mucho 




## Aprendizaje supervisado 
25/04

### Aprendizaje de reglas

#### Métodos simbólicos

- La corriente dominante de la IA hasta el auge del Aprendizaje Automático fue la de los Métodos Simbólicos.
- Los Sistemas Expertos forman parte de esta rama de la IA.
- Hoy en día son menos populares que el Aprendizaje Automático, pero siguen siendo muy utilizados y en muchas ocasiones complementan a los modelos de Aprendizaje Automático.
- Producen modelos fácilmente comprensibles e interpretables gracias a su manipulación explícita de las variables.
- La principal limitación de los Sistemas Expertos es el enorme coste que tiene la generación de su base de datos de reglas de conocimiento. Esto llevó al desarrollo de algoritmos de aprendizaje de reglas buscando al automatización de dicho proceso.
- Existen numerosos algoritmos de aprendizaje de reglas. PRISM es un ejemplo.


#### PRISM 

- PRISM (Programming In Statistical Modeling) es uno de los algoritmos de aprendizaje de reglas más conocidos.
- En cada paso construye una regla con un test sobre una variable que cubre un conjunto de ejemplares y se mide su nivel de acierto para el target. Se guarda la regla con mejor nivel de acierto. Se continua el proceso iterativo con los ejemplares cubiertos por la regla. El proceso termina al conseguir reglas con 100% de acierto para todos los ejemplares o cuando ya no hay más variables que utilizar.
- La evolución de este tipo de procedimientos da lugar a los modelos simbólicos de Aprendizaje Automático. En particular los Árboles de Decisión.

### Árbol de decisión 

- Son modelos de caja blanca (muy fáciles de interpretar, junto con los modelos lineales y de K-vecinos.)
- Son modelos de Aprendizaje Automático en los que las variables se manipulan de forma explícita, siendo los más fácilmente interpretables y sencillos de comprender junto con los modelos lineales y de vecinos.
- Los Árboles de Decisión son una evolución de los Sistemas Expertos y los algoritmos de Aprendizaje de Reglas. Los Árboles de Decisión construyen un conjunto de reglas de manera automática a partir de los datos etiquetados.

![](/img/aprendizaje_automatico/arbol_decision.png)

En este diagrama podemos apreciar que tiene una profundidad de 4 ramas, las ramas son los recuadros con bifurcaciones. Además, tenemos las hojas que son los recuadros al final de de las ramas. Sumando todas las hojas, debe resultar el tamaño del dataset utilizado 

#### Parámetros

- **Profundidad:** El número de ramas que puede tener el árbol. Habitualmente, se usa una profundidad de 3-6. El número de hojas va a a ser 2^n, siendo n la profundiad. 
- Criterio de calidad de los cortes
- Estrategia para realizar el corte
- Número mínimo de elementos por hoja
- Número mínimo de elementos para cortar

![](/img/aprendizaje_automatico/arbol_decision_2.png)

Las fronteras de clasificación utilizando el modelo de árbol de decisión son perpendiculares a los ejes y tiene sentido porque estamos cortando las variables. 

![](/img/aprendizaje_automatico/arbol_decision_3.png)

### Ensembles

Un solo árbol de decisión, por lo general no son muy potentes. Existen formas de mejorar un modelo de machine learning, que es construir *ensembles*: combinar modelos que ayudan a obtener mejores resultados. Aplica a los árboles de decisiones especialmente, porque si les cortamos la profundiad, son muy robustos y ajustan muy poco: son weak learners. 


Técnicas de combinación de modelos (ensembles)
• Bagging (Bootstrap aggregating)
• Boosting
• Stacking
• Otras

#### Bagging (Bootstrap aggregating)

Es una forma de construir ensembles. Una característica que tenemos que asegurar en los modelos es que exista diversidad: los modelos deben ser muy distintos entre ellos, porque así mejoramos la predicición de los datos. 

- En bagging, la diversidad la conseguimos particionando el dataset. 
- Utilizamos varios árboles de decisión y les damos a cada uno una partición del dataset.
-  Se entrenan por separado y en paralelo. 
- Cada árbol emite su voto de predicción. 
- Se elige como predicción global la clase mayoritaria más votada. 
- Como resultado, reduce la varianza de las predicciones. 
- El modelo más popular es el Random Forest. Funciona excelentemente para datos tabulares. No es un bagging simple, agrega una característica mayor a la diversidad: No solo reparte una partición del dataset a cada variable, sino que también discrimina las variables y las reparte a los diferentes árboles de decisión. De esa manera diversifica la capacidad de predicción de los modelos. 


#### Boosting 

- Cada modelo se entrena dando más importancia al subconjunto de los datos que obtuvo malas predicciones con los modelos entrenados anteriormente. 
    - Una vez entrenado el árbol de decisión, se pasa sobre el dataset, se generan las predicciones, se calculan las métricas de de los scores.
    - Y los datos para los que las métricas son peores se les da más importancia en el dataset para la siguiente iteración: se sobremuestrean.
    - Tenemos un nuevo dataset en el que están los datos originales, pero además los datos para los que la predicción del modelo entrenado en primer lugar no fue muy buena, esos aparecen más veces y tienen más peso claro, van a tener más influencia en el entrenamiento del siguiente modelo. 
    - Se entrena un segundo árbol de decisión y esta vez con el data SET ya modificado. Entonces, ese nuevo rol de decisión va a aprender a hacer mejores predicciones en los datos en los que el primero falló porque esos datos aparecen más durante su entrenamiento.
    - Añadimos este segundo árbol de decisión al ensemble que ya teníamos con el primer árbol de decisión, lo aplicamos al dataset de entrenamiento, y otra vez habrá datos con buenas predicciones y malas predicciones. 
    - Los datos con malas predicciones se vuelven a sobremuestrear y así se entrena un tercer modelo y se añaden al ensemble, y así sucesivamente. 
    - En resumen, se agrega un nuevo modelo en cada iteración, y el nuevo modelo se enfoca en los datos para los que no se predice bien en el ensemble hasta ese momento. 
-  Entrenamiento secuencial, no paralelizable. 
- Reduce el sesgo de las predicciones
- Los ejemplos más conocidos son AdaBoost(Scikit-learn), Gradient Boosting (Scikit-learn) y Extreme Gradient Boosting (**es excelente para datos tabulares, junto con los random forests**).

![](/img/aprendizaje_automatico/bagging.png)


#### Stacking

- No es muy utilizado. 
- Se entrena un modelo para combinar las predicciones de un conjunto heterogéneo de modelos (una red neuronal, un árbol de decisión, máquina de soporte, un random forest, etc.)




5/05/2023 

Práctica 2
- Hacer un estudio con técnicas no supervisadas para agrupar los clientes en distintas categorías y luego qué se puede hacer con ello. 
- Ser rigurosos con la metodología. 


Práctica 3. Reconocimiento de dígitos manuscritos

- Hacer una mejora en el código. 

# Aprendizaje no supervisado 

En este caso el target (y) no está disponible como en el caso del Aprendizaje Supervisado.
Veremos dos tipos de técnicas de Aprendizaje No Supervisado:

- Clustering: El objetivo es agrupar los datos. 
- Reducción dimensialidad. 

## Clustering 

El objetivo es agrupar los datos en un número prefijado de categorías o “clusters” que tengan sentido. 

Aunque el target no está disponible, y por tanto no hay una “respuesta correcta”, sí hay una serie de métricas que permiten estimar la bondad de los clusters obtenidos.


![](/img/aprendizaje_automatico/clustering.png)

La inercia es equivalente al MSE en regresión pero extrapolado a la clasificación. La inercia es la suma de la distancia de los puntos y los puntos del centroide del clúster asignado a esos puntos. Esa distancia se llama residuos. En pocas palabras, la inercia es la suma de los residuos. Cuanto menor sea la inercia, más concentrados estarán los puntos. 

### K-means

Una vez elegido el número de clusters K y el umbral mínimo de su loss function (normalmente inertia), sigue un proceso iterativo:

-  Elige aleatoriamente K centroides entre las muestras
- Itera los siguientes pasos:
- Asigna a cada muestra el centroide más cercano
-  Crea nuevos centroides como la media de las muestras asignadas a cada cluster
-  Si la loss cae debajo del umbral, termina

https://youtu.be/2kfY0R34Dy0?t=156

- No funciona bien cuando hay clusters de tamaños muy distintos
- Es muy inestable y sensible a outliers
- Su resultado depende de la inicialización

![](/img/aprendizaje_automatico/k_means.png)

![](/img/aprendizaje_automatico/k_means_2.png)

![](/img/aprendizaje_automatico/k_means_3.png)

![](/img/aprendizaje_automatico/k_means_4.png)

![](/img/aprendizaje_automatico/k_means_5.png

### Hierarchical Clustering


-  Es una familia de métodos de clustering que funcionan generando una jerarquía de clusters anidados que dividen o unifican
sucesivamente
- Tipo aglomerativo: enfoque bottom-up, empieza con un cluster por cada dato y va fusionando clusters
- Tipo divisivo: enfoque top-down, empieza con un cluster para todos los datos y va dividiendo clusters


### Gaussian Mixture

- Supone que los datos están generados por una mezcla de un número finito de distribuciones gaussianas con parámetros
desconocidos. Cada una de esas gaussianas se corresponde con un cluster.
- Es parecido al modelo K-Means, pero además de los centroides estima también las covarianzas de los datos.
- Se entrena con el algoritmo Expectation-Maximization (EM)

https://en.wikipedia.org/wiki/Expectation%E2%80%93maximization_algorithm#Examples

![](/img/aprendizaje_automatico/comparacion.png)

## Reducción de Dimensionalidad

### Principal Component Analysis 

![](/img/aprendizaje_automatico/pca.png)


### Kernel Principal Component Analysis 

- PCA se expresa en términos de XtX, por tanto se puede utilizar el truco del kernel para aumentar su expresividad y conseguir transformaciones no lineales.
- Al igual que con otros métodos kernel, existen una gran variedad opciones como kernel, pero la más habitual es de nuevo el kernel RBF o gaussiano.
- El uso de kernel confiere a PCA mucha más expresividad, a cambio de un coste computacional mayor en entrenamiento e inferencia.

### Indpendent Component Analysis 

- También es un método de transformación lineal
- En este caso, el criterio es el de minimizar la información mutua entre las distintas componentes generadas
- Su uso más habitual es el de separar señales, por ejemplo en una grabación de audio en la que se oye a varias personas hablar, se podría utilizar ICA para obtener por separado las señales de audio de cada persona.


## Ejercicio práctico

