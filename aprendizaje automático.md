
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
- 