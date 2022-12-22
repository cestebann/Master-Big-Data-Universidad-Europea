
# Índice

- Unidad 0. Objetivos del curso
    - Competencias específicas
    - Resultados del aprendizaje
- Unidad 1. Sistemas altamente distribuidos
    - Los sistemas distribuidos en el mundo Big Data
    - Introducción a los sistemas distribuidos
    - Paradigma de programación paralela
    - Tolerancia a fallos en sistemas distribuidos
- Unidad 2. Sistemas cloud y virtualización de servicios
    - Computación y almacenamiento en la nube
    - Consolidación de servicios
    - Amazon AWS
    - Google Web Services
- Unidad 3. Hadoop como sistema de cómputo en plataformas Big Data
    - Apache Hadoop
    - Hadoop Distributed File System
    - Arquitectura de cómputo de Hadoop.
    - Ejecución de aplicaciones en Apache Hadoop.
- Unidad 4. Programación en Scala
    - Introducción al lenguaje Scala
    - Estructuras de control y definición de funciones
    - Listas y contenedores
    - Programación funcional
- Unidad 5. Computación distribuida con Apache Spark
    - Introducción a Apache Spark
    - Programación de aplicaciones con Apache Spark
    - Acceso a fuentes de datos con Apache Spark
    - Gestión de trabajos Spark con Apache YARN
- Unidad 6. Apache Spark avanzado
    - Spark Streaming
    - Ingestión de datos de Twitter mediante Apache Streaming
    - Aprendizaje automático con Mllib
    - Despliegue de aplicaciones con Maven y SBT

# Unidad 0. Objetivos del curso

## Competencias específicas:
- Aplicar las bases teórico-prácticas necesarias sobre Tecnologías de la Información y Comunicaciones de interés para el desarrollo e implantación de servicios de análisis y extracción de modelos a partir de los datos en infraestructuras de altas prestaciones.
- Diseñar, implantar, y administrar redes e infraestructuras físicas para el tratamiento de
grandes volúmenes de datos distribuidos.
- Diseñar y ejecutar un proceso completo de descubrimiento de conocimiento, incluyendo las
fases de almacenamiento, procesamiento y visualización de los datos.
- Aplicar las bases técnicas del funcionamiento de plataformas cloud computing y virtualizadas.

## Resultados de aprendizaje:
- Aplicar las bases técnicas y funcionales de sistemas distribuidos de altas prestaciones
- Desarrollar algoritmos y usar de tecnologías para el acceso a bases de datos de nueva generación.
- Planificar e integrar bases de datos de nueva generación en sistemas distribuidos.

# 1. Sistemas altamente distribuidos

## Los sistemas distribuidos en el mundo del Big Data

El modelo de programación en Big Data consiste en: 

1. La recolección de una gran cantidad de información a través distintos medios. 
2. Aplicar el conocimiento necesario para transformar y analizar dicha información. El analista de datos es clave porque une conocimiento + datos. 
3. Todo este proceso debe resultar en valor

La aproximación basada en Big Data abordará la simplificación de la programación, de tal forma, que no tengamos que preocuparnos por el despliegue de nuestros algoritmos distribuidos, inicialmente con un despliegue y configuración complejo.

![](img/computacion/5vs.png)

La siguiente figura muestra un flujo de trabajo típico de las aplicaciones Big Data

![](img/computacion/5vs.png)

A la hora de programar aplicaciones basadas en Big Data, tendremos que afrontar dos grandes retos: el rendimiento y la complejidad.

Por un lado, deberemos ser capaces de desarrollar soluciones que escalen con el tamaño del volumen de datos a procesar. El rendimiento lo conseguiremos a través de sistemas distribuidos y con la participación de múltiples computadoras.

Conocer la ubicación de los datos será fundamental. Usar este nuevo modelo implicará que tendremos que llevar el cómputo a los datos y no al contrario, como se ha venido haciendo hasta ahora.

## Introducción a los sistemas distribuidos

A día de hoy, los sistemas distribuidos son una parte fundamental de cualquier infraestructura computacional. Desde teléfonos inteligentes a los grandes sistemas de cómputo, los sistemas deben estar interconectados para llevar a cabo acciones complejas.

En este tema se abordarán **cuáles son los factores necesarios para el diseño de un sistema altamente conectado y eficiente.** Todos los sistemas existentes de procesamiento masivo de datos están basados en sistemas distribuidos, desde Apache Hadoop a Apache Spark. Por lo tanto, conocer el funcionamiento de los sistemas distribuidos es un factor clave para entender el movimiento de datos y la computación masivamente distribuida.

### Inicio de los sistemas distribuidos 

La era de la informática moderna comenzó a partir de 1945. Hasta 1985, las computadoras eran grandes y caras, además por falta de conectarlas entre sí, actuaban de manera independiente. Sin embargo, dos factores tecnológicos cambiaron esta situación: 

- **Microprocesadores.** Con las CPUs multinúcleo, nos enfrentamos al reto de desarrollar programas para explotar el paralelismo. 
- **Redes informáticas de alta velocidad.** 
    - LAN (Local Area Networks). Permiten que varios dispositivos en una casa, una oficina o un edificio estén conectados. 
    - WAN (Wide Area Networks). Cientos de millones dispositivos conectados globalmente a velocidades del orden de cientos de millones bps. 

Paralelamente a estos factores, se ha ido desarrollando la **miniaturización** de los sistemas informáticos, siendo el resultado más deslumbrante el *smartphone*. 

Como consecuencia, no sólo es fácil sino también factible construir un sistema distribuido, que consiste en una red de computadoras dispersas geográficamente. El tamaño puede ser de un puñado a millones de nodos y la red de interconexión puede ser cableada, inalámbrica o un híbrido. 

### Definición 

> “A collection of independent computers that appear to the users of the system as a single computer.” - Tanenbaum 

> “A system in which hardware or software components located at networked computers communicate and coordinate their actions only by message passing.” - Coulouris

Los sistemas distribuidos están commpuestos por los siguientes elementos: 
- **Programa**: Conjunto de instrucciones
- **Proceso**: Secuencia de ejecución.
- **Datos**: Información ejecutada por el programa. 
-**Componente**:Elemento HW o SW que soporta la ejecución sistema.
-**Red de computadoras**: Un conjunto de computadores conectados por una red de interconexión.
-**Protocolo**: Un conjunto de reglas e instrucciones que gobiernan la comunicación en un sistema distribuido, es decir, el intercambio de mensajes.
-**Middleware**: Software que soporta la ejecución de aplicaciones distribuidas.

#### Ventajas 
- Compartir recursos (HW, SW, datos)
- Ofrecer una buena relación coste-rendimiento
- Aumentar la capacidad de crecimiento.
- Ofrecen una solución para la tolerancia a fallos, disponibilidad, replicación y escalabilidad. 
- En sistemas de gran escala, son un excelente modelo para la distribución de carga de trabajo
- Es capaz de ofrecer servicios a múltiples clientes de manera simultánea. 

### Sistemas distribuidos y middlewares

> El middleware actúa como un puente entre tecnologías, herramientas y bases de datos diversas para que pueda integrarlas sin dificultad en un único sistema. - AWS 

Los sistemas distribuidos se encargan para tener una capa separada de software para facilitar el uso de aplicaciones compartidas

![](/img/computacion/middleware.png)

Las funciones de un middleware son: 
- Permitir que los componentes, procesos o aplicaciones intercambien información. 
- Ocultar el carácter "distribuido" de los nodos y la heterogeneidad de los componentes. 
- Ofrecer interfaces de alto nivel de estándar y uniformes para el desarollo de apps. 
- Ofrecer servicios comunes para facilitar la comunicación entre aplicaciones. 

### Diseño de sistemas distribuidos

Para construir un sistema distribuido exitoso, es necesario cumplir los siguientes criterios: 

1. Un sistema distribuido debe hacer que los recursos sean fácilmente **accesibles**.
2. El sistema distribuido en **red** debe ser imperceptible para el usuario final, este debe pensar que esta tratando con una única computadora.
3. Debe estar **abierto**.
4. Debe ser **escalable**.

Aspectos a tener en cuenta los aspectos de diseño: 
- Heterogeneidad: Contemplar diferentes HW, SW, lenguajes de programación, velocidad, etc.
- Extensibilidad: Abierto a nuevos estándares, aplicaciones, tecnologías.
- Escalabilidad: Es escalable si su capacidad de procesamiento puede crecer al añadir más usuarios, aumenta el rendimiento al aumentar el número de nodos, el tiempo de respuesta no aumenta y la fiabilidad no se degrada.
- Seguridad: Confidencialidad, integridad, autenticación.
- Tolerancia a fallos y disponiblidad: Al estar compuesto por varios elementos, naturalmente es más propenso a errores por su gran tamaño. Un sistema es tolerante a fallos si el sistema cumple sus especificaciones a pesar de la presencia de fallos. Por lo tanto, se debe asegurar **disponibilidad**, es decir, que los recursos son accesibles a pesar de que se presenten fallos, y que la consistencia de los recursos se asegurare a pesar de los fallos (atomicidad).



Existen diferentes técnicas para el aumento de escalabilidad en los sistemas, como son: 
- Replicación de datos: múltiples copias del mismo dato. 
- Replicación de procesos: múltiples ejecuciones de la misma computación. 
- Caching y su respectivo problema de consistencia de datos. 
- Distribución de carga entre los distintos nodos que conforman el sistema distribuido.

### Teorema del CAP

Antes, el aumento de rendimiento en un sistema era simple: por medio de la escalabilidad vertical o mejorando la aplicación para optimizar su funcionamiento (ajuste de rendimiento). No obstante, cada vez fue necesario incoporar una tercera opción, la escalabilidad horizontal debido al creciente procesamiento de datos, que ya no podía ser solucionado con las dos primeras opciones. 

En casos de Big Data, ya no es aceptable ejecutar un único servidor, con una sola base de datos, en un único centro de datos adyacente a la sede de su empresa. Se necesitan entornos verdaderamente distribuidos para afrontar los retos empresariales actuales.

No obstante, los sistemas distribuidos añaden más variables a la ecuación que producen un costo y una complejidad adicional. 

A raíz de la formulación para obtener la mejor configuración y solventar los problemas, nace el Teorema del CAP (Consistency, Availability, Partition tolerance), Consistencia, Disponibilidad, tolerancia a la Partición. 

![](/img/computacion/CSP.png)

1. **Tolerancia a la partición:** el sistema continúa funcionando a pesar del particionamiento arbitrario debido a fallos de red (fallos de comunicación entre nodos del sistema).
2. **Disponibilidad:** Se refiere a la medida en que cualquier cliente que realice una solicitud de datos obtiene una respuesta, independientemente de que hayan nodos fallando. Como consecuencia, en el diseño del sistema, se asume que el fallo será inminente y por lo tanto entre más nodos, más disponible será el sistema. 
3. **Consistencia:** todos los nodos ven los mismos datos, al mismo tiempo.

### Tipos de sistemas distribuidos 

- **Sistemas clusters y supercomputadores (sistemas informáticos distribuidos)**. Un cluster de cómputo se define como un conjunto de máquinas conectadas entre sí, que permiten resolver un problema de forma distribuida, ofreciendo una alta capacidad de cómputo.Los sistemas cluster son sistema centralizados, basados en la agrupación de computadores genéricos (commodity) de forma barata y ampliable. En prácticamente todos los casos, la computación de clusters se utiliza para la programación paralela en la que un único programa, de computación intensiva, se ejecuta en paralelo en múltiples máquinas.
- **Grid Computing (sistemas de información distribuidos)**. En 1999, Ian Foster y Carl Kesselman plantearon un sistema distribuido como una analogía con el suministro eléctrico: el usuario debe tener acceso a los recursos computacionales en condiciones similares a las que tiene para utilizar la energía eléctrica, es decir, desde cualquier sitio (geográficamente dispersos), con una interfaz uniforme, pudiendo confiar en su funcionamiento (fiables, robustos) y a un coste asequible. Este concepto se basa en agregar y compartir recursos en un ecosistema distribuido.
- **Cloud Computing (sistemas omnipresentes)***. El cloud computing se caracteriza por un conjunto fácilmente utilizable y accesible de recursos virtualizados. Los recursos y cómo se utilizan pueden configurarse de forma dinámica, proporcionando la base para la escalabilidad, si se necesita más trabajo, un cliente puede simplemente adquirir más recursos. Estos sistemas pueden proporcionar un beneficio mutuo o bidireccional a las empresas. Empresas con exceso de capacidad de cómputo pueden, de forma rentable, dejar usar sus sistemas a distintos clientes. Por otro lado, las empresas con demanda de capacidad de cómputo, pueden buscar alquilar la infraestructura de quién le ofrezca mejor precio, servicio o relación entre ellos.

### Sistemas de almacenamiento distribuido

- **Almacenamiento en infraestructura cloud:** esta aproximación ofrece las ventajas de la virtualización y el aislamiento de los datos almacenados. 
- **Almacenamiento secundario:** esta solución tiene como principal ventaja la protección de los datos. Los datos pueden estar organizados en base de datos in-memory como pueden ser: Cassandra, MongoDB, Memcached o BigTable. Una de las técnicas más empleadas en este tipo de sistema de almacenamiento es la deduplicación. La dedupliucación elimina los datos redundantes almacenados, guardando una única copia idéntica de los datos.
- **Almacenamiento en capas (jerarquía de dispositivos):** estos sistemas se componen por sistemas lentos (almacenamiento en cintas), por sistemas como discos magnéticos, pasando por almacenamiento en estado sólido (SSDs), hasta llegar al almacenamiento en memoria (in-memory).
- **Storage-as-a-Service:** sistemas de almacenamiento basados en cloud computing, por ejemplo, Amazon S3.

Otro de los factores críticos a la hora de diseñar un sistema cluster es la elección de la tecnología de interconexión. Se puede encontrar en el mercado soluciones como Ethernet (1 Gbps o 10 Gbps), InfiniBand (hasta 50 Gbps) o fibra (+100Gbps).

13/12/22

**Middleware:** Un middleware es un software que facilita la conexión de aplicaciones que no fueron diseñadas para conectarse entre sí, brindando una funcionalidad mayor que operando independientemente. 
Ejemplo: en un ecommerce 

16/22/22

NetBIOS es el protocolo de unidades de red que implementa Windows, y es el software que hace visible los recursos de un equipo a través de la red para que lo utilicen otros, para compartir de un PC a otros. Linux y la comunidad hicieron algo parecido, SAMBA, no solo se puede compartir recursos y ficheros entre SOs Windows, sino también entre SOs Linux y Windows. NFS (Network File System) es un protocolo que permite compartir recursos entre SO Linux. 

¿Qué es YARN? - Es el clúster que Permite que las aplicaciones que corren en el clúster tengan alta disponibilidad independientemente de los fallos que ocurran, por medio de los nodos en el sistema. 

¿Qué es Hadoop? - Es el sistema de ficheros distribuido. Es la implementación que nos va a permitir que los nodos compartan sus recursos como si fuesen uno solo disco virtual. Permite que los nodos se interconecten y se compartan los recursos de estos. Permite replicar los datos entre cada uno de los datos, trocearlos y replicarlos, para que en caso de fallo de uno de los nodos, podamos recuperar un fichero completamente siempre.  

En Hadoop, tenemos 
- **Namenodes.** Es el nodo que actúa como *master* o coordinador general, es el nodo maestro. 
- **Datanodes.** Nodos que comparten recursos. 

![](/img/computacion/hadoop.png)


Cada cierto tiempo Yarn va a mandarle una llamada a cada uno de los nodos para ver si están funcionando correctamente. Si el nodo no respondiera, el namenode va a mandarle un par de señales más. Si no contesta, el namenode lo va a desconectar, lo va a dar por perdido. 

Vamos a ver los comandos para que podamos navegar por Hadoop. 

Los sistemas Hadoop se diseñaron especialmente para funcionar con sistemas de disco. La información se lee y se graba en un disco. La arquitectura distribuida en Hadoop consiste en trocear un problema, distribuirlo a diferentes nodos (map), resolver una solución parcial local y luego ensamblar las soluciones parciales en una solución global (reduce). Esto se realiza gracias a **map reduce**. *Map* es aplicar a los nodos una función troceada y *Reduce* significa una vez tengo las soluciones parciales, reducirlas a una sola solución. 

Protocolo SSL. Es un protocolo de seguridad para encriptar la información. 


Hay varios formatos de ficheros  de interacambio de información (JSON, XML,CSV), pero no son óptimos para consultas. 

En el mundo Big Data se utilizan consultas de ficheros en disco, directamente consultar los ficheros sin cargar la info en la BBDD. Para este tipo de arquitectura se guarda la info en formatos .parquet y .orc. El formato parquet admite metadatos, y la información se guarda en columnas (formato columnar). La información no está optimizada para el almacenamiento de datos sino para su consulta. Ejemplos que usan el formmato columnar son AWS y BigQuery. La consulta en el formato columnar es mucho más rápida. 

Aparte de permitir la consulta rápida, el formato columnar permite comprimir en disco y ahorrar mucho espacio. 


Comandos que permiten la configuración del servicio 


```bash

vi core-site.yml
vi hdfs-site.yml
vi yarn-site.yml
vi mapred-site.yml

```

Los comnados para entornos de servicios: Configurar o definir cómo se conectan los servicios (.sh/.cmd)

```bash
hadoop-env.sh (Entornos Linux)
hadoop-env.cmd (Entornos Windows)
mapred-env.sh
mapred-env.cmd 
yarn-env.cmd 
yarn-env.sh
```







20/12/22
YAM
Hadoop. Es el sistema de gestión de datos, no tiene nada que ver con el clúster. 