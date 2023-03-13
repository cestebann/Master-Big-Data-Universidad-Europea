# Contenido del curso 

0. Objetivos del curso
1. [Gobierno del Dato](https://github.com/cestebann/Master-Big-Data-Universidad-Europea/blob/master/Gobernanza.md#1-gobierno-del-dato)
- Introducción al Gobierno del Dato
- Glosario, Diccionario y Catálogo de Datos.
- Gestión de Metadatos y Linaje Técnico.
- Gestión de la Calidad de Datos y Seguridad del Dato
2. Modelos de gobernanza
- Gestión de Datos Maestros (MDM) y Datos de Referencia.
- Marcos y Estándares del gobierno del dato
- Estrategia, Roles y Ámbitos de Actuación.
- Herramientas de gobierno del dato
3. Ciclo de Vida del Dato
- Gestión del Ciclo de Vida del Dato
- Gestión del Valor del Dato.
- Gestión de Modelos de Aprendizaje Automático en producción (MLOps).
- Herramientas de operativa de modelos MLOps.


# Objetivos del curso

## Competencias específicas

- Analizar y argumentar los agentes del mercado, empresas y tecnologías que participan en
el sector del análisis de grandes volúmenes de datos en infraestructuras distribuidas.
-  Integrar, implantar y explorar aplicaciones de análisis de datos en plataformas de altas
prestaciones, incluyendo la privacidad y la protección de los datos.

## Resultados del Aprendizaje

- Modelar, diseñar e implantar modelos de gobernanza del dato.
- Definir el ciclo de vida del dato en función del negocio o caso de uso de aplicación

# 1. Gobierno del dato

## 1.1. Introducción al gobierno del dato

### Objetivos de la lección 

- Contexto actual en la gestión de datos por parte de las organizaciones.
- Conceptos generales de qué es un gobierno del dato.
- Conceptos generales sobre los principios de un gobierno del dato.
- Fundamentos sobre principales ventajas y desventajas.

### 1.1.1. Contexto actual en la gestión del dato 

Según Statista, el volumen de datos creados, capturados, copiados y consumidos en todo el mundo en 2025, será de 181 zeta bytes, lo que se duplicarían todos los datos mundiales en apenas 4 años.

Debemos prepararnos para la gestión adecuada de todos estos datos, que debemos estimar que en las próximas décadas podrían llegar a cientos de miles o millones de zeta bytes. ¿Estamos preparados para dicha gestión? ¿Disponemos de metodologías al respecto? ¿Cómo podríamos dar respuesta para poner orden en todo este desorden anárquico digital? ¿Qué hacemos con la falta de microchips de procesadores que existe en el mercado actual? ¿Cuántos más datos mejor o peor? ¿Es sostenible este crecimiento?

#### 1.1.1.1. Crecimiento de los datos abiertos

Data Sharing: término definido por el Centro de Apoyo al Intercambio de Datos como: “recopilación de prácticas, tecnologías, elementos culturales y marcos jurídicos que son pertinentes para las transacciones en cualquier tipo de información en formato digital, entre distintos tipos de organizaciones”.

### 1.1.2. ¿Qué es un Gobierno del dato?

### 1.1.2.1. Definición

> "El Gobierno de Datos es el ejercicio de la autoridad y el control (planificación, el seguimiento y la aplicación) a través de la gestión de los activos de datos. La función de Gobierno de Datos sirve de guía de cómo se llevan a cabo todas las demás funciones de gestión de datos. El Gobierno de Datos es de alto nivel y administra ejecutivamente los datos”. - Asociación Internacional de Gestión de Datos, DAMA.
> “El mapeo de los derechos de decisión y la posterior creación de un marco de responsabilidad para garantizar que se adoptan los comportamientos adecuados en la evaluación, producción, consumo y control de los datos y las prácticas analíticas relacionadas”. - Gartner
> "“el proceso por el que una organización formaliza un deber fiduciario para gestionar los activos de datos críticos para su éxito” - Forrester

#### 1.1.2.2. Áreas del gobierno de datos

- Gestión de arquitectura de datos.
- Gestión de desarrollo de datos.
- Gestión de operación de base de datos.
- Gestión de seguridad de datos.
- Gestión de datos maestro y de referencia.
- Gestión de almacén de datos e inteligencia de negocio.
- Gestión de documentos y contenido.
- Gestión de metadatos.

#### 1.1.2.3. Responsabilidades del gobierno del dato

Los datos no son propiedad de las áreas de tecnologías de la información, sino que deben ser considerados como un activo estratégico de la organización.

El área de gobierno del dato es la autoridad y tiene las competencias sobre las gestión del dato, su calidad, metadatos, seguridad, utilización y distribución, entre otras, sin competencia directa sobre los sistemas tecnológicos en los que se encuentran alojados.

**Data steward**: En ellos recae la responsabilidad de que se asegure el control y uso de datos de manera eficiente en las organizaciones por áreas de negocio.
- Es un perfil perteneciente al área en cuestión.
- Tiene un alto grado de conocimiento funcional sobre los datos.
- Es el encargado de gestionar y administrar los datos correspondientes a su área de experiencia y conocimiento.

### 1.1.3. Principios del Gobierno del Dato

1. **Gobernanza normativa:** Desarrollo y mantenimiento de las políticas, estándares, normativas, comités de gestión del dato de alto nivel.
2. **Gobernanza técnica:** Desarrollo y mantenimiento de los metadatos, linaje técnico, calidad y seguridad de los datos, entre muchos otros, y todo lo relacionado con la gestión de datos desde el comienzo de flujo de datos desde la fuente de origen hasta la llegada de los datos al área funcional de la compañía.
3. **Gobernanza funcional:** Desarrollo y mantenimiento de la gestión de los datos, desde la llegada a su área funcional o de negocio hasta la utilización por el usuario final, facilitando el entendimiento de los mismos mediante *diccionario de datos*, *glosario y catálogos de datos*, así como las personas autorizadas para su consulta.


### 1.1.3.1. Objetivos del Gobierno del Dato

1. Útil
2. Focalizado al negocio y no a Tecnologías de Información
3. Iterativo
4. Decentralizado y no centralizado
5. Centrado en el empleado
6. Sin parálisis burocráctica

## Gestión de la Calidad de Datos y Seguridad del Dato

Sesión 4. 9/12/2022

Disponer de una buena gestión de datos y unos datos de calidad en los repositorios de la organización se ha convertido en una obligación, más que en un requisito con el creciente almacenamiento y procesamiento de grandes cantidades de datos. 

### Calidad del dato

> **Calidad del dato** Se refiere al estado de la información cualitativa o cuantitativa. Los datos son de alta calidad si son *aptos para usos previstos en las operaciones, la toma de decisiones y la planificación.* 

!   [](/img/gobernanza/propiedades_calidad_datos.png)


#### Definiciones sobre calidad del dato

- **Regla de calidad**: la regla define la forma funcional de cómo deben estar presentes los datos para servir a los propósitos de las áreas de negocio.
- **Control de calidad:** es la correlación de la regla de calidad con la información real;. Los controles son únicos y mantienen una relación uno a uno respecto a las notas de calidad (las KQI).
- **KQI (nota de calidad)**: un indicador porcentual que establece una nota de calidad en positivo y que explica de manera cuantitativa la adecuación de un dato a una regla de calidad establecida en un determinado sistema. *La agregación de varios KQI de la misma jerarquía permite monitorizar y establecer objetivos la calidad a nivel dato, métrica y reporte*. 
- **Problema de calidad de datos:** son inconsistencias en los datos, según lo definido en las reglas de calidad. Puede surgir en cualquier momento del ciclo de vida de los datos, desde la creación hasta la eliminación.
- **Plan de remediación**: acción correctiva de una inconsistencia de calidad. Pueden ser acciones puntuales de corrección, modificación en los procesos de origen o redefinición/creación de reglas de calidad.
- **Dimensión de calidad:** la dimensión de la calidad hace referencia al tipo o profundiad del control en términos de coherencia, completitud, duplicidad, formato, etc.
- **Perímetro de control:** los conjuntos de datos de objetos a ser perfilados y las localizaciones en el proceso donde deben implementarse.

Ejemplo:

![](/img/gobernanza/google_dataprep.png)

#### Metodología de control de calidad

1. **Perfilado de datos**: proceso de estudio, análisis y creación de resúmenes de datos útiles, siendo generalmente el primer paso crítico para asegurar la calidad de los datos. Esto se restringe únicamente para los atributos críticos o que generan valor. 
2. **Evaluación del perfilado:**  la identificación de los datos críticos y se analizan los resultados de aquellos conjuntos de datos que han obtenido un resultado que se aleja del estándar esperado.
2. **Definición de reglas y controles de calidad:** definición de las pruebas de calidad que se quieren implementar sobre los datos críticos. Se definirán los umbrales o resultados objetivos.
- **Definición de acciones a tomar:** definición de la toma de decisiones desde negocio (avisos, escalar, detener la operación) si un dato rebasa las tolerancias de error admisibles prestablecidos. 
- **Implementación de controles:** una vez validados los controles por los expertos de negocio, se implementan técnicamente en los puntos críticos del proceso, tanto manuales, como automáticos.
- **Diseño de un cuadro de mando:** definición de los cuadros de mando (dashboards), sistemas de alertas y avisos para las áreas de negocio. 
- **Monitorización de resultados:** visualización de los resultados reales de los QKI en reuniones/informes periódicos, que refleja el principal conocimiento sobre el estado de la calidad.
- **Evaluación de resultados:** activación de los planes de remediación, toma de decisiones por los actores poertinentes,  y definición de propuestas de mejoras en base a los resultados obtenidos.
- **Remediación:** Aplicación de las acciones correctivas correspondientes y de las propuestas de mejora, a la vez que se realizan las pruebas de validación correspondientes.

![](/img/gobernanza/metologia_controles.png)

#### Definición sobre cuadros de mando y monitorización 


![](/img/gobernanza/dashboard_monitorizacion.png)

#### Agregación de KQIs

![](/img/gobernanza/agregacion_kqi.png)

#### Controles sobre calidad del dato

![](/img/gobernanza/controles_tipos.png)


# 2. Modelos de gobernanza

## Gestión de Datos Maestros (MDM) y Datos de Referencia

### Definición de datos maestros

Un dato maestro es un dato relevante a la actividad de la compañía y es una fuente de verdad indiscutible (ingresos,)

 > “La administración de datos maestros es el control de los valores de los datos maestros para asegurar el uso consistente, compartido y contextual de la versión de la verdad sobre las entidades esenciales del negocio, en los diferentes sistemas de la empresa” - DAMA

> "**La gestión de datos maestros (MDM)** es una disciplina tecnológica en la que las empresas y los departamentos de TI colaboran para garantizar la uniformidad, la precisión, la gestión, la coherencia semántica y la responsabilidad de los activos de datos maestros compartidos de la empresa."

> "**Los datos maestros** son el conjunto coherente y uniforme de identificadores y atributos ampliados que describen las **entidades principales de la empresa** (como clientes, clientes potenciales, ciudadanos, proveedores, centros, jerarquías y planes de cuentas)”. - Gartner 

### Metodología de la gestión de datos maestros

El procedimiento debe asegurar la gestión, asegurando su actualización y calidad.

Las tres fases principales para la gestión de datos maestros y de las diferentes actividades a llevar a cabo en cada una de ellas para una correcta gestión de datos maestros son las siguientes. 

![](/img/gobernanza/metodologia_datos_maestros.png)

![](/img/gobernanza/golden_record.png)

#### Fase 0. Descubrimiento de datos maestros

![](/img/gobernanza/fase0.descubrimiento_dmaestros.png)

### Beneficios de la gestión de los datos maestros

![](/img/gobernanza/beneficios_dmaestros.png)



## Gestión de Datos de Referencia

> "la administración de datos referenciales es el control del dominio de los valores definidos (también conocido como vocabulario), incluyendo el control sobre los términos estándares, los valores de los códigos y otros identificadores únicos, las definiciones de negocio para cada valor, las relaciones de negocios dentro y entre las listas de los dominios de valores; así como también el uso consistente y compartido de los valores de los datos referenciales relevantes, precisos y **oportunos para la clasificación y categorización los datos**”.- DAMA

### Diferencias entre un Dato de Referencia y Datos Maestros

**IMPORTANTE** Los datos maestros representan términos claves para las áreas de negocio, con datos relacionados con clientes y actividades de negocio. Los datos de referencia representan un conjunto de datos aplicables y obtenidos de los datos maestros.

Son cualquier dato que se utiliza para caracterizar, clasificar y catalogar otros datos, o para relacionar datos con información externa a una organización.

![](/img/gobernanza/proceso_dmaestros.png)

### Beneficios de Datos de Referencias 

![](/img/gobernanza/beneficios_dreferencia.png)

![](/img/gobernanza/ciclo_metadatos.png)



**Sesión 5. 15/12/2022 pendiente**


Sesión 6. 22/12/2022

# Ciclo de vida del dato y modelos analíticos 

## Ciclo de vida del dato

![](/img/gobernanza/ciclo-de-vida.png)

### Tipos de datos

- **Datos calientes.** Se refiere a los datos almacenados en la plataforma por un tiempo determinado y durante ese tiempo nunca se borran. 
- **Datos fríos.** orientado a datos históricos, hacen referencia a los datos de que pasado un tiempo sin uso no requieren ocupar espacio en el almacén de datos calientes, por lo que pasan a un estado de almacenamiento secundario.

## Gestión de Modelos de Aprendizaje Automático (MLOps)

> Es un conjunto de prácticas que tiene como objetivo implementar y mantener modelos de aprendizaje automático en producción de manera confiable y eficiente. La palabra es un compuesto de aprendizaje automático y la práctica de desarrollo continuo de DevOps en el campo de software. 

### Fases de un modelo de aprendizaje automático 

1. **Reprocesamiento de datos.**
2. **Separación del conjunto de datos.**
3. **Entrenamiento del modelo.**
4. **Evaluación del modelo.**
5. **Ajustes de hiperparámetros.**
6. **Evaluación final y despliegue.**

- Matriz de confusión

![](/img/computacion/matriz_confusion.png)

### Elementos de un modelo analítico 

![](/img/gobernanza/elementos_modelo_analitico.png)

### Entrenamiento 

![](/img/gobernanza/entrenamiento.png)

### Ejecución de un modelo analítico

El modelo ya compara datos reales, está ya desplegado

![](/img/gobernanza/ejecucion_m_analitico.png)

### Ciclo de vida de un modelo analítico 

Esta metodología tiene partes en común con las buenas prácticas de devops y es a veces llamada MLOps (Machine Learning Operations), pues estandariza todo el proceso de gestión el ciclo de vida de los proyectos analíticos, dentro de los cuales se generan activos analíticos. También está alineada con las formas de trabajo ágiles, pudiendo ser el objetivo de un sprint el recorrer al menos una vez todo el ciclo e ir mejorando el modelo continuamente, sprint a sprint. El siguiente diagrama ilustra la metodología, poniendo de relieve la naturaleza iterativa del proceso:

![](/img/gobernanza/ciclo-de-vida-m-analitico.png)


### MLflow 

Es una plataforma de código abierto para administrar el ciclo de vida de ML, incluida la experimentación

## Control de versiones 

> El método de git-flow



- El examen son 20 preguntas tipo test. (Son 4 opciones, solo hay una opción correcta )
- No hay factor de corrección.
- Para estudiar el examen lo mejor es estudiar los PDFs. 

