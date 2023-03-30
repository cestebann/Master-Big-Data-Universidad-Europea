
Profesor: David Díaz Vico


Unidad 1. Introducción al aprendizaje automático
- Introducción al aprendizaje automático
- Aplicación de la IA al entorno empresarial.
- Principales proveedores de IA.
- Procesos del aprendizaje automático
Unidad 2. Aprendizaje Supervisado
- Métodos de predicción lineal
- Métodos simbólicos
- Fundamentos de Deep Learning
- Problemas del aprendizaje predictivo
Unidad 3. Otras técnicas de Aprendizaje
- No Supervisado - Agrupamiento
- No Supervisado – Reducción de dimensiones
- Sistemas de Recomendación
- Aprendizaje de métricas y ordenaciones
Unidad 4. Evaluación del aprendizaje
- Conceptos de Evaluación.
- Evaluación del aprendizaje supervisado
- Cálculo de medidas de efectividad del aprendizaje supervisado
- Shap Values
- Evaluación del aprendizaje no supervisado
Unidad 5. Análisis de textos y contenidos multimedia
- Análisis semántico y sentimientos.
- Clasificación de imágenes con ML ‘clásico’
- Introducción a Pytorch.
- Detección de imágenes con Deep learning
Unidad 6. Ética de la Inteligencia Artificial
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

# Aprendizaje Supervisado 


## Modelos Lineales

![](/img/aprendizaje_automatico/modelo_lineal.png)

### Ventajas
- Eficaces (resuelven problemas usando pocos paramétricos)
- Rápidos al predecir
- Interpretalbes (un parámetro pro cada variable de entrada indicando su relevancia).
- Estables (cambios pequeños en las variables de entrada suponen cambios pequeños en los parámetros al entrenar.)

### Desventajas
- Poder expresivo limitado por su naturaleza lineal. 

#### ¿Qué quiere decir que el sistema sea capaz de aprender?
- No debería necesitar que un humano codifique el conocimiento.
- Debería aprender únicamente observando los datos.
- El aprendizaje debería ser acumulativo. 


#### Solución iteratia
- Basada en descenso de gradiente.
- Permite entrenar poco a poco un modelo, 


Modelos Lineales: Regresión Lineal 
Modelos Lineales: Regresión Logística
Ejercicio Práctico

