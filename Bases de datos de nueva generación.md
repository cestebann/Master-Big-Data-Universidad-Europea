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
### 28/11/22

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




