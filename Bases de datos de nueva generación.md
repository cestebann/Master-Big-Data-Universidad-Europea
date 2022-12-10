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
1. **Invención de la máquina tabuladora.** Hermann Hollerith inveta la máquina tabuladora y la patenta en 1889. 

2. **Desarrollo de BBDD jerárquicas.** En los años 60s aparecieron los discos duros y se populariza el uso de BBDD que almacenaban la información en red o en modo de lista de árboles (jerárquicas). El objetivo era crear una capa independiente entre el SO y el aplicativo,  abstrayendo al aplicativo de la complejidad de acceso a la información. 

3. **Desarrollo del modelo relacional.** En 1970 Edgar Codd publica un manifiesto que normaliza el modelo relacional de BBDD y pasa a convertirse en el paradigma predominante. 
4. **Creación del lenguaje SQL.** Durante la década de los 80s se desarrolló el lenguaje SQL *(Structured Query Language)*, un lenguaje declarativo, fácil de aprender que permite crear y hacer consultas en BBDD de una manera simple, y que pasó a convertirse en un estándar en las BBDD relacionales gracias al apoyo de ISO y ANSI. 

5. **Desarrollo de BBDD orientadas a objetos.** En los años 90s aparece el modelo de programación orientada a objetos, que desbanca la programación estructurada, cuyo objetivo es simplifcar la arquitectura.

![](/img/bd_nuevas/orden_cronolo.png)

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

![](/img/bd_nuevas/tipos_bd_carac.png)

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
- **No estructuradas.** BBDD en los que la información no sigue ningún tipo de rigidez. Ejemplos son videos, fotos, llamadas telefónicas, etc. 

![](/img/estructura_bbdd.png)

#### BBDD según la ubicación de los servidores

- **BBDD Centralizadas.**  Son BBDD que corren en un único servidor, esto simplifica la capa de software de control de la BBDD ya que no tiene que gestionar interconexiones, seguridad, puntos de fallo, etc. A la hora de crecer debemos de aumentar los recursos de servidor central, esto tiene sus implicaciones como
- **BBDD Distribuidas.**  Son BBDD que distribuyen sus datos en varios servidores con el objetivo de aumentar su rendimiento. Implican un software más complejo para poder gestionar los diferentes servidores y la comunicación entre ellos.

!['Tipos de BBDD según la ubicación de los servidores'](/img/tipos_BBDD.png)

## BBDD Relacionales

![](/img/bd_nuevas/filas_tuplas.png)

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

![](/img/bd_nuevas/FN.png)

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

> "Una transacción se trata de la unidad básica de modificación desde el punto de vista del SGBD." - Ramakrishnan y Gerhke, *Sistemas de Bases de Datos*

!['ACID'](/img/ACID.png)

- **Atomicidad** La transacción se ejecuta por completo o no se ejecuta. Una transacción es una unidad indivisible, aunque esté formada por diferentes operaciones. 
- **Consistencia** Al ejecutar la transacción debemos partir de un estado válido de la BBDD y concluir en otro estado igualmente. 
- **Aislamiento** La ejecución de una transacción no debe afectar a otras transacciones. 
- **Durabilidad** Nos garantiza que una vez que se ha realizado una transacción, debe persistir en la BBDD y no se podrá deshacer incluso ante un fallo del sistema. 

### Escalabilidad y modelos distribuidos 

Escalabilidad: Capacidad que tiene un sistema para crecer aumentando las capacidades de sí mismo. Existen dos tipos: 
- **Escalabilidad vertical** Añadir más recursos a un equipo existente. Es la forma más sencilla de implementar ya que seguimos trabajando en el mismo servidor, no requiere cambios en las apps y hasta un límite es una solución económica. No obstante, es una solución limitada ya que no se puede disponer de infinitos recursos para un mismo recurso y a partir de un punto el coste se vuelve demasiado alto. 

- **Escalabilidad horizontal** Consiste en añadir nuevos equipos multiplicando de este modo los recursos disponibles. Podemos escalar horizontalmente infinitamente en la teoría. Este modelo requiere que el software sea capaz de trabajar sobre un **modelo distirbuido** y esta es una tarea bastante compleja. 

Debido al alto coste y la alta complejidad para mantener las propiedades ACID en un sistema de BBDD incremental, nuevos modelos horizontales han surgido para resolver estas problemáticas. 


## Siglo XXI - Aparación BBDD NoSQL y persistencia políglota

### Motivación BBDD NoSQL

Pese a las numerosas ventajas de las BBDD relacionales, existen algunas limitaciones:

- **Adaptación entre objeto-relacional** No existe correspondencia entre los objetos de las aplicaciones y su representación en las BBDD. Los registros de lenguajes orientados a objetos no se adaptan bien a las BBDD relacionales porque no contienen atributos complejos (registros anidados, listas...). Las BBDD orientadas a objetos surgieron para resolver este problema, pero era tal la popularidad de las BBDD relacionales y su lenguaje de consultas estándar, SQL, que se relegaron a un segundo plano. 

- **BBDD Integración vs. Aplicación** Una de las razones por las que las BBDD orientadas a objetos no reemplazaron a las relacionales, es debido al carácter integrador de estas últimas. No obstante, con el surgimiento de otros mecanismos de integración como los servicios web, los desarrolladores obtienen una alta oferta de tipos de BBDD que se adaptan mejor a la aplicación que se le quiere dar a su sistema. Es por ello que, claramente se prioriza la BBDD según la aplicación que se le quiera dar, al carácter integrador de la BBDD, que al final del día, no es algo que el cliente final sea consciente o valorice.

- **Escalabilidad.** Con la explosión incremental de datos ligada a la web2.0, surge la necesidad de implementar sistemas que sean capaces de correr de forma *distribuida* sobre clústeres de servicios. 

Es a partir de 2009 en San Francisco cuando Johan Orkarsson acuña el término NoSQL, refiriéndose a BBDD Not Only SQL. 

> **BBDD NoSQL**: aquellas BBDD, en su mayoría *open source* surgidas en el siglo XXI que no poseen una estructura fija y que están diseñadas para correr en clúster de forma distribuida (exceptuando las BBDD NoSQL de grafos que utilizan un modelo basado en relaciones). 


El surgimiento de las BBDD NoSQL no significa que van a desbancar a las relacionales de su trono, más bien, se amplía la gama de opciones a los desarrolladores y empresas para escoger la BBDD de acuerdo a sus necesidades y circunstancias, permitiéndole a la empresa centrarse en la función de la aplicación de cara al usuario final y otorgándole prestaciones superiores, y paralelamente del lado interno, haciendo imperativa la **persistencia políglota** de los equipos en el manejo de los sistemas de BBDD.


### Tipos de BBDD NoSQL

Se pueden clasificar en si están pensadas en escalar por medio de un clúster o no. 
- BBDD de agregados. 
- BBDD de grafos. 

### BBDD de agregados

No almacenan la información en tuplas con tablas estrcuturadas, formadas por atributos fijos, sino que se almacena por medio de objetos anidados o listas semiestructuradas (tipo documentos JSON o XML).

La información se coloca de manera desnormalizada. 

Los agregados aparecen debido a la necesidad contextual/ semántica de la aplicación que va a utilizar el usuario final, la bddd no tiene una estructura tan rígida. 

![](/img/bd_nuevas/agregado_vs_relacional.png)

A diferencia de los modelos relacionales, con el paradigma de agregados únicamente podremos acceder a una perspectiva por agregado por lo que tendremos que diseñar nuestro agregado en función de cómo los datos sean accedidos por el cliente final. Por ejemplo, en la imagen de abajo vemos la estructura de un documento en función del cliente y la misma información pero en función del contenido. 

![](/img/bd_nuevas/estructura_agregado.png)

![](/img/bd_nuevas/agregado_contenido.png)

Las implicaciones directas de trabajar con agregados son: 
- No existe un único modo o manera correcta de crear un agregado. Se pierde la normalización de la estructura.
- Contienen una clave que facilitará la tarea de distribución de los datos en los servidores. 
- Las transacciones y propiedades ACID se van a ver afectadas negativamente. 
- Las BBDD tienen un esquema flexible o simplemente no tenerlo. 
- El desarrollador tendrá complejidad de procesar y consultar la BBDD en función de cuán semiestructurada sea la información.

![](/img/bd_nuevas/los_agregados.png)

![](/img/bd_nuevas/BBDD_transaccionales.png)

![](/img/bd_nuevas/ausencia_esquema.png)


Ahora vamos a ver algunos tipos de agregados. 

#### Clave-valor

- Es una tabla con dos valores por registro: un ID (clave) y un valor. 
- El cliente solo puede interactuar con la BD por medio de la clave. 
- Manejan los diccionarios de manera excepcional.
- Tienen gran rendimiento y fácil escalabilidad. 

![](/img/bd_nuevas/clave_valor.png)

Ejemplos comerciales de estas BBDD son: 
- Redis
- Riak
- Memcached
- Dynamodb 

#### Columna ancha

Son como los clave-valor, pero los valores pueden a su vez actuar como claves de otros valores denominados familia de columna (*column family*). Se podría ver como una BD clave-valor de dos dimensiones. 

![](/img/bd_nuevas/columna_ancha.png)

Ejemplos comerciales de este tipo son: 
- Cassandra
- Hbase
- Hypertable
- SimpleDB

#### Documental

- El agregado está compuesto por documentos (tipo JSON o XML).
- Permite definir estructuras jerárquicas o listas. 
- Diferentes documentos guardados en la misma "tabla" no tienen por qué contener los mismos atributos. 
- Los documentos cuentan con un id que nos ayudará a distribuirlos. 
- A diferencia de los clave-valor, en las BBDD documentales sí conocemos la estructura del documento a nivel de cliente (se pueden hacer consultas con esa granularidad). 

Ejemplos comerciales: 
- MongoDB
- CouchDB
- Raven DB

![](/img/bd_nuevas/documental.png)

#### Motores de búsqueda 

- Aunque son similares a las BBDD documentales, están optimizadas para consultas complejas en tiempos de respuesta del orden de milisegundos. 
- Son capaces de indexar y realizar búsquedas sobre texto libre con gran eficiencia y devolviendo los resultados más relevantes en cada caso (trabajan muy parecido a los motores de búsqueda web).
- Se utilizan bastante para aplicaciones de BI y Machine Learning. 

Ejemplos comerciales: 

- Elasticsearch
- SolR
- Splunk
- OpenSearch

![](/img/bd_nuevas/motores_busqueda.png)

![](/img/bd_nuevas/full_text.png)


### BBDD de Grafos

Aunque se sale del alcance de esta asignatura, se aborda este tema a grosso modo. 

- Al igual que las BBDD relacionales, son un modelo en el que existen relaciones, sin embargo, son capaces de representar interconexiones mucho más complejas que las BBDD relacionales. 
- Simulan las redes neuronales. 
- Bastante uso en la IA. 

En la imagen de abajo se pueden ver las aplicaciones comunes. 

![](/img/bd_nuevas/grafos_usos.png)

Ejemplos comerciales: 

- Neo4J (!!)
- Microsoft Azure Cosmos DB
- Arango

En la clase se visualizó una simulación usando Neo4J para hacer recomendaciones, utilizando a Tom Hanks como referencia.


![](/img/bd_nuevas/neo4j.png)

# Actividad 1

## Ejercicio 1 (30%)

>  Tras lo visto en la primera unidad “Introducción a nuevas arquitecturas de modelos de datos” responda si las siguientes afirmaciones son verdaderas o falsas e intente razonarlas.

1. *Cuando diseñamos una BBDD relacional solemos apoyarnos en diagramas (E/R, UML…) para la realización del diseño conceptual. Sin embargo, en las BBDD NoSQL no es recomendable el uso de este tipo de diseños y se suele operar directamente con el SGBD.*

Falso. El diseño conceptual es independiente al modelo que se use.

2. *Una de las ventajas de las BBDD NoSQL de agregados es que al permitir estructuras de datos más complejas que las BBDD relacionales nos permiten acceder a los datos desde diferentes perspectivas con un único agregado.*

Falso. A diferencia de los modelos relacionales, con el paradigma de agregados únicamente podremos acceder a una perspectiva por agregado por lo que tendremos que diseñar nuestro agregado en función de cómo los datos sean accedidos por el cliente final.

3. *La ausencia de esquemas en muchas BBDD NoSQL de agregados puede suponer un problema para los desarrolladores a la hora de acceder o recuperar la información.*

Verdadero. La mayor libertad a la hora de definir las propiedades de cada uno de los registros también provoca que aumente su complejidad, ya que al extraer los registros no sabemos qué información vamos a recibir.

4. *El crecimiento de las BBDD NoSQL a lo largo del siglo XXI está provocando que la mayoría de las grandes empresas reemplacen todas sus BBDD relacionales por BBDD de este tipo.*

Falso. El surgimiento de las BBDD NoSQL no significa que van a desbancar a las relacionales de facto, más bien, se amplía la gama de opciones a los desarrolladores y empresas para escoger la BBDD de acuerdo a las necesidades y circunstancias del cliente, permitiéndole a la empresa centrarse en la función de la aplicación de cara al usuario final y otorgándole prestaciones específicas.

5. *Una de las ventajas de las BBDD NoSQL de agregados es que, a diferencia de las BBDD relacionales, podemos mejorar su rendimiento aumentando los recursos (RAM, CPU…) del servidor.*

Falso. Debido al alto coste de la escalabilidad vertical llegado un umbral y la alta complejidad para mantener las propiedades ACID en un sistema de BBDD relacional en un modelo horizontal, las BBDD NoSQL de agregados, atacan estos problemas de raíz compatibilizando la escalabilidad horizontal.  

## Ejercicio 2 (50%)

 > La empresa de juegos de mesa “Dragones y Mazmorras S.A.” tuvo un crecimiento fortísimo a raíz del confinamiento y necesita mejorar sus sistemas para adaptarse a este nuevo volumen de ventas. Para ello ha decidido contratarte como arquitecto de BBDD para que les ayudes a diseñar sus BBDD y encontrar la mejor solución para cada caso de uso. Las peticiones de la empresa son las siguientes:

### Realizar un diagrama Entidad/Relación (10%)

*Se pide realizar un diseño conceptual mediante un diagrama E/R que recoja los siguientes requisitos:*
- *“Dragones y Mazmorras S.A.” solo realiza **ventas** a través de tiendas físicas.*
-  *La empresa tiene **tiendas** ubicadas en diferentes **ciudades.***
-  *Un **cliente** únicamente está dado de alta en una tienda física.*
-  *Almacenamos como datos de los clientes su dirección (lo consideramos un único campo), su dni, su nombre y su teléfono.*
- *Los **juegos** se encuentran categorizados por **géneros** (educativos, RPG, estrategia…).*
- *Los géneros poseen un nombre único y una descripción del mismo.*
- *Los juegos poseen un identificador único, un nombre, una descripción y un precio de venta al público.*
- *Las **ventas** se producen cuando un cliente compra un juego o varios en una **tienda** específica.*
- *Cada **venta** posee un domicilio, una fecha de venta y un descuento total (puede ser 0).*

*Para simplificar el ejercicio se han identificado en negrita las entidades a representar, será necesario definir sus relaciones (con su cardinalidad) y sus atributos.*

![](/img/bd_nuevas/modelo_conceptual.png)

### Construir el modelo relacional (10%)

> Realizar el modelo relacional a partir del diagrama E/R construido en el ejercicio anterior. Las tablas deben estar definidas en tercera forma normal. Únicamente será necesario especificar las tablas, nombres de columnas, claves primarias y claves foráneas.

![](/img/bd_nuevas/modelo_fisico.png)


### Agregados y perspectivas (15%)

> El equipo encargado de la web de “Dragones y Mazmorras SA” se apoya en una BBDD de aplicación propia y han elegido para ello utilizar la BBDD NoSQL documental MongoDB. Para una nueva funcionalidad que están construyendo quieren crear un servicio que devuelva a partir del DNI del cliente los juegos que ha comprado y su género. Y como experto en BBDD acuden a ti en busca de consejo:

- **¿Podrías poner un ejemplo de cómo sería un agregado/documento? Es necesario especificar también su clave.** *(Se tendrá en cuenta únicamente el diseño del agregado y no si tienen sentido los registros, por ejemplo, catalogar - “La Oca” como juego de rol será válido siempre que el diseño sea correcto).*

![](/img/bd_nuevas/primer_agregado.png)

-  *Si tuvieran que crear un nuevo servicio que devolviera a partir del identificador de un juego los clientes que lo han comprado. **¿Podrían reaprovechar el agregado anterior? De no ser así, ¿Cómo sería el nuevo agregado?***

No, habría que hacer otra estructura. 

![](/img/bd_nuevas/segundo_agregado.png)


- *Mediante una BBDD relacional, **¿sería posible responder a estas preguntas sin modificar su esquema? De ser así, ¿Cuáles serían las sentencias SQL necesarias?***

Sí. 

Para acceder a los videojuegos y géneros que ha comprado el cliente: 

``` sql
SELECT j.nombre as "Nombre del videojuego", g.genero as "Género"
FROM juegos j, clientes c
INNER JOIN generos g,
ON g.ID_genero = j.ID_genero
WHEN c.DNI="1234567T"
```

Para consultar la lista de clientes que han comprado un determinado videojuego: 

``` sql
SELECT c.nombre as "Nombre del cliente"
FROM clientes c, ventas v, 
INNER JOIN generos g,
ON g.ID_genero = j.ID_genero
WHEN c.DNI="1234567T"
```


## Persistencia políglota (15%)

 > “Dragones y mazmorras SA” está empeñada en convertirse, con tu ayuda, en un referente a nivel nacional, por ello y una vez le has explicado la importancia de la persistencia políglota, te pide una recomendación de qué BBDD (de las vistas en la unidad 1) usar en cada caso de uso.

- *La organización ha crecido mucho y el departamento de BI quiere tener la capacidad de poder analizar de una manera ágil las ventas realizadas y poder realizar consultas interactivas mediante dashboards usando herramientas de reporting. ¿Qué tipo de BBDD recomendaríais?*

Motores de búsqueda 

- *La empresa cree que poniendo en contacto a los usuarios con gustos similares podría incrementar su volumen de ventas. Para ello quiere crear grupos en su web y quiere contar con una BBDD que le facilite tanto encontrar estos usuarios como almacenar las relaciones entre ellos a través de los grupos. ¿Cuál crees que sería la mejor opción de BBDD?*

BBDD basadas en grafos. 

- *En 2023 se celebra la conferencia mundial “Dice Rolling” y “Dragones y mazmorras SA” va a ser el encargado de construir la BBDD para el evento. Esta BBDD no tiene que cumplir las propiedades ACID, pero necesita poder escalar con facilidad para poder satisfacer los accesos de los usuarios. Gracias a la tecnología Cloud usada por la empresa podemos añadir nuevos servidores de forma instantánea, pero necesitamos una BBDD que se adapte bien a este crecimiento. ¿Qué tipo de BBDD recomendarías?*

Le recomendaría una BBDD clave-valor por el alto rendimiento que tiene para crecer horizontalmente. 

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


