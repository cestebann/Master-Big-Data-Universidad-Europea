
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

28/03/23

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
