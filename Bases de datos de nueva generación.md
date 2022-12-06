# Objetivos del curso

## Competencias específicas 

- **Diseñar, implantar y administrar redes e infraestructuras físicas** para el tratamiento de grandes volúmenes de datos distribuidos.
- Diseñar y ejecutar un **proceso completo de descubrimiento de conocimiento,** incluyendo las fases de almacenamiento, procesamiento y visualización de los datos.
- Aplicar las bases técnicas del funcionamiento de sistemas distribuidos de altas prestaciones, sus entornos de desarrollo y bases de datos (SQL y noSQL).

## Resultados del aprendizaje 
-  Modelar, diseñar, y administrar redes de infraestructuras para el almacenamiento de grandes volúmenes de datos y su tratamiento.
- Diseñar **y usar bases de datos de nueva generación (noSQL)** y sus diferencias con las bases  de datos relacionales.
- Desarrollar algoritmos y usar de tecnologías para el acceso a bases de datos de nueva generación.

# Unidad 1. Introducción a nuevas arquitecturas de modelos de datos
#### 21/11/22

## Objetivos
1. Comprender la evolución de las BBDD a lo largo de la historia.
2. Identificar los distintos tipos de BBDD.
3.  Entender qué es un sistema de gestión de BBDD.
4. Poner en valor la importancia del modelo relacional y sus características más relevantes.
5. Comprender los motivos que provocan la aparición de nuevos modelos de BBDD.
6. Identificar los diferentes tipos de BBDD NoSQL y los grupos en los que se subdividen.
7.  Poner de manifiesto la importancia de la persistencia políglota.

## BBDD y su evolución hasta el siglo XX 

> "Una base de datos es una recopilación organizada de información o datos estructurados, que normalmente se almacena de forma electrónica en un sistema informático."- Oracle

### Cronología de la evolución de las BBDD
1. **Invención de la máquina tabuladora.** Hermann Hollerith inventa la máquina tabuladora y la patenta en 1889. 

2. **Desarrollo de BBDD jerárquicas.** En los años 60s aparecieron los discos duros y se populariza el uso de BBDD que almacenaban la información en red o en modo de lista de árboles (jerárquicas). El objetivo era crear una capa independiente entre el SO y el aplicativo,  abstrayendo al aplicativo de la complejidad de acceso a la información. 

3. **Desarrollo del modelo relacional.** En 1970 Edgar Codd publica un manifiesto que normaliza el modelo relacional de BBDD y pasa a convertirse en el paradigma predominante. 
4. **Creación del lenguaje SQL.** Durante la década de los 80s se desarrolló el lenguaje SQL *(Structured Query Language)*, un lenguaje declarativo, fácil de aprender que permite crear y hacer consultas en BBDD de una manera simple, y que pasó a convertirse en un estándar en las BBDD relacionales gracias al apoyo de ISO y ANSI. 

5. **Desarrollo de BBDD orientadas a objetos.** En los años 90s aparece el modelo de programación orientada a objetos, que desbanca la programación estructurada, cuyo objetivo es simplifcar la arquitectura.

### Sistemas de Gestión de BBDD (DBMS)

Un sistema de BBDD se compone de los siguientes elementos: 

1. **BBDD.** Las bases de datos, o la información. 
2. **SGBD/DBMS** Un sistema de Gestión de Bases de Datos o DBMS (Database Management System) Es el software que administra la BD y donde el personal técnico realiza consultas directas a la BD. 
3. **Aplicación.** Es el interfaz donde el usuario final interactúa con la BD sin tener conocimientos de programación o ser consciente que está interactuando con ella. 

Vamos a enfocarnos a hablar de los DBMS. Sus características son: 

- Independencia con respecto a los datos
- Acceso eficiente a los datos
- Integridad y seguridad de los datos
- Acceso concurrente y recuperación en caso de fallo
- Reducciónd del tiempo de desarrollo de las aplicaciones 

### Tipos de bases de datos

Las bases de datos se pueden clasificar de tres maneras: 

- En cuanto al modelo 
- En cuanto a la estructura de los datos
- En cuanto a la ubicaicón de los servidores 

#### BBDD según el modelo

- **BBDD Jerárquicas.** Fueron los primeros tipos de BBDD pero ahora es un modelo obsoleto. Este tipo de BBDD almacenaban la información jerárquicamente en forma de árbol invertido. Recorre en un solo sentido. Tiene una estructura inmutable. Un nodo hijo tiene un solo padre. 
- **BBDD en Red.**  Tiene una mayor flexibilidad que las jerárquicas debido a que rompen la limitación de que un nodo hijo solo pueda tener un nodo padre, permitiendo de este modo las relaciones muchos a muchos (aunque resulta compleja de implementar entre nodos de distintos niveles). 
- **BBDD Relacionales.** Los datos se organizan por medio del modelo entidad-relación. La BBDD relacionales proporcionan al usuario una forma de acceso a los datos eficiente y flexible
-- Columnas: Son las entidades. 
-- Tuplas: Son las filas en una tabla.
-- Claves primarias: le dan un identificador único a la tupla. 
-- Claves foráneas: permiten relacionar dos tablas entre sí. 

!['Ejemplo de una BBDD relacional'](/img/bbdd_rela.png)

- **BBDD Multidimensionales.** Se aplica mucho en el BI y el ámbito empresarial. La información se estructura en cubos. Está orientada para bases de datos transaccionales. Permiten consultas completas en línea de una manera rápida. Se liga a herramientas de reporting/visualización de datos.

!['BBDD multidimensionales'](/img/bbdd_multidim.png)

- **BBDD orientadas a Objetos.** Su objetivo es poder representar la estructura completa de un objeto y todas sus propiedades en el modelo de datos. Este tipo de BBDD simplifica mucho la labor del desarrollador al tener una relación uno a uno entre registros de las BBDD y objetos en su código.
- **BBDD Deductivas.** Tienen la capacidad de extraer conclusiones a través de ciertas reglas. 

#### BBDD según la estructura
- **Estructuradas.** Hace referencia a la información que se almacena en tablas mediante filas y columnas bien definidas. Su rigidez proporciona que el esquema de cada uno de los registros facilite la gestión y explotación de la información.
- **Semiestructuradas.** Cuentan con cierta organización pero sin ser tan estricta. Se encuentran en los lenguajes de marcado como XML o JSON. 
- No estructuradas. BBDD en los que la información no sigue ningún tipo de rigidez. Ejemplos son videos, fotos, llamadas telefónicas, etc. 

![](/img/estructura_bbdd.png)

#### BBDD según la ubicación de los servidores

- **BBDD Centralizadas.**  Son BBDD que corren en un único servidor, esto simplifica la capa de software de control de la BBDD ya que no tiene que gestionar interconexiones, seguridad, puntos de fallo, etc. A la hora de crecer debemos de aumentar los recursos de servidor central, esto tiene sus implicaciones como
- **BBDD Distribuidas.**  Son BBDD que distribuyen sus datos en varios servidores con el objetivo de aumentar su rendimiento. Implican un software más complejo para poder gestionar los diferentes servidores y la comunicación entre ellos.

!['Tipos de BBDD según la ubicación de los servidores'](/img/tipos_BBDD.png)

## BBDD Relacionales


### Un modelo estándar

El modelo relacional ha tenido mucha popularidad y uso porque: 

- es un modelo que los desarrolladores y profesionales de BBDD pueden aprenderlo con relativa facilidad y aplicarlo en varios proyectos. 
- La mayoría de SGBD relacionales utilizan SQL, que permite a los desarrolladores utilizar una *lingua franca* que les permitirá interaccionar con varios SGBD. 

A continuación, la estructura de una tabla relacional. 

![](/img/Modelo_relacional_estructura.png)

### Diseño conceptual 

Antes de crear la BBDD es necesario elaborar el diseño de la misma. Los diagramas más utilizados para crear el modelo conceptual son los **diagramas entidad/relación.**

Los diagramas E/R se componen de: 
- Entidades. Representadas por rectángulos. Normalmente son sustantivos. 
- Atributos. Son cualidades o propiedades de las entidades. Se representran con un óvalo. 
- Relaciones. Describen la conexión entre dos entidades, normalmente son verbos y se representan por medio de rombos. 
- Cardinalidad. Hace referencia al número de entidades con la que otra entidad puede asociarse mediante una relación binaria. 
    - Uno a varios (1:*)
    - Uno a uno (1:1)
    - Varios a varios (* : *)

**El diseño conceptual es independiente del modelo de BBDD que se use, por ello es recomendable su uso aun cuando decidamos usar una BBDD no relacional.**

### Formas normales

Para asegurar la normalización de las BBDD se han postulado las formas normales. Si se cumplen, es casi garantizado evitar determinados problemas, como la redundancia de datos o inconsistencias a la hora de modificar. Las formas normales van siendo cada vez más restrictivas conforme aumentan de nivel. Aunque en la actualidad hay 6FN, una BBDD se considera que está normalizada si tiene 3FN. 

**Primera forma normal**. 

La tabla de abajo no está en primera forma normal. 

!['1FN'](/img/1FN.png)

**Segunda forma normal.** 

!['tabla antes de 2FN'](/img/2FN_antes.png)


!['tabla con 2FN'](/img/2FN_despu%C3%A9s.png)

**Tercera forma normal**

!['tabla antes de 2FN'](/img/3FN_antes.png)


!['tabla antes de 2FN'](/img/3FN_despu%C3%A9s.png)


### Transacciones y propiedades ACID
### Escalabilidad y modelos distribuidos 

## Siglo XXI - Aparación BBDD NoSQL y persistencia políglota

### Motivación BBDD NoSQL
### Tipos de BBDD NoSQL


# Unidad 2. Introducción a las bases de datos distribuidas y el teorema de CAP

## ¿Cómo distribuimos nuestros datos?

Conoforme van creciento nuestros datos, las escabilidad vertican no es una opción, hemos llegado a los discos máximos y los recursos para aumentar el espacio son muy costosos. El dpto. IT nos da la opción de aumentar espacio con 3 servidores adicionales pequeños. 

1. Distribuimos la información de nuestros clientes (clusterizada, es decir, toda la info de los clientes va unida) uniformememente en los 3 servidores. 
2. Ubicamos la información de nuestros clientes por medio de un índice o con una función definida a la hora de crear la tabla. 


## Sharding

Este es un concepto fundamental 


 - Permite escalar horizontalmente
 - "Tolerancia a fallos"
 - Particionado
 - Enrutamiento 
 - Resharding / Mantiene uniformidad
 - Permite consultas analíticas


