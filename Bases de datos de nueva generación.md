# Contenido




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
21/11/22

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
5/12/22

Se pueden clasificar en si están pensadas en escalar por medio de un clúster o no. 
- BBDD de agregados. 
- BBDD de grafos. 

### BBDD de agregados

No almacenan la información en tuplas con tablas estructuradas, formadas por atributos fijos, sino que se almacena por medio de objetos anidados o listas semiestructuradas (tipo documentos JSON o XML).

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
SELECT C.nombre AS 'Cliente', j.nombre AS 'Videojuego', g.nombre AS 'Género'
FROM cliente c, venta v, juego j, genero g, venta_juego vj
WHERE c.dni='0000000X'
AND c.dni = v.dni
AND v.numero_factura = vj.numero_factura
AND j.idjuego = vj.idjuego
AND j.idgenero = g.idgenero; 
```

Para consultar la lista de clientes que han comprado un determinado videojuego: 

``` sql
SELECT C.nombre AS 'Cliente'
FROM cliente c, venta v, juego j, genero g, venta_juego vj
WHERE j.idjuego=0
AND c.dni = v.dni
AND v.numero_factura = vj.numero_factura
AND j.idjuego = vj.idjuego
AND j.idgenero = g.idgenero; 

```


## Persistencia políglota (15%)

 > “Dragones y mazmorras SA” está empeñada en convertirse, con tu ayuda, en un referente a nivel nacional, por ello y una vez le has explicado la importancia de la persistencia políglota, te pide una recomendación de qué BBDD (de las vistas en la unidad 1) usar en cada caso de uso.

- *La organización ha crecido mucho y el departamento de BI quiere tener la capacidad de poder analizar de una manera ágil las ventas realizadas y poder realizar consultas interactivas mediante dashboards usando herramientas de reporting. ¿Qué tipo de BBDD recomendaríais?*

Motores de búsqueda 

- *La empresa cree que poniendo en contacto a los usuarios con gustos similares podría incrementar su volumen de ventas. Para ello quiere crear grupos en su web y quiere contar con una BBDD que le facilite tanto encontrar estos usuarios como almacenar las relaciones entre ellos a través de los grupos. ¿Cuál crees que sería la mejor opción de BBDD?*

BBDD basadas en grafos. 

- *En 2023 se celebra la conferencia mundial “Dice Rolling” y “Dragones y mazmorras SA” va a ser el encargado de construir la BBDD para el evento. Esta BBDD no tiene que cumplir las propiedades ACID, pero necesita poder escalar con facilidad para poder satisfacer los accesos de los usuarios. Gracias a la tecnología Cloud usada por la empresa podemos añadir nuevos servidores de forma instantánea, pero necesitamos una BBDD que se adapte bien a este crecimiento. ¿Qué tipo de BBDD recomendarías?*

Le recomendaría una BBDD clave-valor por el alto rendimiento que tiene para crecer horizontalmente. 


## Ejercicio 3 (20%)

> Desde su explosión a partir de los 2.000 las BBDD NoSQL han crecido exponencialmente en las empresas hasta el día de hoy, permitiéndoles llevar a cabo diferentes casos de uso. Se pide que encontréis algún caso de éxito del modelo NoSQL (puede ser BBDD de agregados o de grafo), y que argumentéis por qué en ese caso era más conveniente un enfoque NoSQL y sus ventajas frente al modelo relacional.

 [Toyota Material Handling Europa utilizando MongoDB](https://www.mongodb.com/blog/post/video-toyota-industry-40-creating-smart-factory-moving-from-monolithic-code-base-microservices-mongodb-atlas-microsoft-azure)

 Toyota Material Handling Europa es un conglomerado de la corporación Toyota que fabrica y comercializa carretillas, montacargas, AGVs y otros productos de logística avanzada. 

La decisión de utilizar MongoDB en Toyota surgió por cumplir el objetivo de trascender a la Industria 4.0. Este consiste en implementar  Internet de las Cosas (IoT) en todos sus productos y dispositivos que le permitirá a la fábrica ser más autónoma (de carretilleros y operarios de primer nivel), inteligente y segura. La imagen de abajo describe cómo estarían interconectados todos los artefactos de la fábrica a un servidor.

![](/img/bd_nuevas/actividad_1_toyota.png)

 Evidentemente, para el correcto tratamiento de la información de todos los múltiples dispositivos conectados, se necesitaba la arquitectura que capture, almacene, administre y analice las información entrante y la mejor solución en el mercado para cumplir estos criterios fue MongoDB. La imagen de abajo ilustra los objetivos de Toyota. 

![](/img/bd_nuevas/actividad_1.png)

Las razones por las que es más conveniente implementar una base de datos NoSQL en este caso son:

 - **Big Data.** El tratamiento de grandes volúmenes de datos obliga a buscar bases de datos autoadministradas, flexibles y escalables. Durante 8 años, Toyota ha procesado la información de 80k montacargas. Con el debido cuidado, la información se puede utilizar para generar patrones y luego predicciones que le permitan a la fábrica disponer únicamente de montacargas autónomos porque van a saber cuándo y dónde desplazarse.  
 - **Recolección de información semiestructurada.** La recolección y almacenamiento de datos de IoT viene como      sensores y vehículos debe ser en una base de datos flexible que no ponga restricciones a la entrada de datos con una estructura líquida. 
 - **Rápida escalabilidad  y rendimiento.** El almacenamiento de información en tiempo real de múltiples fuentes (ya no solo tablets y laptops) produce la necesidad de utilizar una base de datos que se adapte fácilmente al crecimiento constante y rápido.  
 - **Fuerte enfoque en la aplicación.** Mantenimiento y operaciones back-end automáticas que les permite a los desarrolladores enfocarse en las aplicaciones de uso, más que en la administración de la base de datos.  "La parte más hermosa es el modelo de datos. Todo es un documento JSON natural. Así que, para los desarrolladores, es fácil, muy fácil para ellos trabajar rápidamente. Dedicar tiempo a generar valor comercial, en lugar de modelar datos".


# Unidad 2. Introducción a las bases de datos distribuidas y el teorema de CAP

## Objetivos

Los objetivos que se pretenden alcanzar a lo largo de esta unidad son los siguientes:
- Aprender los conceptos de sharding y replicación en las BBDD distribuidas.
- Entender cómo se trata la consistencia en este tipo de BBDD.
- Comprender los motivos por los que las propiedades ACID no son aplicables en estos sistemas.
- Entender el teorema de CAP y las limitaciones que plantea.

## Sharding 

### ¿Cómo distribuimos nuestros datos?

Conoforme van creciento nuestros datos, las escabilidad vertical no es una opción, hemos llegado a los discos máximos y los recursos para aumentar el espacio son muy costosos. El dpto. IT nos da la opción de aumentar espacio con 3 servidores adicionales pequeños. 

1. Distribuimos la información de nuestros clientes (clusterizada, es decir, toda la info de los clientes va unida) uniformememente en los 3 servidores. 
2. Ubicamos la información de nuestros clientes por medio de un índice o con una función definida a la hora de crear la tabla. 

Las BBDD de agregados nos ayudan a poder trabajar en un entorno distribuido, ya que un agregado ideal contendrá toda la información que necesitamos extraer en cada acceso de la BBDD. Desde el punto de vista del almacenamiento esto implicará que todos los bytes que forman este agregado puedan almacenarse juntos en un único servidor y, que, al acceder a la BBDD, únicamente tengamos que acceder a uno de los servidores para extraer la información.

Al crear nuestro agregado debemos tener en cuenta algunos aspectos: 
- Enfoque en el contexto de nuestra aplicación: No existe un agregado único y dependerá de nuestro caso de uso, siendo probable que tengamos que modificar el agregado (o crear nuevos) si las necesidades de nuestra aplicación cambian.
- Aun asumiendo la redundancia de datos, no siempre será buena idea desnormalizar los datos. Existen casos de uso en los que algunas “entidades” que formen parte de un agregado se modificaran con mucha regularidad y el coste de mantener la consistencia nos lleve a crear varios agregados y realizar joins a nivel de aplicación realizando varios accesos a la BBDD para extraer la información completa. Estos joins se suelen realizar a nivel de aplicación debido a que la mayoría de BBDD NoSQL orientadas a agregados no soportan esta operación.

En resumen, la orientación a agregado nos abre las puertas a una distribución de datos menos compleja; pero a su vez no es una ciencia exacta ya que a partir del diseño conceptual es imposible llegar a una única definición de agregado. Por ello tendremos que definir estos agregados en función de las necesidades de cada caso de uso.


### Sharding 

Es el proceso de fragmentar los datos, es decir, dividir los datos en diferentes particiones y almacenar cada una de estas particiones en diferentes servidores. De este modo nuestra BBDD es capaz de escalar horizontalmente.

En la práctica implementar este concepto no es tan sencillo, ya que debemos conseguir particionar los datos de modo que la carga se distribuya uniformemente entre todos los servidores.

Algunos aspectos a tomar en cuenta son: 

- Se debe conseguir que cada acceso únicamente extraiga un agregado. De este modo garantizamos que el usuario únicamente necesita acceder a un servidor.
- Se debe tener la carga balanceada, por lo que tenemos que distribuir los datos de modo que cada nodo soporte la misma carga. Esto se complica cuando existen registros que son consultados constantemente (hotspot).
- En ocasiones es posible que queramos leer registros de forma secuencial, en ese caso es importante asegurarnos de que esos registros se escriban de este modo en un mismo nodo.

A la hora de realizar el sharding de nuestra BBDD tenemos que dotar a la misma de un mecanismo que permita a los clientes que se conecten a nuestra BBDD poder saber en qué servidor se encuentran los datos que necesita. Para ello tenemos dos opciones: utilizar una tabla maestra o utilizar una función.

#### Mediante tabla maestra

Utilizar una tabla maestra ubicada en un servidor externo a los servidores de datos que actúe como índice. De este modo el cliente tendría que consultar la ubicación del dato antes de acceder al mismo.

Este mecanismo presenta como ventaja su sencillez, pero también tiene la desventaja de que el servidor con la tabla maestra se convierte en un punto único de fallo (SPOF).

#### Mediante función 

La mayoría de BBDD actuales definen para cada colección de agregados las reglas de distribución para la misma, de este modo la distribución de los datos se realiza acorde a las necesidades de la aplicación.

Una vez definida esta función el cliente sabrá exactamente dónde se encuentra cada uno de los datos, esta función debe aplicarse sobre un registro (clave) que sea inmutable para evitar el movimiento de datos, usualmente se aplica sobre la clave primaria.

La mayoría de BBDD ofrecen la posibilidad de realizar esta distribución de manera automática, usualmente mediante un hash, sin embargo, no siempre es la mejor idea ya debemos tener en cuenta las características de nuestra aplicación para poder optimizar el rendimiento.

### Ventajas y Desventajas 


#### Ventajas

1. La principal ventaja del uso del sharding es que nos permite ampliar tanto la capacidad como el rendimiento de nuestra BBDD simplemente añadiendo nuevos servidores tipo *hardware commodity*.
2. Permite almacenar grandes cantidades de datos y responder a volúmenes de peticiones que serían impensables en un modelo centralizado.
- Resiliencia que nos proporciona ante posibles fallos, si un nodo de la BBDD cae únicamente perdemos parte de la información y los clientes pueden seguir accediendo al resto de los nodos.


#### Desventajas 

Si comparamos una BBDD con sharding con una BBDD centralizada, sin lugar a duda su principal ventaja es la complejidad añadida que implica el tener que trabajar con diferentes servidores. Esta complejidad se puede ver desde diferentes puntos de vista: 

- Particionado: Es necesario definir cómo queremos particionar los datos de modo que estos se distribuyan lo más uniformemente posible entre todos nuestros nodos.
- Enrutamiento: Estas BBDD requieren de un mecanismo que permita al cliente saber qué servidor contiene los datos que desea extraer, lo cual supone unna complejidad extra.
- Resharding: Una BBDD usualmente contiene un conjunto de datos vivos y tendremos que mantener la uniformidad en el reparto de datos, aunque estos cambien. Esto puede provocar que, en ocasiones, tengamos que reparticionar nuestros datos (resharding) para que vuelvan a distribuirse homogéneamente. El resharding es un proceso bastante costoso por lo que en la medida de lo posible debe realizarse un particionamiento que nos evite llegar a esta situación.
- Consultas analíticas: Cuando queremos procesar nuestros datos en las BBDD centralizadas podemos hacerlo en el propio servidor o en el del cliente. En cambio, al trabajar con grandes cantidades de datos que se encuentran en diferentes nodos en la BBDD distribuidas usualmente recurrimos a métodos de procesamiento distribuido en los mismos servidores en los que se encuentran los datos. Este tipo de analítica, aunque más potente, añade una complejidad extra. Un ejemplo de este tipo de procesamiento distribuido es el framework Map-Reduce.

## Replicación 
12/12/2022

Repaso de la clase pasada. 

![](/img/bd_nuevas/cuestionario41.png)

![](/img/bd_nuevas/cuestionario42.png)

![](/img/bd_nuevas/cuestionario43.png)

![](/img/bd_nuevas/cuestionario44.png)

![](/img/bd_nuevas/cuestionario45.png)

![](/img/bd_nuevas/cuestionario46.png)

![](/img/bd_nuevas/cuestionario47.png)


Debido a la naturaleza de baja calidad del hardware en los sistemas distribuidos (hardware commodity) y al mero hecho de contamos con muchos servidores,  la posibilidad de que tengamos un fallo aumente considerablemente. Además, estos servidores no suelen “cuidarse” del mismo modo en el que se “cuidan” los servidores centralizados (“mascotas VS ganado”), mucho menos aún en despliegues Cloud, por lo que debemos establecer un mecanismo que nos proporcione tolerancia a fallos. Este mecanismo se denomina replicación.

**La replicación consiste en que cada agregado tenga copias, llamadas réplicas, en diferentes nodos que puedan ser usada en caso de fallo en el sistema.** Usualmente los sistemas distribuidos usan un factor de réplica de 3 (aunque es configurable), ya que nos proporciona una gran alta disponibilidad y en caso de un fallo nos permitiría perder otra réplica mientras tratamos de recuperarnos del mismo.

### Modelos de Replicación 

Existen dos modelos de replicación que se usan en las BBDD NoSQL orientadas a agregados. 

#### Master-slave 

En este tipo de replicación tenemos que dividir los nodos en dos tipos:
- **Un nodo máster**: Es el responsable de procesar y actualizar los datos. Solo se podrán ejecutar escrituras y modificaciones en el nodo máster. De este modo el sistema se asegura de que estamos modificando el último dato actualizado. 
- **Uno o varios nodos esclavos**: Son nodos secundarios que poseen una copia de los datos del nodo máster.

Este tipo de replicación nos proporciona varias de las ventajas antes vistas:

-  Si un nodo máster falla, el tener nodos esclavos sincronizados provoca que uno de esos nodos pueda asumir rápidamente el papel de máster.
- Se pueden optimizar las lecturas concurrentes ya que podemos redirigir las peticiones de lectura hacía los nodos esclavos pudiendo escalar horizontalmente conforme añadamos más nodos.
Sin embargo, este tipo de replicación no permite escalar horizontalmente en cuanto a escrituras, ya que es el nodo máster el encargado de realizarlas todas.

Otro aspecto para tener en cuenta es la consistencia, que la trataremos más adelante, ya que si leemos de un nodo esclavo no podemos garantizar que el dato sea el mismo que la última escritura en el nodo máster.

![](/img/bd_nuevas/master-slave.png)

#### Peer-to-peer 

Al prescindir del nodo máster, todas las réplicas en este tipo de arquitectura tienen el mismo peso y todas aceptan acceso tanto de lectura como de escritura, de este modo la caída de uno de los nodos no provoca la pérdida de acceso de ningún tipo a la BBDD.

Con estas características el modelo peer-to-peer nos podría parecer el modelo ideal, sin embargo, existen complicaciones ligadas a este modelo, la principal de ellas es la consistencia. Cuando puedes escribir un mismo registro en dos lugares diferentes, corres el riesgo de tener un conflicto “escritura-escritura”, que sería bastante más grave que un conflicto de lectura.

### Ventajas y Desventajas

A continuación se describen los pros y contras de la replicación en las BBDD orientadas a agregados con respecto a las BBDD centralizadas. 
#### Ventajas

- Permite tener alta disponibilidad (HA) en nuestra BBDD, en el caso de que un nodo falle el nodo con la réplica puede servirnos el dato.
- Permite optimizar los accesos por cercanía. Podemos tener los dos servidores separados geográficamente y en cada momento acceder al servidor más cercano.
- Permite optimizar las lecturas concurrentes, pudiendo distribuirse la carga entre todos los nodos que contengan una réplica del dato. De este modo podemos escalar horizontalmente en cuanto a rendimiento de lecturas.
- En el modelo peer-to-peer podemos también aumentar el rendimiento de las escrituras.

#### Desvventajas

-  La redundancia de datos ya que, por ejemplo, con un factor de replicación 3 necesitaríamos el triple de espacio de almacenamiento. Sin embargo, hoy en día el almacenamiento es relativamente barato y este aspecto no representa un gran inconveniente. 
- Al igual que en el sharding la replicación aumenta la complejidad de nuestra solución de BBDD ya que debemos tener un mecanismo que se encargue de replicar los cambios que realizamos en nuestra BBDD.
-  Por último, y quizás el aspecto más importante, hay que considerar el impacto que la replicación tiene en la consistencia, al ser necesario mantener la sincronía entre réplicas. Este punto lo trataremos a lo largo del apartado 4.

## Consistencia 

Vamos a abordar la consistencia desde el punto de vista de los conflictos que pueden surgir en una BBDD noSQL y qué factores inducen a que la perdamos.

### Conflicto escritura-escritura 

Cuando en una BBDD tradicional realizamos varias escrituras en un mismo momento queremos garantizar que estas se realicen de manera secuencial evitando un conflicto “escritura-escritura”, para ello las BBDD cuentan con un mecanismo de control de concurrencia que evita que se pierdan actualizaciones. Esta pérdida de actualizaciones en algunos casos no supone un gran problema en nuestra BBDD, pero si, por ejemplo, estamos trabajando con el saldo de una cuenta corriente el problema se acrecienta y es vital que siempre actualicemos a partir del último estado de la BBDD.

Imaginemos que Javier y María reservan casi al mismo tiempo un mismo asiento para el mismo vuelo, pero Javier llega un poco antes que María. 

![](/img/bd_nuevas/conflico-escritura-escritura.png)

Javier reserva el asiento y completa la reserva.

![](/img/bd_nuevas/conflico-escritura-escritura2.png)

María luego reserva su asiento en la misma plaza que Javier, inconscientemente y sin que el sistema se lo impida. 

![](/img/bd_nuevas/conflico-escritura-escritura3.png)

Como vemos la escritura de Javier se ha perdido en nuestra BBDD, aunque para Javier la escritura se haya realizado de manera correcta. Probablemente el día del vuelo nos encontremos con un caso de overbooking.

Un SGBD centralizado se puede resolver este conflicto desde dos perspectivas: 
- Un enfoque pesimista 
- Un enfoque optimista. 

La aproximación pesimista parte de la base de que los conflictos pueden ocurrir y actúa antes de que estos ocurran para prevenirlos. El mecanismo pesimista más habitual son los bloqueos, consiste en que antes de realizar cualquier actualización se adquiere un “cerrojo” de este modo el sistema se segura que solo un cliente tiene un “cerrojo” en cada momento.

En el ejemplo anterior, en el momento de que Javier accede al sistema de reservas, el sistema lo protege con un cerrojo que impide que cualquier otro usuario pueda hacer cambios al mismo tiempo y deberá esperar hasta que Javier complete su reserva o finalice la sesión. 

![](/img/bd_nuevas/conflico-escritura-escritura4.png)

La aproximación optimista en cambio no previene los conflictos, sino que deja que estos ocurran y en ese momento los detecta y actúa para resolverlos. Un mecanismo común son las actualizaciones condicionales que consisten en que en el momento de la actualización, se comprueba si el valor que se va a actualizar difiere de la última lectura; en el caso de que así sea, la escritura falla y es necesario reintentarla.

![](/img/bd_nuevas/conflico-escritura-escritura5.png)

En un sistema master-slave, el mecanismo no es diferente al de un BBDD centralizada, ya que solo es el nodo máster el encargado de modificar y hacer lecturas sobre los datos. 

![](/img/bd_nuevas/conflico-escritura-escritura6.png)

No obstante, en un sistema peer-to-peer el problema se agrava ya que  todos los nodos pueden hacer escrituras y es más complicado aplicarle un cerrojo a un usuario (ya que puede estar en cualquier nodo) y además, todos los nodos deben estar de acuerdo a la hora de modificar un dato. Esto se soluciona a través del Quórum que se verá más adelante. 

![](/img/bd_nuevas/conflico-escritura-escritura7.png)

### Conflicto lectura-escritura 

#### Consistencia lógica

Usualmente, si pensamos en un modelo relacional, los datos están repartidos en varias tablas y es común que cuando tengamos que realizar modificaciones en la BBDD tengamos que realizarlas en diferentes registros, que pueden estar a su vez en diferentes tablas. Si en el periodo entre el inicio de la actualización y el final de la misma, otra persona accediera a las diferentes tablas se encontraría con una BBDD inconsistente. Este tipo de conflictos se denominan conflictos de lectura-escritura y debemos evitarlo para mantener en nuestra BBDD una consistencia local, es decir, asegurar que todo el conjunto de datos tiene sentido juntos.

Como ya vimos, las BBDD relacionales resuelven estos conflictos con las transacciones que cumplen las propiedades ACID, garantizando, entre otros, el aislamiento entre transacciones. Evitando este tipo de conflictos aseguramos la consistencia lógica de nuestra BBDD.

En las BBDD NoSQL de agregados no se suelen cumplir estas transacciones ACID y solo se garantiza la atomicidad y el aislamiento cuando modificamos un único agregado. Esto significa que obtenemos consistencia lógica únicamente cuando trabajamos con los agregados de forma individual, de otro modo tendremos un tiempo denominado ventana de inconsistencia en el que no tendríamos consistencia lógica en nuestra BBDD

![](/img/bd_nuevas/conflicto-lectura-escritura.png)

#### Consistencia eventual 

De nuevo la replicación introduce nuevos problemas de consistencia, ya que si leemos los datos de diferentes nodos es probable que las últimas actualizaciones no se repliquen a la vez en todos los nodos y nos encontremos con diferentes valores dependiendo del nodo en el que estemos leyendo. Esta inconsistencia ocurrirá durante un tiempo hasta que las actualizaciones se repliquen a la totalidad de los nodos, es por ello que a este tipo de consistencia se le denomine consistencia eventual o consistencia débil, en contraposición de la consistencia fuerte (que garantiza que siempre se lea la última actualización).


![](/img/bd_nuevas/conflicto-lectura-escritura2.png)

![](/img/bd_nuevas/conflicto-lectura-escritura3.png)

![](/img/bd_nuevas/conflicto-lectura-escritura4.png)

En un sistema master-slave, si fuerzas que las lecturas se hagan en el nodo master, aunque se pierda rendimiendo, aseguras que el usuario va a leer la última versión moddificada. En un modelo peer-to-peer, se leerían todos los nodos y el sistema devuelve la última versión aunque existen modelos más sofisticados. 

## Quórum 

Para obtener una consistencia fuerte no es necesario involucrar la totalidad de los nodos, usualmente basta con involucrar a una mayoría de los nodos; esto es lo que denominamos el quorum. Podemos ver dos tipos de quorum, de lectura y de escritura.

El quorum de escritura viene definido por el número de nodos que participan en una escritura para garantizar una consistencia fuerte, en la práctica solo la mitad más uno de los nodos (que contienen una réplica del dato) son necesarios para garantizarla.

![](/img/bd_nuevas/quorum-escritura.png)

El quorum de lectura se trata del número de nodos necesarios para garantizar que estamos leyendo el último dato escrito, es decir que haya consistencia fuerte, sin embargo, en el caso de la lectura no podemos tener una fórmula tan sencilla ya que depende del quorum de escritura configurado y tenemos que asegurarnos que al menos leemos la réplica del dato en alguno de los nodos en los que se ha escrito. Siendo:

- N: Factor de replicación
- W: El número de confirmaciones necesario para la escritura

El número de lecturas necesaria sería N-(W-1).

Este modelo aplica a una distribución peer-to-peer, ya que como hemos hablado hasta ahora en un modelo maestro-esclavo podemos evitar los conflictos accediendo directamente al nodo máster.

![](/img/bd_nuevas/quorum-lectura.png)

## ACID en BBDD NoSQL Orientadas a Agregados 

1. **Atomicidad.** En los modelos de agregados garantizar la consistencia entre agregados se vuelve una tarea compleja y costosa computacionalmente por lo que la mayoría de estas tecnologías únicamente garantizan esta atomicidad a nivel de agregado.La consistencia nos indica que al ejecutar la transacción debemos partir de un estado válido de la BBDD y concluir en otro estado igualmente válido.
2. **Consistencia**. La consistencia nos indica que al ejecutar la transacción debemos partir de un estado válido de la BBDD y concluir en otro estado igualmente válido. Aún quedándonos a nivel de agregado, es posible que nuestra BBDD no tenga la consistencia fuerte de las BBDD relacionales debido a la replicación y, en función de la configuración que hagamos, tengamos que optar por una consistencia eventual.
3. **Aislamiento.** El aislamiento hace referencia a que la ejecución de una transacción no debe afectar a otras transacciones. Es decir, el estado intermedio de una transacción no debe ser visible por otras transacciones.consistencia. Ya vimos que si trabajábamos con diferentes agregados otro cliente podría ver el estado intermedio de nuestras modificaciones. Por lo tanto, al igual que la atomicidad, el aislamiento solo puede garantizarse a nivel de agregado.
4. **Durabilidad**. La durabilidad nos garantiza que una vez que se ha realizado una transacción, esta debe persistir en la BBDD y no se podrá deshacer incluso ante un fallo del sistema. Depende de la configuración, hay casos de uso que puede sacrificarse la durabilidad como en una memoria caché. 


![](/img/bd_nuevas/acid_no_sql.png)

### Modelo Base 

El Modelo BASE surge en contraposición del modelo ACID, ya que deja de ser válido en las BBDD NoSQL orientadas a agregados. 

- **Basically Available**: Los modelos NoSQL que hemos descrito a lo largo de este tema dejan de centrarse en la consistencia total de la BBDD para, mediante la distribución de datos con shards y réplicas, asegurar la disponibilidad.
- **Soft state**: De nuevo debido a las posibles inconsistencias lógicas no podemos garantizar el estado de nuestra BBDD como lo hacen las BBDD ACID, quedando esta responsabilidad delegada a la parte de la aplicación.
- **Eventually consistency**: Como hemos visto hay escenarios en nuestras BBDD distribuidas, no todos, en el que nos encontramos consistencia eventual. 

## Teorema del CAP

Este teorema hace referencia a tres propiedades que son deseables en cualquier sistema de datos distribuido: la tolerancia a particiones, la consistencia y la disponibilidad.

### Propiedades del Teorema

#### Particiones

Cuando diseñamos la arquitectura de nuestra BBDD los servidores donde se encuentran los servidores que almacenan las diferentes réplicas pueden encontrarse:

- **En un mismo rack:** Dentro del mismo rack podemos tener diferentes servidores. La comunicación entre ellos es muy confiable, pero tenemos bastantes elementos en común (alimentación, red…) que hacen que un fallo en uno de ellos pueda provocar la pérdida de todas las réplicas.
- **En diferentes racks:** Es una práctica habitual, que, aunque los servidores se encuentren en la misma sala de un CPD (o zona si hablamos de Cloud), estos se encuentren en diferentes RACK para asegurar su disponibilidad en caso de fallo en alguno de los componentes comunes. La comunicación en este caso sigue siendo bastante confiable.
- **En diferentes zonas/salas de un mismo CPD/Región:** Podemos pensar que teniendo toda la información en la misma sala aún corremos bastante riesgo de que haya fallos generales que afecten a toda la sala; por este motivo podemos distribuir los datos entre diferentes salas (zonas si hablamos de Cloud) aumentando de este modo la disponibilidad. En este caso los nodos estarán conectados por comunicaciones entre salas, que, aunque estén más expuestas que los casos anteriores siguen siendo confiables.
-  **En diferentes regiones/CPD:** Por último, podemos pensar en separar nuestras réplicas en diferentes CPDs (regiones si hablamos de Cloud) ofreciendo redundancia geográfica que nos proteja ante cualquier desastre (p.e. un corte de luz en nuestro CPD). En este caso la disponibilidad aumenta considerablemente, pero, a cambio, la comunicación entre nuestros nodos se debe realizar a través de internet, que es una red bastante menos confiable que las redes privadas descritas en los casos anteriores.

![](/img/bd_nuevas/ubicacion-particion.png)


Una partición de red es cuando un nodo o una réplica se queda incomunicada del sistema. 

![](/img/bd_nuevas/particion_red.png)

#### Disponibilidad 

La  disponibilidad hace referencia a que la BBDD siempre estará disponible para operaciones de escritura y lectura, aunque en algunos momentos el resultado devuelto no sea el último escrito (consistencia eventual).

![](/img/bd_nuevas/disponibilidad.png)


#### Consistencia

La consistencia, desde el punto de vista del teorema, se basa en la consistencia a nivel de agregado y nos dice que ante una lectura la BBDD siempre debe devolver la última versión escrita.

![](/img/bd_nuevas/consistencia.png)

### El Teorema

Este teorema hace referencia a las tres propiedades vistas anteriormente:
- Tolerancia a las particiones.
- Consistencia.
- Disponibilidad

Y enuncia que todo sistema de datos distribuido puede cumplir como máximo con dos de estas tres propiedades.

El 100% de los sistemas distribuidos prefiere y debe  escoger la Tolerancia a Particiones y sacrificar o Disponibilidad o Consistencia.


![](/img/bd_nuevas/teorema_cap.png)

#### Renunciamos a la Consistencia (AP)

![](/img/bd_nuevas/ap.png)

#### Renunciamos a la Disponibilidad (CA)

![](/img/bd_nuevas/ca.png)

# 2. Sistema de Ficheros Distribuidos

## GFS y el origen del BigData

### Surgimiento del Big Data

Los primeros en enfrentarse al manejo de datos masivos fueron Google, Yahoo y Altavista  a finales de los 90s y principios de los 2000. 

Google fue el primero en resolver ambas cuestiones mediante dos papers que proponían modelos de almacenamiento y procesamiento distribuido que fueron presentados en 2003 y 2004, y lo denominaron como Google File System (GFS). 

### GFS

- GFS tiene la misma estructura que un sistema de ficheros que corre en un sistema operativo Linux.
- Tiene una jerarquía de padre-hijo. 
- Existen las mismas operaciones de Linux (teclear, abrir, cerrar, escribir, leer).
- Google añadió más comandos: append (a continuación de un fichero añadir más datos) y snapshot (capturas de un fichero en un momento dado para crear una copia de seguridad)

![](/img/bd_nuevas/gfs%20arquitectura.png)

#### Arquitectura 

Existe un sistema de master-esclavo: un solo servidor master y varios servidores esclavos llamados chunkservers. 

![](/img/bd_nuevas/GFS_arquitectura_2.png)

##### Rol del Máster
- El servidor máster guarda el árbol de archivos. Tiene el conocimiento de la jerarquía de los directorios.
- Todos los ficheros los divide en fragmentos llamados chunks de 64 MB. 
- El master tiene mapeado el fichero con el número fragmentos, sus ubicaciones y además las ubicaciones de sus réplicas en los chunkservers. 
- Aunque el master tiene información del árbol de archivos la tiene en una memoria temporal (no la persiste), periódicamente los chunkservers le comunican qué chunks almacenan ellos y así no saturan su disco duro. Mantiene un estado de todos los cambios que se van realizando por medio de un Operations Log. Este Operations Log es volcado en un Checkpoint.
- El master se comunica con los chunkservers por medio de un heartbeat para informar que "están vivos" u operativos. Además van a pasarle información de los fragmentos que tienen cada uno de ellos, el máster no tiene información permanente de esto, se fía de los informes de los chunkservers. 
- El master es un punto único de fallo. No podemos perderlo de ninguna manera porque solo hay uno y perderíamos el árbol de archivos. 
- Google habla de tener dos servidores máster, por si cae el servidor principal (shadow master)


##### Rol del Chunkserver
- Alojan los chunks, los fragmentos de los ficheros. No obstante, no tienen el conocimiento del fichero entero, solo del fragmento. 
- Para construir el fichero, deberemos recurrir a los metadatos del master donde tenemos la correspondencia con cada fichero. 

19/12/22

##### Lectura

![](/img/bd_nuevas/GFS_lectura.png)

1. Cuando un cliente quiere leer un fichero, se lo comunica al máster. 
2. El servidor máster le da el mapa de los fragmentos (el nombre de los chunks, *chunk handle*, y la ubicación que tienen). 
3. El cliente solicita directamente a los chunkservers los fragmentos del fichero que quiere, normalmente con aquellos que tienen las réplicas físicamente más cerca. 
4. El cliente recibe el fichero reducido (entero, desfragmentado).

Notas. La petición la guarda el cliente en caché para evitar que se sature el master ya que como es uno solo, queremos evitar que tenga la mínima carga posible para atender todas las solicitudes que le generen múltiples clientes en tiempos de respuesta cortos. 

##### Escritura

![](/img/bd_nuevas/gfs_escritura.png)

1. El cliente le pregunta al servidor máster dónde puede escribir. 
2. El master le responde la ubicación y el servidor primario donde se va a ubicar la copia original. 
3. A partir de ahí, el cliente envía los datos al nodo con la ubicación físicamente más cerca para obtener una menor latencia, no importando si ese nodo es el que va a alojar una réplica secundaria. 
4. Envía una solicitud de confirmación al nodo primario de la réplica. 
5. El chunkserver que tiene la réplica primaria solicita confirmación a servidores que alojan las réplicas secundarias. 
6. Servidores secundarios devuelven señal positiva, ACK. 
7. Servidor primario devuelve señal positiva al cliente, ACK. 

## HDFS y el origen de Hadoop 

### Democratización del Big Data 

#### No solo Google

Con el paso del tiempo, la cantidad de datos han explosionado en varias empresas, y tienen que lidiar tratar sus datos con soluciones parecidas a Google en los 2000. 

![](/img/bd_nuevas/no_solo_google.png)

#### Las 3Vs del Big Data 

![](/img/bd_nuevas/3vs.png)

#### Qué buscan las empresas

Las empresas buscan exactamente con el Big Dta lo mismo que buscaba Google en los 2000: 

1. Crecer en capacidad de almacenamiento y cómputo con recursos baratos que pudieran fallar y protegerse ante esos fallos. 
2. Trabajar con ficheros grandes. 
3. La mayoría de las lecturas de los ficheros son secuenciales. 
4. Que muchos usuarios puedan acceder concurrentemente a los datos. 
5. Primar el ancho de banda sobre la latencia. 

![](/img/bd_nuevas/que_buscan_las_empresas.png)

Es por ello que surge Hadoop.

### Surgimiento del Big Data

El origen de Hadoop comienza en el 2001 cuando Apache Lucene (un motor de búsqueda) pasó a formar parte de la Apache Software Foundation (creada en 1999). Utilizando Lucene, y dentro de Apache surge entonces de la mano de Doug Cutting y Mike Cafarella en 2002 un proyecto llamado Nutch. Nutch se trata de un robot web que es capaz de rastrear e indexar páginas Web.

En las primeras versiones de Cutting y Cafarella se dieron cuenta de que en un sistema centralizado con una sola máquina solo podían indexar un total de 100 millones de páginas y que, aunque la operativa se simplificaba contando con un único servidor, el coste de escalar verticalmente era elevado y además limitado. En ese momento para mejorar Nutch, sus autores echaron un vistazo a los papers publicados por Google sobre GFS y MapReduce. A partir del primero (GFS) crearon lo que se conoció como **NDFS (Nutch Distributed FileSystem).**.

En 2006 Doug Cutting pasó a formar parte de Yahoo llevándose con él a Nutch, dentro de Yahoo el proyecto Nutch se dividió dando lugar a dos partes bien diferenciadas: una parte de computación distribuida y una parte de motor de búsqueda. El nuevo proyecto surgido de la parte de computación pasó a denominarse Hadoop y NDFS evolucionó en HDFS (Hadoop Distributed File System)

![](/img/bd_nuevas/evolucion_hadoop.png)

### HDFS

#### Objetivos principales de HDFS

- **Tratar grandes cantidades de datos.**
- **Permitir fallos HW:** uno de los objetivos de Hadoop es poder detectar estos fallos y recuperarse de ellos lo más rápidamente posible. Uno de los objetivos de Hadoop es poder detectar estos fallos y recuperarse de ellos lo más rápidamente posible.
- **Tratamiento Batch.** HDFS se enfoca principalmente en el tratamiento Batch, priorizando el rendimiento a la baja latencia. 
- **Ficheros inmutables.** HDFS utiliza ficheros inmutables. Una vez que un fichero se crea, se escribe y se cierra, este no puede volver a ser modificado. Esto simplifica la coherencia de los datos y nos habilita a tener un gran rendimiento en el acceso a los datos.
- **Localidad del dato.** Cuando surge HDFS, surge con la premisa de que es más barato mover la computación que el dato. De este modo HDFS provee a las aplicaciones las interfaces necesarias para que el cómputo pueda correr en los mismos nodos en los que se encuentran los datos.
- **HW Commodity:** HDFS y Hadoop son proyectos OpenSource que están pensados para correr en HW convencional, barato y además permiten la creación de clústers sobre máquinas heterogéneas.

#### Arquitectura HDFS

HDFS posee una arquitectura maestro-esclavo que consiste en un único nodo máster denominado namenode que gestiona el espacio de nombres del sistema de ficheros y regula el acceso a los ficheros por parte de los clientes. Este namenode sería el equivalente al máster de GFS.

Por otro lado, tendríamos N datanodes, normalmente uno por nodo del clúster, que gestionan el almacenamiento de cada uno de los nodos. Los datanodes serían los equivalentes a los chunkservers de GFS.

Internamente los ficheros se dividen en uno o más bloques (chunks, en GFS) que son almacenados en los datanodes.

El namenode se encarga de las operaciones como abrir, cerrar y renombrar ficheros y directorios; también de mapear los bloques con los datanodes. Va a tener cargado en memoria (que no en disco) la correspondencia de los bloques con los datanodes (la ubicación de todas las réplicas). También tienen un FSImage (análogo al checkpoint para GFS) que es el estado del clúster en todo momento y en lugar de un Log de Operaciones va a tener un EditLog. Cuando el sistema se reinicie, el namenone va a actualizar el FSImage con los cambios declarados en el Editlog
 
Los datanodes, en cambio, alojan los bloques, sin tener información de los ficheros; se ocupan de resolver las peticiones de lectura y escritura hechas por los clientes; además son los encargados de gestionar los bloques (crearlos, eliminarlos y replicarlos) en función de las instrucciones del namenode.

La comunicación de los datanodes a los namenodes siempre es con latidos para dar señales de vida y para informar los bloques que alojan. A su vez, el namenode la va a dar instrucciones al datanode.

Las diferencias entre GFS y Hadoop son casi nulas, básicamente Hadoop es agnóstico al SO y GFS solo puede operar con Linux. 

![](/img/bd_nuevas/hadoop.png)

#### Alta Disponibilidad y Federación del NameNode 

1. Siendo el Namenode el Punto Único de Fallo, se ha implementado un Secondary Namenode. 

2. El Secondary Namenode solicita al NameNode el Edit Log. A partir de aquí el Secondary Namenode actualiza el FSImage, el NameNode lo ejectua pero solamente durante un reinicio. Este secondary namenode no solo nos proporciona un backup de los datos del namenode, sino que además nos realiza checkpoints periódicos, lo que evita que los EditLogs se vuelvan demasiado grandes.
3. En caso de pérdida del Namenode principal, el Namenode secundario tiene toda la información necesaria para sustituirlo. 

Aunque el secondary namenode nos proporciona un mecanismo de backup que evita el desastre (la pérdida total de acceso al sistema de ficheros), en caso de perder la información del namenode; el sistema de ficheros quedaría inaccesible 24/7 ya que el namenode sigue siendo un punto único de fallo y para promover el secondary namenode hay que hacerlo manualmente.

![](/img/bd_nuevas/secondary_namenode.png)


![](/img/bd_nuevas/cuestionario51.png)

![](/img/bd_nuevas/cuestionario52.png)

![](/img/bd_nuevas/cuestionario53.png)

![](/img/bd_nuevas/cuestionario54.png)

![](/img/bd_nuevas/cuestionario55.png)

![](/img/bd_nuevas/cuestionario56.png)

![](/img/bd_nuevas/cuestionario57.png)

![](/img/bd_nuevas/cuestionario58.png)

![](/img/bd_nuevas/cuestionario59.png)


Para ello se introduce la posibilidad de tener auténtica alta disponibilidad (HA) en el namenode, pudiendo tener dos nodos con una arquitectura activo-pasivo.

Uno de los objetivos principales de HadoopV2 es manejar esta situación.

##### HDFS HA - Journal Nodes

Esta es la solución que aplican muchas empresas para obtener una alta disponibilidad. 


![](/img/bd_nuevas/journalnode.png)

Vamos a tener dos namenodes: un namenode activo (que escribe) y un namenode pasivo (que lee). 

El namenode activo siempre escribe el EditLog por medio de un sistema de archivos compartidos (Journal Nodes).
El namenode pasivo siempre va a leer el EditLog. Este sistema de archivos compartidos se va a implementar con diferentes nodos, corren en el mismso servidor que los namenodes. Tienen que ser al menos 3 e impares para que en caso de una caída exista quórum en las escrituras para asegurar la consistencia. 

El número de journalnodes suele ser tres, aunque puede establecerse un número mayor impar, para permitir la tolerancia a fallos, sería paradójico que una solución que intenta evitar que exista un único punto de fallo en el namenode introdujera otro nuevo.

Como podemos ver en la figura, todos los datanodes envían la información (heartbeats y bloques) a ambos namenodes para que los dos estén actualizados y puedan asumir el papel activo en cualquier momento.

El namenode pasivo se configura con las mismas funciones que un secondary namenode.

Es necesario que exista un coordinador que controle la salud de ambos namenodes y establezca cuál es el activo en cada momento. Ese coordinador es Zookeeper.

##### HDFS HA - Zookeeper

![](/img/bd_nuevas/zookeeper.png)

Como podemos ver en la figura, cada namenode va a disponer de un agente llamado ZKFC (Zookeeper Failover Controler) que controle la salud de ese namenode y establezca una sesión con Zookeeper. En Zookeeper se implementa un candado (lock) que solo puede ser adquirido por uno de los namenodes. Cuando un namenode se encuentra “sano” intenta adquirir ese candado en el caso de que no esté asignado convirtiéndose así en el nodo activo. Para evitar el split-brain el número de nodos de zookeeper debe ser mayor que tres (y usualmente impar).

##### Federación

Además de la alta disponibilidad HadoopV2 introduce también novedades en cuanto a la escalabilidad. Como hemos visto, todo el mapeo ficheros-bloques se realiza en el namenode, por lo que un gran número de ficheros podría provocar que nos quedáramos sin capacidad o saturación en el namenode. Para evitar esto, la buena práctica es que no existan muchos bloques pequeños (menores de 128 MB). No obstante, para evitar este escenario, Hadoop introduce la capacidad de escalar en namenodes mediante la federación.

![](/img/bd_nuevas/namenode_escalabilidad.png)

Para lograr este objetivo, la federación de namenode utiliza múltiples espacios de nombres creando un pool de bloques en cada uno. Todos los espacios de nombres comparten todos los datanodes, por lo que los datanodes ubicaran en su almacenamiento bloques de todos los pools. Cada espacio de nombres se ocupa de un punto de montaje diferente, como podemos ver en la siguiente figura.

## Hadoop y su ecosistema

Hadoop es más que HDFS. 

![](/img/bd_nuevas/hadoop_universo.png)

## Introducción a Kubernetes

### ¿Qué son los contenedores?

- Estándar de paquetización software y dependencias. 
- Entorno de Ejecución completo: aplicación, dependencias, bibliotecas, archivos binarios y archivos de configuración necesarios para ejecutarlo, agrupados en un paquete. 

### Contenedores VS. Máquina Virtual

Los contenedores no tienen hipervisor ni SO. También tienen un peso comparativamente más ligero. 

![](/img/bd_nuevas/maquina_virtual_vs_contenedor.png)

### Componentes de una arquitectura de contenedores

- Engine: Docker daemon, lleva a cabo las tareas de construcción, ejecución y destrucción de los contenedores. La comunicación a través de un API REST. 
- Images: Plantilla que define instrucciones para la creación de los contenedores a través de un fichero denominado Dockerfile. Se puede construir desde cero o emlear imágenes creadas por otros. 
- Contenedor: Instancia ejecutable de una imagen. 
- Repositorios: Librerías de imágenes públicas (Duckerhub) o privadas (mismo o distinto servidor)


![](/img/bd_nuevas/docker.png)

### Qué es Kubernetes 

- Tecnología open-source para despliegue automático, escalado y gestión de clúster de contenedores y aplicaciones *containerizadas*
- Desarrollado por Google como su propio mecanismo de gestión de aplicaciones *containerizadas*. 

### Recursos básicos Kubernetes para BBDD

- POD: Unidad mínima de Kubernetes. 1 o varios contenedores. 1 dirección de red. 
- Servicio: Balanceador para agrupar pod con funcionalidad común y exponerlos al exterior. 
- Replicacion Controller/Replica Sets: Asegura que siempre haya X réplicas corriendo. 
- Deployment: Declaración de puesta en marcha de los objetos en K8s. Para aplicaciones sin estado. 
- Statefulset: Declaración de puesta en marcha de los objetos en K8s. Para aplicaciones con estado.
- Persistent Volume: Objeto de almacenamiento persistente. 
- Persistent Volume Claim: Solicitud de almacenamiento persistente por parte de la aplicación. 
- ConfigMap/Secret: Objetos de configuración. 
- Namespace: Tenant lógico para dividir recursos entre múltiples usuarios/casos de uso.  

### Arquitectura HDFS en K8s

![](/img/bd_nuevas/arquitectura_k8s.png)


Por qué vamos a usar Kubernetes?
1.Primero porque es algo que se usa mucho y es importante que sepamos usarlo. 
2. Al ser los pods bastante ligeros, el hecho de poder desplegar diferentes nodos nos va a permitir trabajar con varios nodos y pocos recursos. 

## Entorno A2

### Entorno AWS 

![](/img/bd_nuevas/awa.png)

9/01/2023

# Unidad 7. Bases de datos documentales


![](/img/bd_nuevas/fs_image.png)

![](/img/bd_nuevas/federacion.png)

![](/img/bd_nuevas/edit_log.png)

![](/img/bd_nuevas/datanodes.png)

![](/img/bd_nuevas/maestro_esclavo.png)

![](/img/bd_nuevas/consistencia_2.png)

El documento es el concepto principal: son ficheros XML, JSON que contiene información semiestructurada, elementos embebidos, etc. 

La BBDD documental más popular es mongoDB. 

![](/img/bd_nuevas/documentales_estructur.png)

### Tipos de datos

![](/img/bd_nuevas/mongodb.png)


## MongoDB - Clientes

Se puede acceder de 3 maneras. 

1. Mongo Shell. 
2. Interfaces Gráficas (Compass)
3. Drivers de diferentes lenguajes de programación. 

## Arquitectura


Un cliente se conecta a un único demonio o servidor y el cliente se conecta a la base de datos que se encuentra en el servidor único. 

![](/img/bd_nuevas/mongodb_arquitectura.png)

### Replication set 

![](/img/bd_nuevas/mongodb_arquitectura.png)

En MongoDB, la arquitectura es análoga al maestro-esclavo, con la diferencia que tanto las lecturas como las escrituras se van a ejecutar solamente desde el servidor maestro para asegurar la consistencia. 

Normalmente, se hacen 3 réplicas a los documentos, en donde habrá un nodo primario y el resto serán nodos secundarios. 

![](/img/bd_nuevas/mongodb_arquitectura_replicationset.png)

![](/img/bd_nuevas/mongodb_arquitectura_replicationset_2.png)

Aunque la lectura se va a hacer por defecto en el nodo primario, se puede configurar la preferencia de lectura a un nodo específica. 

El log de MongoDB se denomina oplog y es una colección APED que tiene un tamaño fijo que cuando llega a la capacidad máxima se reinicia. 

![](/img/bd_nuevas/mongodb_arquitectura_replicationset_3.png)

Existen algunas arquitecturas donde no es necesario tener 3 nodos. 

![](/img/bd_nuevas/mongodb_arquitectura_replicationset_4.png)

Tenemos un nodo que desempata la votación, pero no almacena nada.

Si se cayera un nodo primario, gracias a los heartbeats que existen, un nodo secundario realiza su candidatura como nodo primario, los demás nodos votan y se promueve este nodo como un nodo primario. Este sistema solo soporta la caída de un nodo, si tuvierasmos un sistema de 3 nodos y uno se cayera, ya no podríamos escribir y modificar. 


### Sharding-Distribución de los datos

Clases donde da tutorial de Mongo:
- 9/01, 16/01, 23/01


![](/img/bd_nuevas/mongo_sharding.png)

El sharding permite partir una colección en fragmentos (chunks). Por defecto están compuestos por 128MB. 
Los chunks son configurables entre 1MB y 1GB. 
Los chunks se guardan en shards (replica sets). 

Un *demonio* es un proceso que está corriendo en background.

![](/img/bd_nuevas/mongo_sharding_2.png)


Mongo también añade otro componente a la arquitectura: el configserver, que es un equivalente al namenode. Tiene toda la información de las conexiones que están distribuidas (los shards que existen) e información de ellos. 

El Config Server es un replica set. 

En MongoDB, el tamaño que tiene el config Server en comparación con una base de datos, necesitamos 10MB por cada 1TB. 

Dentro de una base de datos de Mongo, podemos tener colecciones distribuidas y colecciones que no están distribuidas. El config Server solo almacenaría info de las colecciones distribuidas.

![](/img/bd_nuevas/mongodb_distribuci%C3%B3n.png)


### Sharding - arquitectura

Mongo sirve como un router para llevarnos al shard adecuado. 

![](/img/bd_nuevas/mongodb_arquitectura.png)

### Clúster de ejemplo

![](/img/bd_nuevas/mongo_db_cluster.png)

23/01/23
Práctica de MongoDB

MongoDB se diferencia con HDFS y Cassandra, en que la configuración se guarda en la BD.

En el tema 2, decíamos que las BBDD orientadas a agregados que solo se podían acceder a una única perspectiva. A primera vista, MongoDB desmentía esto, pero una vez distribuimos la BBDD en un clúster, siempre tenemos que acceder por la clave de partición. 

Así aseguramos acceder a un servidor o a unos cuantos servidores. 

Qué pasa cuando tenemos un id-particionado con muchos datos (un hotspot)? Que la distribución de los datos ya no es homogénea ya que el id de partición debe ir siempre en el mismo servidor. Soluciones para contrarrestar esto es pensar inteligentemente en un id de partición o generar una partición compuesta (p. ej. por fecha).

### Modelado de datos

### Consideraciones básicas

1. Normalizar vs. Desnormalizar. Aunque lo normal es desnormalizar la información para acceder a toda la información con un solo acceso, en ciertos casos es necesario normalizar commo en las fechas. 
2. Esquema flexible. Tenemos que tener cuidado que en cuanto más flexible sea la estructura más complicado será el desarrrollo de la aplicación. 
3. Elección de shard key. El shard-key afecta directamente los cuellos de botella con hotspots, que accedamos a todos los servidores, la escalabilidad. 
4. 

### Sharding - Distribución de los datos 

- Por rangos del id. Los beneficios es de que si los rangos están igualados, la lectura será secuencial en disco. No obstante, lo mejor es particionar por hash. 
- Hash. Asegura la distribución homogénea de los datos entre todos los chunks. Además, MongoDB crea por defecto dos chunks por cada Replica Set que tengamos (cuando es por rangos se crea un único chunk). 

![](/img/bd_nuevas/mongodb_chunks.png)

- Por zonas. Si tenemos RS en diferentes zonas geográficas, podemos generar zonas discriminando por la ubicación geográfica. 

![](/img/bd_nuevas/mongodb_chunks-2.png)

### Soluciones comerciales

MongoDB es open-source, pero ¿por qué hace falta una solución empresarial ? 

Brindan soporte proactivo y oficial. También proporcionan funciones extras como cursos, consultoría, herramientas de automatización, seguridad. Van a simplificar los procesos para dar un servicio adecuado. 

![](/img/bd_nuevas/mongodb_enterpise%20.png)

#### MongoDB Atlas

Es un servicio en la nube. MongoDB as a Service.

![](/img/bd_nuevas/cuestionario71.png)
![](/img/bd_nuevas/cuestionario72.png)
![](/img/bd_nuevas/cuestionario73.png)
![](/img/bd_nuevas/cuestionario74.png)
![](/img/bd_nuevas/cuestionario75.png)
![](/img/bd_nuevas/cuestionario76.png)
![](/img/bd_nuevas/cuestionario77.png)
![](/img/bd_nuevas/cuestionario78.png)


# Unidad 4. Bases de datos clave-valor y columna ancha

![](/img/bd_nuevas/cassandra_1.png)

La columna ancha se puede ver como una BBDD de clave-valor de dos dimensiones. Usando la terminología de BigTable tenemos una clave de fila y un column family. En el column family tenemos valores. Se puede ver que tenemos dos clave diferentes. 


![](/img/bd_nuevas/cassandra_2.png)

Se puede ver como una especie de tabla no estructurada (registros faltantes, diferente número de columnas, diferente orden). 

![](/img/bd_nuevas/cassandra_3.png)


## Cassandra

Es una base de datos escrita en Java que es una combinación de DynamoDB (clave-valor) y BigTable (columna ancha). Cassandra intenta tomar lo mejor de los dos mundos. 

A diferencia de MongoDB, Cassandra está pensada 100% trabajarla de forma distribuida. En MongoDB las colecciones pueden estar o no estar distribuidas. 

### Categorización original 

Hasta hace poco la siguiente imagen era la forma de categorizar de Cassandra. Recientemente Cassandra cambió la nomenclatura para parecerse a SQL. Debido a que se utilizan diferentes versiones de Cassandra, es útil saber cómo era la estructura original de Cassandra. 

![](/img/bd_nuevas/cassandra_4.png)

Casi siempre vamos a tener que acceder a Cassandra por rowkeys. 

### Tipos de datos

![](/img/bd_nuevas/cassandra_5.png)


### Formas de acceder a Cassandra

- CQL Shell
- Drivers. No existen tantos como en MongoDB, pero está java, C, Python. 

No tenemos ninguna interfaz gráfica, por la simplicidad que se realizan con CQL. 

## Arquitectura 

![](/img/bd_nuevas/cassandra_7.png)

No tiene sentido tener un único nodo, siempre vamos a pensar que tenemos una arquitectura distribuida. Incluso si tenemos un solo nodo, Cassandra va a pensar que tenemos una arquitectura distribuida, el sistema le va a asignar una clave de partición. Esa clave va a estar preparada para escalar

Cassandra le va a aplicar a todas las claves un hash, el mismo de MongoDB, y así va a segmentar los datos para distribuirlos en los diferentes nodos. 

Cassandra no va tener configservers, namenodes, nodos primarios ni nada, trabaja con peer-to-peer con un protocolo que se llama gossip en donde todos los nodos se están comunicando constantemente. De esta manera, van a tener información sobre el resto de nodos. Todos los nodos van a saber los rangos que tienen cada uno. Los clientes van a poder conectarse a cualquier nodo y va a hacer la función de coordinador. 


### Sharding- particionador

Un elemento clave es el particionador que devuelve un hash, que indica en qué punto del anillo estamos.

Por ejemplo, si tengo una clave primaria: Repsol, el particionador va a calcular un token con una función hash que se llama Murmur3, en un rango del 0 al 99. (en la realidad Cassandra particiona con un rango de -2>63 - 2>63).

En función de aplicar el particionador a la partion key, lo que vamos a hacer es asignarle un nodo en función del rango que tenga (los nodos se van a distribuir los partition key en función del rango que tenga cada uno). 

Volviendo con el ejemplo de Repsol, en el caso que tengamos un nodo este es el escenario: 

![](/img/bd_nuevas/cassandra_10.png). 

En el caso de agregar un segundo nodo, los rangos de la clave de partición se dividen en dos: 

![](/img/bd_nuevas/cassandra_12.png)

En el caso de agregar el tercer nodo, segmentamos el rango de la clave de partición en 3 nodos: 

![](/img/bd_nuevas/cassandra_11.png)


Cualquier nodo va a jugar el papel de coordinador, ya que además de conocer los rangos de los que son responsables, los nodos también saben los rangos que custiodan los otros nodos. Esto tiene algunas implicaciones como que no va a haber ningún nodo dedicado a servir como namenode, coordinador, etc; que el cliente se va a poder conectar a cualquier nodo para leer/escribir. 


### Replicación

MongoDB crea un anillo y a través del particionador le envía la información a un nodo o a otro. 

![](/img/bd_nuevas/cassandra_8.png)

Se intenta poner las réplicas en los nodos adyacentes al que aloja la copia original. Esto se consigue por medio de un keyspace. 

Si especificamos varios racks, Cassandra va a colocar las copias en diferentes racks.
Si tenemos diferentes diferentes datacenters, va a crear anillos en cada uno. 

El snitch nos indica la topología: los racks y datacenters que tiene nuestro clúster, de manera estática con ficheros de configuración o de manera dinámica p. ej. en cloud por medio de la IP sabe en qué región/rack estamos desplegando. 


### Escritura 

Cassandra está bastante optimizada para escritura, porque se escribe en memoria. 

![](/img/bd_nuevas/cassandra_9.png)

Cuando escribimos un dato tenemos un número de partición (hash). Va a escribir en memoria en una tabla denominada Memtable, y en disco va a aparecer como un log de transacciones, que es un fichero de solo Append.

Cuando se llena la memoria RAM o tras un periodo determinado se ejecuta un "flush" o volcado de memoria en una estructura en disco denominado SSTable, que es inmutable. Esto tiene algunas implicaciones: estamos escibiendo sin ver lo que estamos grabando en disco, vamos a escribir a alta velocidad, no vamos a poder verificar si un dato ya existe durante un *update* o un *insert*.
        
### Escritura - Actualizaciones y borrados

Si en el Update, el registro no existe, el sistema lo va a crear. Y si existe, lo va a actualizar. 
Similar es el procedimiento con el borrado (no vamos a comprobar si lo estamos borrando), donde le genera un Tombstone (una marca de que queremos eliminarlo como una x).

30/01/23

### Escrituras Memtable y SSTables

Cuando la *Memtable* se llena o en un periodo de tiempo, se ejecuta un flush que crea un SSTable. Conseguimos una lista de SSTables

![](/img/bd_nuevas/Escrituras_mmtables_SStables.png)

Esta es la estructura de una SS Table: 

 - Primary key, compuesta por dos partes.
    - Partition key (obligatorio.)
    - Columnas de clustering (permite ordenar los registros dentro de la partición, opcional).


### Lectura 

Primero el cliente va a ir a caché para ver si está su consulta ahí para no tener que ir a la BBDD. Si no está en caché, va a comprobar si la consulta está ahí (eso aplica para las consultas frecuentes o hotspots), luego irá a Memtables. Si no está ahí, entonces deberá recorrer SSTables en disco. Ahí nos encontraremos con las SSTables que se han ido escribiendo, y se van a tener que recorrer una a una. 

![](/img/bd_nuevas/cassandra_13.png)

Para ser más eficientes, la estructura de las SSTable tienen la siguiente estructura. 

-**Bloom filter:** Indica si es probable que un fichero esté en la SSTable o no. 
- **Caché de claves:** Las claves de partición que más frecuentemente se acceden y su ubicación dentro de la SSTable. 
- **Partition summary:** Muestreo de la SSTable, que indica la ubicación de esa muestra.
- **En disco se encuentra el Partition Index**, que es un índice, e indice el offset exacto en el que se encuentra una clave. 

![](/img/bd_nuevas/cassandra15.png)

Lo ideal es no tener más de 4 SSTables. Cassandra resuelve el número creciente de SSTables por medio de compactaciones, cuyo objetivo es reducir el número de SSTables. A partir de dos SSTables, las fusiona y las convierte en una sola. 

Por ejemplo, Cuando aparece una segunda Tabla, en cada celda Cassandra también agrega un timestamp, que es la última vez que un registro se escribió. 


![](/img/bd_nuevas/cassandra_16.png)

### Compactación - En una partición 

El mecanismo para contrarrestar la ralentización de lecturas debido a un alto volumen de SSTables, es la compactación, que es una agrupación/fusión de SSTables, con el objetivo de reducir la cantidad.

Un ejemplo de cómo funciona esto es el siguiente: 


Tenemos una partición 1 que está en dos SSTables y queremos fusionarlas. Tenemos dos registros que tienen diferentes valores, además Cassandra imprime un timestamp que indica la última vez que el registro se escribió. 


El timestamp de Sofía tiene un timestamp mayor que el de Juan (ya que significa más reciente), por lo tanto el registro que se queda es "Sofía". 

En el caso de la fila 3, hemos borrado un registro para la SSTable 2 (como vimos anteriormente el espacio no se elimina porque le generamos una marca o un tombstone), el grace_period se ha pasado. Como consecuencia, el registro correspondiente a Ana, no se incluiría en la compactación. 

![](/img/bd_nuevas/cassandra_17.png)

### Compactación completa 

A la hora de hacer la compactación, vamos a ir cogiendo diferentes particiones de las SSTables y las vamos a escribir.

En el caso particular de la nueva partición 9 (ver imagen abajo), puede que la compactación se vuelva más corta que sus antecesoras,debido a que estas tenían registros borrados que ocupan espacio. 

**¿Cuál es la diferencia con la sección anterior?** 

![](/img/bd_nuevas/cassandra_19.png)

### Clúster ejemplo desplegado 

Vamos a desplegar un clúster con esta estructura 

![](/img/bd_nuevas/cassandra_18.png)

- Nodetool status : ver el estatus de nuestros nodos. 
    - El número de token son los rangos que cada nodo va a tener. 
    - Cassandra no da un rango, da 16 rangos por defecto. 
    - La columna Owns indica la ocupación relativa de archivos
- Nodetool describecluster
    - Aquí podemos ver el snitch 
    - Podemos ver el particionador (por defecto es Murmur3)
    - Nos dice el número de nodos
    - Cuántos Data centers tenemos 
    - Keyspaces
- nodetool info: extraemos información propia del nodo
    - nodetool info -T: nos indica lso rangos con detalle de cuáles son. 
- nodetool gossip info: Tenemos información de los Ips de los diferentes nodos, racks y tokens que se van mandando entre nodos para que siempre sepan donde está ubicado cada dato. 
- nodetool ring: vemos el anillo completo
    - Se fragmenta por los Data Centers, y cada nodo aparece 16 veces, indica qué rango tiene y qué cantidad de datos tiene. 

#### Para entrar a la consola de Cassandra: 

- cqlsh: entrar a Casandra
-  CREATE KEYSPACE <bbddng WITH replicacion = {'class':'NetworkTopologyStrategy','DC1':3,'DC2':1}>; : Crear un kesypace
- nodetool describering <nombre, en este caso bbddng>: información de todas las réplicas (cuáles son los documentos, en qué rack están y en qué Data Center)
- use bbdng: para usar el bbdng
- // Crea una tabla con un comando bastante largo, que me imagino que nos va a compartir, que se llama Spacecraft_journey_catalog
- Para que dos columnas sean la clave de partición tenemos que poner doble columnas, p. ej: "PRIMARY KEY((columna_1, columna_2));
- Vamos a poblar nuestra bbdd. Para ello en la consola de Cassandra referimos un archivo que tiene todos los registros clave-valor. 
    - cqlsh 
    - use bbddng; 
    - SOURCE /<ruta del archivo/archivo>; //con esto se debería cargar todo
    - SELECT * FROM <nombre_archivo> LIMIT 2;

![](/img/bd_nuevas/cassandra_20.png)

Como podemos ver en la imagen de arriba (ver declaración de abajo), tuvimos un error a la hora de insertar el valor (ojo que utlizamos UPDATE y no INSERT), porque solo colocamos el "Journey_ID" como partition key y se nos olvidó que el primary key está compuesta por un *Partition Key" y un "Column Key", por lo que obligatoriamente debemos agregar dos campos como mínimo. 

Ahora haremos una sobreescritura:

![](/img/bd_nuevas/cassandra_21.png)

Con la declaración INSERT, nos pasa lo mismo que con UPDATE. Debemos agregar las dos claves que componen la clave primaria o nos devolverá un error. 

Aunque existen inserciones masivas (batch), no optimizan Cassandra, por lo que no lo vamos a ver. 

Vamos a entrar a otro nodo y vamos a ver cómo funciona la consistencia. 

![](/img/bd_nuevas/cassandra_22.png)

Vamos a crear un Keyspace que solo se replica en un datacenter. 

![](/img/bd_nuevas/cassandra_23.png)

Cassandra nos permite jugar con varios niveles de conssitencia de dos, vamos a tener una consistencia fuerte y vamos a leer la última lectura, pero en caso de caída no vamos a tener disponibilidad a los ficheros. 
No obstante, si tenemos una concistencia de nivel uno, vamos a tener siempre garantizada la disponibilidad de los datos aunque no sean los más actualizados. 

![](/img/bd_nuevas/cassandra_24.png)

Cassandra está optimizada para ofrecer un sistema donde prime la disponibilidad sobre la consistencia. 

Por defecto Cassandra tiene hasta 4 SSTables y después hace MemTables. 

#### Agregaciones

![](/img/bd_nuevas/cassandra_25.png)

### Anti-patterns

Evitar en la medida de lo posible cuando trabajemos en Cassandra. 

- Full scans: Esto ralentiza el sistema porque implica recorrer todos los servidores. 
- Leer antes de escribir. No es una buena práctica aunque Cassandra te dé la opción. 
- Allow Filtering: Te permite lanzar cualquier query a Cassandra. 
- Abusar de índices Secundarios
- Abusar de las colecciones no inmutables o no Frozen. 
- No tener en cuenta los Deletes, cuando borramos aumentamos los SSTables, es mejor borrar una partición por completo .
- Aumentar el timeout del cliente. 

### Soluciones comerciales 

![](/img/bd_nuevas/cassandra_26.png)

Hay una empresa detrás que es DataStax, que ofrece 

- Herramientas de gestión
- Funciones avanzadas de memoria
- Analíticas con Spark 
- Monitorización más visual
- Atención al cliente y apoyo técnico. 


Cassandra tiene la escalabilidad más lineal que MongoDB, pero a cambio de una simplicidad máxima. 

## Astra DB. Cassandra as a Service

Es análoga a MongoDB Compass. 

![](/img/bd_nuevas/cassandra_27.png)


![](/img/bd_nuevas/cuestionario81.png)

La respuesta correcta es peer-to-peer. 

![](/img/bd_nuevas/cuestionario82.png)

![](/img/bd_nuevas/cuestionario83.png)

![](/img/bd_nuevas/cuestionario84.png)
![](/img/bd_nuevas/cuestionario85.png)
![](/img/bd_nuevas/cuestionario86.png)
![](/img/bd_nuevas/cuestionario87.png)

Esto es porque con la clave secundaria va a acceder a todos los servidores y esto sería ineficiente. 

![](/img/bd_nuevas/cuestionario88.png)


# Motores de Búsqueda 

![](/img/bd_nuevas/motores_busqueda_2.png)

Nos permite funcionalidades más allá de una BBDD convencional. Podemos hacer consultas más complejas de las que haríamos en otra BBDD. 

Lo que pretendemos con búsquedas de texto libre es que podamos hacer consultas que no han sido categorizadas previamente. 

Los primeros resultados son los que más se encajan dentro de la consulta que estoy buscando. 

#### De Lucene a Elasticsearch

![](/img/bd_nuevas/motores_busqueda_3.png)

Lucene es una librería Java, no es una base de datos ni un motor distribuido, que nos permite indexar información y luego realizar búsquedas sobre esa información. Se usa en LinkedIn, Netflix, etc. No obstante, es complicada de utlizar, que requiere programación. 

Elasticsearch utiliza Lucene pero nos proporciona una gran capa de abstracción y actúa commo una BBDD, no solo como una librería. 

#### You know, for Search 

Cuando clasifica la información, Elasticsearch indexa los archivos. 

11/02/23



### Elasticsearch - Clasificación de la información 

Almacena la información en forma de documentos (en formato JSON) como si de una BBDD documental se tratara; sin embargo, no solo almacena esta información, sino que además indexa por defecto todos los campos de cada documento con el objetivo de que podamos realizar búsquedas sobre el mismo.

La clasificación que se hace es que la información se almacena en índices. Comparándolo con la analogía en el modelo relacional, es lo equivalente a una tabla o a una conexión en MongoDB. 

Por defecto todos los campos se indexan.

#### Diferencias con BBDD documentales.
- Toda la información que va en un documento se indexa, independientemente del tipo de campo. 
- La información está esquematizada. Un índice tiene algo que se denomina mapping y define el esquema de los datos (todos los datos en un campo deben ser del mismo tipo). 

Tenemos un campo ID que si no lo asignamos, el sistema lo va a asignar por defecto. 

![](/img/bd_nuevas/elasticsearch.png)

#### Index vs. Index vs. Index

1. **Índice**: Colección de documentos, al igual que en otras BBDD documentales se agrupan en colecciones. 
2. **Indexar**: Insertar un documento. Cada campo es indexado. 
3. **Shard**: Índice en Lucene. 

En Elasticsearch no tenemos diferenciación por bases de datos, esquemas o keyspace, por lo que directamente accedemos a los índices.

### Estructura de los índices

1. Configuración/Settings
2. Mappings 
    - Es definir la estructura de los documentos almacenados, o parecido a definir las columnas en una tabla. La diferencia es que un mapping es dinámico. El índice va a determinar automáticamente el mapping en base a una serie de reglas que determinemos. 
3. Alias
    - Sirve para acceder a la totalidad del índice o a un subconjunto de los documentos de este.Es análogo a las vistas en las bases de datos relacionales. 

Todo esto se puede definir en un "index template" para replicar la estructura en diferentes bases de datos. 

### Tipos de datos 

![](/img/bd_nuevas/elasticsearch_2.png)

### Elastic Stack 

![](/img/bd_nuevas/elasticsearch_3.png)


#### Casos de uso.

![](/img/bd_nuevas/elasticsearch_4.png)

## Arquitectura

Los nodos principales son los nodos master y nodos de datos. 

- Nodos máster: Mantienen metadatos del clúster (cluster-state) y aunque tenemos varios, tenemos uno que va a ser el nodo master activo. 
- Nodos de datos. Guardan la información.

Existen otros roles como el rol de coordinador (recibe las peticiones), ml, etc. Está configurado por defecto en todos los coordinadores. 


![](/img/bd_nuevas/elasticsearch_5.png)


### Sharding 

No hay que confundir shard con lo visto en MongoDB. Es equivalente a un chunk o bloque. El número de chard se define a nivel índice y a priori no se puede modificar. 

![](/img/bd_nuevas/elastic_search_6.png)

### Cluster - state 

![](/img/bd_nuevas/elasticsearch_7.png)

Todos los nodos tienen una copia del cluster-state pero solo el nodo master activo tiene la capacidad de modificarlo. 

### Réplicas 


![](/img/bd_nuevas/elasticsearch_8.png)

Elasticsearch sigue un modelo de maestro-esclavo pero la replicación es síncrona. El ACK, la confirmación al cliente, no se va a devolver hasta que la información esté replicada. Así se protege Elasticsearch de no dejar tareas de escritura/lectura pendientes. 


Para cada shard vamos a tener un número de réplicas definido a nivel de índice. 
Por cada grupo de réplicas va a existir un shard definido como primario, y es ahí donde se van a realizar las escrituras (como pasan en los modelos de replicación m-e), pero la lectura se va a poder ejecutar en cualquier nodo. 

## Análisis de texto 


Esta es una de las grandes fortalezas de los motores de búsqueda. 

Elasticsearch hace uso de los índices invertidos. 

> Índice invertido: Va a extraer diferentes térmminos o tokens que tenemos en la colección de documentos. Y nos va a decir dónde aparece un término para cada documento. 

![](/img/bd_nuevas/elasticsearch_9.png)

1. **Filtrado de caracteres**: Eliminación de caracteres especiales (p. ej. estamos indexando páginas web y nos encontramos muchas etiquetas). Esto se elimina. Podemos eliminar números, sustituir el "&" por una "y". 
2. **Tokenizar**: Partir el doucmento en tokens. Diivide por un delimitador de espacios (espacios, guion, coma).
3. **Token filter**: Una vez extraido el token, permite transformar la info, agregar sinónimos (p. ej. tratar "rápido" y "veloz" de la misma forma). 

Cada vez que realizamos una búsqueda, Elasticsearch va a aplicar todo el proceso anterior para commpatibilizarlo con las reglas de análisis. 

![](/img/bd_nuevas/elasticsearch_10.png)

## Soluciones empresariales 

Aunque es open-source, tenemos una empresa que brinda soporte técnico. Tenemos otras funcionalidades añadidas:
- Seguridad, que nos mejoran la autenticación y para acceder a ciertos indices en función de los roles. 
- Machine Learning
- Detectar anomalías
- Características especiales de mapas
- Permite replicar entre clústers. 

### Elastic as a Service

Como en Cassandra y Mongo, existe Elastic as a Service. No es como Astra y Atlas que te registres y accedas a un clúster, pero es algo que despliegas y gestionas. Se puede desplegar en las principales Clouds, y en servidores propios. 

Esta solución permite desplegar de forma sencilla 

## Parte práctica 

``` bash
 kubectl exec -it <nombre del nodo> /bin/bash/ #esto es para entrar al nodo, cualquiera hace de coordinador. 
 curl localhost:9200 #este es el puerto por defecto de Elasticsearch. Curl nos info del nodo y del clúster, la versión de Lucene, etc. 
curl localhost:9200/_cluster/health #salud del clúster 
curl localhost:9200/_cluster/health?pretty #nos da lo mismo de arriba pero mejor estructurado
curl -XPUT localhost:9200/prueba #crea un índice 

 ```

Kubana tiene un DevTools. 

![](/img/bd_nuevas/dev_tools_elasticsearch.png)


## Cuestionario 

![](/img/bd_nuevas/elasticsearch_10.png)
![](/img/bd_nuevas/elasticsearch_11.png)
![](/img/bd_nuevas/elasticsearch_12.png)
![](/img/bd_nuevas/elasticsearch_13.png)
![](/img/bd_nuevas/elasticsearch_14.png)
![](/img/bd_nuevas/elasticsearch_15.png)
![](/img/bd_nuevas/elasticsearch_16.png)
![](/img/bd_nuevas/elasticsearch_17.png)
![](/img/bd_nuevas/elasticsearch_18.png)


# Sistemas de coles


La idea de un sistema de colas es desacoplar el sistema de servicio. 

![](/img/bd_nuevas/colas.png)

El servicio puede ir consumiendo a su ritmo sin saturarse porque la cola atiende las peticiones de los clientes. A nivel de cliente, tenemos una alta disponibilidad.

![](/img/bd_nuevas/colas_2.png)

## Limitaciones del sistema de colas

Cuando tenemos diferentes servicios que necesitamos el mismo contenido. 


![](/img/bd_nuevas/colas_3.png)
![](/img/bd_nuevas/colas_4.png)

![](/img/bd_nuevas/colas_3.png)

![](/img/bd_nuevas/colas_4.png)


## Apache Kafka - Introducción 

![](/img/bd_nuevas/colas_5.png)




![](/img/bd_nuevas/colas_6.png)

![](/img/bd_nuevas/colas_7.png)



