# Visualización de Datos 

Profesor: Sandra Becker


# Contenido del Curso

- Objetivos 
- Unidad 1. Introducción a la visualización de datos
    - Introducción a la visualización de datos
    - Tipos de visualizaciones
    - Visual Encoding
    - Percepción humana
- Unidad 2. Visualización de datos en la práctica
    - Hands on: Visualización dinámica
    - ¿Qué es una buena visualización?
    - Elementos de la interactividad
    - Animación en la visualización
- Unidad 3. Visualización dinámica Parte (I)
    - Introducción
    - Manipular y preparar datos
    - Análisis exploratorio de datos (EDA)
    - Conceptos principales
- Unidad 4. Visualización dinámica Parte (II)
    - Visualizaciones simples
    - Visualizaciones animadas
    - Visualizaciones interactivas
    - Visualizaciones avanzadas
- Unidad 5. Visualización de datos geolocalizados
    - Introducción
    - Opciones de styling & scaling
    - Location Intelligence a través del análisis
    - Interactividad con los widgets y publicación
- Unidad 6. Visual Storytelling en la practica
    - Introducción al mundo de Visual Storytelling
    - Creación de una historia visual
    - Lenguaje visual
    - Conceptos: Scrollytelling, Martini Glass Structure, Drill-down


# Objetivos

## Competencias específicas:
-  CE2. Aplicar las bases teórico-prácticas necesarias sobre Tecnologías de la Información y Comunicaciones de interés para el desarrollo e implantación de servicios de análisis y ex-tracción de modelos a partir de los datos en infraestructuras de altas prestaciones.
- CE4. Diseñar y ejecutar un proceso completo de descubrimiento de conocimiento, inclu-yendo las fases de almacenamiento, procesamiento y visualización de los datos.
- CE9. Evaluar las posibilidades de la gestión masiva de datos y la inteligencia artificial en el desarrollo del negocio en los diferentes sectores de aplicación (banca, salud, comunicacio-nes, gobierno, etc.).
- CE10. Investigar tendencias técnicas en tecnologías y procesos de descubrimiento de infor-mación y generación de conocimiento a partir de los datos.
- CE11. Aplicar las diferentes metáforas de visualización, analíticas visuales, y tecnología necesaria para mejorar la interpretación de los datos en el proceso de interacción hombre-máquina.
## Resultados de aprendizaje:
- RA1. Conocer las diferentes metáforas de visualización y tecnología necesaria para mejorar la interpretación de grandes volúmenes de datos.
- RA2. Diseñar visualizaciones en diversos dominios de aplicación.
- RA3: Conocer los procesos de diseño e implantación de soluciones en diferentes dominios.
- RA4: Diseñar soluciones que ayuden a la toma de decisiones.


# Unidad 1. Introducción a la visualización de datos

## Objetivos
Los objetivos que se pretenden alcanzar con este recursos son los siguientes: 
- Conocer el mundo y cómo se define la visualización de datos
- Aprender los objetivo sy el por qué de la visualización de datos. 
- Familiarizarse con el flujo de la creación a través de algunos ejemplos. 

## Intro

### ¿Qué significa la visualización de datos? 

![](/img/visualizacion/insights.png)

> El objetivos de la visualización es de elucidar a las personas. No es de entretener a ellos, no es de vender productos, servicios o ideas a ellos, es de informarles. Es tan fácil  y tan complicado como eso. - A. Cairo. 

### Flujo de la Creación 

![](/img/visualizacion/flujo_creacion.png)


¿Para qué necesitamos visualizar los datos? 

- Para entender los datos de manera sencilla
- Para tomar decisiones rápidamente.
- Proponer nuevas preguntas
- Conoctar ideas. 
- Responder a preguntas. 
- Mostrar patrones
- Descubrir los unknown unknowns. 


### Caso de uso: ¿Cómo ha cambiado el Big Data a la visualización de datos? 

- La compilación de muchos datos en pocas gráficas. 
- Le agrega complejidad, para la limpieza y el procesamiento de datos. 

> It's not what you look at what matters, it's what you see. - H. Thoreau

> The purpose of data visualization are insights, not pictures. - B. Schneidermann 

> Let my dataset change your mindset- H. Rosling

> The purpose of data visualizations is to englighten people. Not to entertain them, not to sell them products, services or ideas, but to inform them. It's as simple and as complicated as that. - A. Cairo

> Above all else, show the data. - E. Tufte

![](/img/visualizacion/big_data.png)

El big data nos permite hacer un zoom out enorme de nuestros datos para encontrar patrones, que con una cantidad de datos menor, no seríamos capaces de detectar. 

![](/img/visualizacion/big_data_2.png)


![](/img/visualizacion/big_data_3.png)


### Caso de uso: Predicción 

Las predicciones tienen mucho peso hoy en día, pero son naturalmente inciertas, lo cual se puede representar visualmente con la transparencia por ejemplo. 

Si vamos a generar predicciones, también tenemos que calcular la predicción de que ocurra dicha predicción. 

![](/img/visualizacion/big_data_4.png)

![](/img/visualizacion/pasos.png)

### Caso de uso: simulación 

![](/img/visualizacion/simulacion.png)


### Caso de uso: Storytelling

![](/img/visualizacion/stortytelleing.png)


### Caso de uso: algoritmo 

![](/img/visualizacion/algoritmo.png)

### Data Art

La visualización de datos también incluye un aspecto de belleza que a veces es la única razón para su creación y se llama "DataArt"

![](/img/visualizacion/art.png)


## Tipos de visualización de datos 

### Objetivos

- Conocer lso diferentes tipos de visualización 
- Aprender la importancia de elegir el tipo adecuado. 
- Entender cómo el uso de la interactividad puede influir el tipo de la visualización 

### Diferentes tipos de la visualización de datos

![](/img/visualizacion/un_conjunto_25_vis.png)


#### Un conjunto de datos, 25 visualizaciones

https://flowingdata.com/2017/01/24/one-dataset-visualized-25-ways/


#### Catálogos

[Data viz project](https://www.datavizproject.com)


[Data viz project. Muestra qué tipo de visualización se puede crear en función de la información](https://www.data-to-viz.com)

![](/img/visualizacion/catalogo)



### Spaguetti plot

![](/img/visualizacion/catalogo)

Con todas las líneas, coloes y puntos es muy difícil ver el comportamiento y los patrones de los datos. 


#### Highlighting

en el fondo siguen las líneas, pero con el highlighting reforzamos las líneas que que queremos que el usuario vea. 

![](/img/visualizacion/highlighting.png)

#### Filtering


![](/img/visualizacion/filtering.png)

#### Small Multiple

La idea es mostrar a lo largo del itempo varias visualizaciones a la vez. 

![](/img/visualizacion/small_multiple.png)

#### Filtering & Linked Highlighting

![](/img/visualizacion/filtering_linked_highlighting.png)

#### Small multiple, Filtering & Highlighting

![](/img/visualizacion/small_multiple_filtering_highlighting.png)

## Visual Encodings

### Objetivos

- Entender qué son los visual encodings y cómo se usan. 
- Presentar los diferentes tipos de visual encodings y su fiuncionamiento a través de diferentes ejemplos: colores y posición. 
- Demostrar el uso adecuado de los visual encodings. 

### ¿Qué es un visual encoding? 

#### Seeing = Understanding

![](/img/visualizacion/visual_encoding.png)



#### ¿Qué es un visual encoding? 

Un visual encoding es traducir cualquier información cuantitativa o categórica a un elemento visual, y por otro lado cuando la persona mira a la visualización, pueda descodificar esta información intuitivamente. 

![](/img/visualizacion/visual_encoding_2.png)


De acuerdo a los tipos: 

![](/img/visualizacion/visual_encoding_3.png)

Los más importantes son: 

- Color
- Posición 
- Saturación 
- Tamaño 



#### Los más adecuados 

![](/img/visualizacion/los_mas_adecuados.png)

### Color 



#### Color wheel

![](/img/visualizacion/color.png)



#### Herramientas online

![](/img/visualizacion/color_brewer.png)

![](/img/visualizacion/color_adobe.png)

![](/img/visualizacion/viz_palette.png)

#### Ejemplos

![](/img/visualizacion/ejemplo.png)

![](/img/visualizacion/ejemplo_2.png)

![](/img/visualizacion/ejemplo_3|.png)

## Percepción humana

- Transmitir las reglas básicas de la percepción humana. 
- Introducir diferentes conceptos y cómo pueden afectar a la comprensión de las visualizaciones. 
    - El concepto Weber's Law. 
    - El concepto Gestalt Principles
    - El concepto Cuarteto de Anscombee. 
    - Introducir diferentes conceptos y cómo pueden afectar a la comprensión de las visualizaciones. 
- Introducir la perspectiva del usuario y los conceptos relativos como por ejemplo evitar el chart junk, presentar la verdad y mostrar datos marginales. 


### Conceptos de la percepción 

> ¿ Por qué nos debería interesar la visualización? Porque el sistema visual humano es un buscador de patrones de enorme poder y sutileza. El ojo y la corteza visual del cerebro forman un procesador masivamente paralelo que proporciona el canal de mayor ancho de banda a los centros cognitivos humanos. En los niveles más altos de procesamiento, la percepción y la cognición están estrechamente relacionadas, por lo que las palabras "comprender" y "ver" son sinónimos. - *Information Visualization, Second Edition, Colin Ware, Morgan Kaufmann Publishers, 2004, page 21. 

#### Weber's Law

![](/img/visualizacion/weber's%20law.png)

![](/img/visualizacion/webers_law.png)


#### Gestalt's - formato vs. colores

Gesalt dice que los colores tienen un poder mucho más fuerte para distinguir diferentes clases que las formas. 

![](/img/visualizacion/gestalt.png)

![](/img/visualizacion/gestalt_2.png)

#### Cuarteto de Anscombee

![](/img/visualizacion/cuarteto_anscombee.png)

![](/img/visualizacion/cuarteto_anscombee.png)

## ¿Quién va a ser el usuario de la visualización? 

Cuando estemos haciendo visualizaciones 

- Para qué sirve este elemento. 
- Cuánto sirve
- Cuánto pesa (espacio visual, atención. )

### Evitar el chartjunk

![](/img/visualizacion/chart_junk.png)

### Presentar la verdad 

![](/img/visualizacion/presentar_verdad.png)

### Cómo presentar outliers 

![](/img/visualizacion/como_ver_outliers.png)

# Unidad 3. Visualización dinámica con D3.js/Observable - I

El objetivo de esta unidad es familiarizarse con el mundo de la programación y específicamente la librería de D3.js. Se muestra sobre todo el funcionamiento de las tecnologías fundamentales, en el entorno de D3.js. Después se explica cómo manejar los datos y los funciones principales de D3.js (selecciones, escalas y ejes).





## D3 - Data-Driven Documents

https://d3js.org/

![](/img/visualizacion/d3.png)

![](/img/visualizacion/svelte.png)

D3.js es una librería escrita en Javascript, pero afecta a la página. 

![](/img/visualizacion/d3_2.png)

