
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
    - MPLS. Lo instala la compañía telefónica, instala un gran ancho de banda, que luego fragmenta en tuberías virtualizadas para venderlo a clientes individuales. Como consecuencia, es muy fácil crear recursos o desensamblar la red.  

Paralelamente a estos factores, se ha ido desarrollando la **miniaturización** de los sistemas informáticos, siendo el resultado más deslumbrante el *smartphone*. 

Como consecuencia, no sólo es fácil sino también factible construir un sistema distribuido, que consiste en una red de computadoras dispersas geográficamente. El tamaño puede ser de un puñado a millones de nodos y la red de interconexión puede ser cableada, inalámbrica o un híbrido. 

### Protocolos TCP y/o Modelos de Operación

Los sistemas distribuidos y Cloud existen porque se han dado las condiciones. Entre ellas están los protocolos de red. 

Es importante porque seguramente si trabajamos con una app Cloud como AWS, a la hora de hacer un despliegue en una infraestructura, con toda seguridad vamos a tener que instalar una VPC y subredes; segmentar una subred para poder tener direcciones de red suficientes; saber abrir puertos. 



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

16/11/22 

#### Ventajas 
- Compartir recursos (HW, SW, datos)
- Ofrecer una buena relación coste-rendimiento. Trabajan con el objetivo de disminuir la latencia, tiempo de respuesta, ancho de banda y capacidad de proceso. Esto se logra gracias al uso de hardware commodity (productos no diferenciados)
- Escalabilidad. Aumentar la capacidad de crecimiento.
- Ofrecen una solución para la tolerancia a fallos, disponibilidad, replicación y escalabilidad. 
- Rendimiento mejorado. En sistemas de gran escala, son un excelente modelo para la distribución de carga de trabajo
- Es capaz de ofrecer servicios a múltiples clientes de manera simultánea. 

#### Desventajas
- Complejidad. Son difíciles de implementar. mantener y solucionar. No solo se limita al hardware, sino también al software. Varios sistemas trabajando al mismo tiempo (leyendoo y escribiendo) pueden provocar fallos en el sistema e inconsistencias en los datos. 
- Coste de entrada inicial alto 
- Cuellos de botella en transferencia de red. Cuando los datos se distribuyen entre varios nodos, es necesario moverlos.
- Fallos debido a errores humanos. Con múltiples componentes el factor de error aumenta. 

### Sistemas distribuidos vs. Computación Paralela

En una topología de procesamiento en paralelo: 
- La carga de trabajo se distribuye en varios procesadores en una o más computadoras, denominadas nodos de cómputo. 
- Los entornos de procesamiento en paralelo se clasifican como: 
    - Sistemas de multiprocesamiento simétrico (symmetric multiprocessing, SMP).  Uno o más procesadores que comparten componentes de hardware. 
    - Procesamiento paralelo masivo (massively parallel processing, MPP). Es una arquitectura donde hay muchas computadoras alojadas físicamente en un mismo chasis. Son las famosas supercomputadoras. 

#### MPP 

Un sistema MPP, está físicamente disperso. 
- El rendimiento mejora al no compartir recursos físicos. 
- El sistema escala agregando commputadoras, disco y memoria. 
- Un sistema de archivos se comparte por medio de red. 
- Los archivos de programa se pueden compartir en el sistema en lugar de copiarse en cada disco individual .


### Sistemas distribuidos y middlewares

**Middleware:** Un middleware es un software que facilita la conexión de aplicaciones que no fueron diseñadas para conectarse entre sí, brindando una funcionalidad mayor que operando independientemente. Es capaz de asegurar que múltiples procesos ocurriendo sobre un mismo recurso no corrompe los datos. 

> El middleware actúa como un puente entre tecnologías, herramientas y bases de datos diversas para que pueda integrarlas sin dificultad en un único sistema. - AWS 

Los sistemas distribuidos se encargan para tener una capa separada de software para facilitar el uso de aplicaciones compartidas

![](/img/computacion/middleware.png)

Las funciones de un middleware son: 
- Permitir que los componentes, procesos o aplicaciones intercambien información. 
- Ocultar el carácter "distribuido" de los nodos y la heterogeneidad de los componentes. 
- Ofrecer interfaces de alto nivel de estándar y uniformes para el desarollo de apps. 
- Ofrecer servicios comunes para facilitar la comunicación entre aplicaciones. 

#### Tipos de middleware

- Servidores de aplicación web o middleware de dispositivos móviles.
- *Integración basada en la nube como servicio* (Integration Platform as a Service, IPaaS) es una solución basada en la nube que simplifica la integración en entornos locales (on-premises ) y en la nube. Es una solución de autoservicio
- bus de servicio empresarial (Enterpise Service Bus, EBS)
- *Message brokers.* Son una tecnología de comunicación de aplicaciones para ayudar a construir un mecanismo de integración común para admitir arquitecturas de nube nativas. 
- iP

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

- **Almacenamiento en capas**

- **Sistemas clusters y supercomputadores (sistemas informáticos distribuidos)**. Un cluster de cómputo se define como un conjunto de máquinas conectadas entre sí, que permiten resolver un problema de forma distribuida, ofreciendo una alta capacidad de cómputo.Los sistemas cluster son sistema centralizados, basados en la agrupación de computadores genéricos (commodity) de forma barata y ampliable. En prácticamente todos los casos, la computación de clusters se utiliza para la programación paralela en la que un único programa, de computación intensiva, se ejecuta en paralelo en múltiples máquinas.
- **Grid Computing (sistemas de información distribuidos)**. En 1999, Ian Foster y Carl Kesselman plantearon un sistema distribuido como una analogía con el suministro eléctrico: el usuario debe tener acceso a los recursos computacionales en condiciones similares a las que tiene para utilizar la energía eléctrica, es decir, desde cualquier sitio (geográficamente dispersos), con una interfaz uniforme, pudiendo confiar en su funcionamiento (fiables, robustos) y a un coste asequible. Este concepto se basa en agregar y compartir recursos en un ecosistema distribuido.
- **Cloud Computing (sistemas omnipresentes)***. El cloud computing se caracteriza por un conjunto fácilmente utilizable y accesible de recursos virtualizados. Los recursos y cómo se utilizan pueden configurarse de forma dinámica, proporcionando la base para la escalabilidad, si se necesita más trabajo, un cliente puede simplemente adquirir más recursos. Estos sistemas pueden proporcionar un beneficio mutuo o bidireccional a las empresas. Empresas con exceso de capacidad de cómputo pueden, de forma rentable, dejar usar sus sistemas a distintos clientes. Por otro lado, las empresas con demanda de capacidad de cómputo, pueden buscar alquilar la infraestructura de quién le ofrezca mejor precio, servicio o relación entre ellos.

![](/img/computacion/almacenamiento_cloud.png)

### Sistemas de almacenamiento distribuido

- **Almacenamiento en infraestructura cloud:** esta aproximación ofrece las ventajas de la virtualización y el aislamiento de los datos almacenados. 
- **Almacenamiento secundario:** esta solución tiene como principal ventaja la protección de los datos. Los datos pueden estar organizados en base de datos in-memory como pueden ser: Cassandra, MongoDB, Memcached o BigTable. Una de las técnicas más empleadas en este tipo de sistema de almacenamiento es la deduplicación. La dedupliucación elimina los datos redundantes almacenados, guardando una única copia idéntica de los datos.
- **Almacenamiento en capas (jerarquía de dispositivos):** estos sistemas se componen por sistemas lentos (almacenamiento en cintas), por sistemas como discos magnéticos, pasando por almacenamiento en estado sólido (SSDs), hasta llegar al almacenamiento en memoria (in-memory).
- **Storage-as-a-Service:** sistemas de almacenamiento basados en cloud computing, por ejemplo, Amazon S3.

Otro de los factores críticos a la hora de diseñar un sistema cluster es la elección de la tecnología de interconexión. Se puede encontrar en el mercado soluciones como Ethernet (1 Gbps o 10 Gbps), InfiniBand (hasta 50 Gbps) o fibra (+100Gbps).


16/22/22

NetBIOS es el protocolo de unidades de red que implementa Windows, y es el software que hace visible los recursos de un equipo a través de la red para que lo utilicen otros, para compartir de un PC a otros. Linux y la comunidad hicieron algo parecido, SAMBA, no solo se puede compartir recursos y ficheros entre SOs Windows, sino también entre SOs Linux y Windows. NFS (Network File System) es un protocolo que permite compartir recursos entre SO Linux. 

¿Qué es YARN? - Es el clúster que Permite que las aplicaciones que corren en el clúster tengan alta disponibilidad independientemente de los fallos que ocurran, por medio de los nodos en el sistema. 

¿Qué es Hadoop? - Es el sistema de ficheros distribuido. Es la implementación que nos va a permitir que los nodos compartan sus recursos como si fuesen uno solo disco virtual. Permite que los nodos se interconecten y se compartan los recursos de estos. Permite replicar los datos entre cada uno de los datos, trocearlos y replicarlos, para que en caso de fallo de uno de los nodos, podamos recuperar un fichero completamente siempre.  

- YARN: Gestor del clúster. Keep Alive. Sistema distrbuidor de cargas, se encarga de mantener y distribuir las cargas en los diferentes nodos del clúster. Ahora Hadoop recomienda no utilizar Yarn. 
- HDFS: Sistema de gestión de ficheros. Se encarga de generar réplicas en distintos nodos, gestiona el acceso a los datos. Tiene su propio formato. 


En Hadoop, tenemos 
- **Namenodes.** Es el nodo que actúa como *master* o coordinador general, es el nodo maestro. 
- **Datanodes.** Nodos que comparten recursos. 

![](/img/computacion/hadoop.png)


Cada cierto tiempo Yarn va a mandarle una llamada a cada uno de los nodos para ver si están funcionando correctamente. Si el nodo no respondiera, el namenode va a mandarle un par de señales más. Si no contesta, el namenode lo va a desconectar, lo va a dar por perdido. 

Vamos a ver los comandos para que podamos navegar por Hadoop. 

Los sistemas Hadoop se diseñaron especialmente para funcionar con sistemas de disco. La información se lee y se graba en un disco. La arquitectura distribuida en Hadoop consiste en trocear un problema, distribuirlo a diferentes nodos (map), resolver una solución parcial local y luego ensamblar las soluciones parciales en una solución global (reduce). Esto se realiza gracias a **map reduce**. *Map* es aplicar a los nodos una función troceada.  En Map pasas una función y una lista a la que hay que aplicarle la función y el sistema itera en cada uno de los índices de la lista aplicándole la función. *Reduce* significa una vez tengo las soluciones parciales, reducirlas a una sola solución.

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

## Tolerancia a fallos en sistemas distribuidos

Las empresas se han dado cuenta que necesitan algo más que crear una infraestructura confiable para resistir y sobrevivir las amenazas, respaldar el crecimiento y proteger la información. Esto implica que no sólo estamos hablando de desastres naturales como un huracán o un tornado, sino también y principalmente de ataques cibernéticos. 

Plan de Continuidad del Negocio vs Plan de Recuperación ante Desastres 

- **Business Continuity Plan:** Qué condiciones y recursos debo disponer para que  los usuarios y servidores no perciban un desastre en caso de que ocurra.  Debo identificar los nodos que deben permanecer inalterados. Es un proceso muy caro.  
- **Disaster Recovery Plan:** Qué condiciones mínimas necesito para que mi negocio siga trabajando tras un desastre.



### Disaster Recovery Plan 

- Busca restablecer los servicios básicos lo antes posible para que el negocio pueda operar. No solo incluye estrategias de hardware y software sino también involucra operaciones manuales. 

### Business Continuity Plan

> Es un plan que describe cómo la empresa continuará operando incluso ante la aparición de un problema, que, teóricamente hablando, produciría una interrupción no planificada en el servicio. Busca que el negocio no se detenga. 


¿Por qué es importante tener un Business Continuity Plan?

Es importante para evaluar la resiliencia y la sincronización entre los procesos del negocio, las aplicaciones y la infraestructura de TI. 

 1. En caso de una eventualidad la empresa deja de producir valor y recibir ingresos. 
 2. Genera desprestigio. 

#### Aspectos principales a tomar en cuenta 
- **Alta disponibilidad**. Busca proporcionar las capacidades y procesos necesarios para que una empresa tenga acceso a las aplicaciones clave independientemente de los fallos acaecidos. Estos fallos pueden ser físicos, en el proceso, en el hardware o software. 
- **Operaciones continuas**. Protegen la capacidad de mantener los sistemas en funcionamiento tanto durante las interrupciones planificadas como las no planificadas. 
- **Recuperación ante desastres**

### Motivación de tener un BCP

- El BCP surgió de la planificación para la recuperación ante desastres a principios de los 70s. 
- Organizaciones como bancos y aseguradoras invirtieron en colocar copias de seguridad en emplazamientos alternativos. 
- En los 80s aparecieron proveedores comerciales que prestaban servicios de respaldo de IT. 
- Con la creciente globalización en los 90s, surgió la necesidad del acceso a los datos desde varios emplazamientos situados en largas distancias. Se dejó de pensar en un DCP y se comenzó a considerar el BCP de una manera más holística. 

### La transformación digital y la hiperconvergencia

Crean puertas de acceso no deseadas y con ella nuevos riesgos, vulnerabilidades, ataques y puntos de fallo. 
Los BCP están contemplando cada vez más la eventualidad de un ciberataque. 

Los planes de contingencia han de incluir formas de defenderse contra esos riesgos, proteger aplicaciones y datos críticos y ser capaces de recuperarse de ataques o fallos de manera controlada y medible. 
Otro problema añadido es el del aumento exponencial de los volúmenes de datos. 

RPO (Objetivo de Punto de Recuperación ): Es la cantidad máxima de datos, medida en el tiempo, qu una organización puede perder sin causar daños irreversibles a su negocio. 
RTO (Objetivo de Tiempo de Recuperación): Es el tiempo máximo tolerable que una computadora, sistema o red puede estar fuera de servicio después de que ocurre un fallo o desastre. (minutos, segundos, horas o días.)


10/01/2023

## Computación paralela vs. Computación en serie

### Computación en serie

Tradicionalmente el software se ha escrito para el **cálculo en serie**: Un proble se divide en una serie discreta de instrucciones. La sinstrucciones se ejecutan secuencialmente una tras otras ejecutándose en un solo procesador, solo se puede ejecutar una instrucción en cada momento. 

![](/img/computacion/computacion_serie.png)


### Computación en paralelo 

La carga de de cada trabajo se distribuye entre varios procesadores en una o más computadoras denominadas nodos de cómputo. 

Los entornos de procesamiento paralela se clasifican como: 
- Sistemas de procesamiento en paralelo (SMP) 
- Procesamiento paralelo masivo (MPP)


![](/img/computacion/computacion_paralela.png)

### Características de la computación paralela

En el sentido más estricto, es el uso simultáneo de múltiples recuross informáticos para resolver un problemas computacional

- Un problema se divide en partes discretas que se pueden resolver al mismo tiempo
- Cada parte se divide en una serie de instrucciones. 
- Las instrucciones de cada parte se ejecutan simultáneamente diferentes procesadores. 
 
 El problema dque se trata de computar debe ser capaz de: dfescomponerse en partes discretas de trabajo que puedan resolverse simultáneamente. Ejecutar múltiples instrucciones del probgrama en cualquier momento. Debe de poder se resuelto en menos tiempo con varios recursos informáticos que un único recurso. 

 Los recurso sinformáticos suelen ser: Una sola computadora con mútliples procesadores/núcleos. Un número artbitrario de tales computadoras conectas por una red. 

### Cómo puede una computadora procesar en paralelo 

Desde la perspectiva del hardware prácticamente todas las computadoras hoy en día tienen capacidad de proceso en paralelo: múltiples unidades funcionales (caché L1 y L2, decodificación, punto flutante, procesamiento de gráficos (GPU), entero, etc.). No es lo mismo hacer cálculos con números enteros, con números de coma flotante. Actualmente tenemos múltiples unidades/núcleos/cores de ejecución. El hardware tiene una capacacidad para múltiples subprocesos/threads

No obstante, para algunos software no por tener mútltiples núcleos la máquina puede ir más rápido, más bien a veces puede ir más lento. Por ejemplo, los videojuegos. 

*La memoria caché (oculto, escondido en francés) es información, instrucciones, procedimientos que se guardan de forma temporal y se usan de manera frecuente. Se guarda una copia cerca del procesador para que sea más rápido obtener esa información y así no deba consultar a los servidores origen. Los beneficios son que el rendimiento mejora. No obstante, la saturación de la memoria puede volverse contraproducente, por lo que es deseable y necesario que se vaya eliminando de tanto en cuando. Tiene que buscarse el tiempo óptimo de eliminación ya que si la eliminación es muy frecuente entonces el procesador no va a tener copias a las cuales consultar y por lo tanto el procedimiento de consulta va a ser lento.*

*Tenemos dos tipos de memoria caché: web y disco. La memoria caché web almacena las páginas web que visitamos frecuentemente para agilizar la carga de dichas páginas y así ahorrar ancho de banda o datos, y la caché disco tiene un significado parecido a lo explicado arriba*.

### ¿Por qué utilizar la computación paralela?

-El mundo real es enormemente complejo, se simula mejor en procesos paralelos que en serie. 
- En teoría es bastante eficiente y ahorra tiempo y dinero para solucionar una tarea que debe resolverse en un tiempo corto. En pocas palabras, trabajar en paralelo acorta el tiempo de ejecución. 

![](/img/computacion/computacion_paralela_beneficios.png)


## La ley de Amdahl

> La fórmula de la ley de Amdahl sirver para definir si la introducción de una mejora en sus sistema merece o no la pena. 

Calcula la mejora esperada de un sistema si se mejora una única parte de la misma. Esto quiere decir que hay una parte del código que se ejecuta en serie y no vamos a poder optimizar, mientras que hay otra parte que se puede o ya se ejecuta en paralelo. 

![](/img/computacion/amdahl.png)

- *Smax* es la mejora posible del sistema global y se expresa como un numero decimal mayor que 1. Entre más grande mejor. 
- *p* es la parte del sistema que se trata de mejorar, expresada como un númeroentre [0,1]. En otras palabras, es la fracción paralela del código. Por lo tanto 1-p es la fracción serie del código. 
- *s* es el factor de mejora de p, expresado como el factor de veces que p puede ser ejecutado más rápidamente. Es el número de procesadores o mejora de velocidad en la parte paralela. 


![](/img/computacion/amdahl_2.png)

![](/img/computacion/amdahl_3.png)

![](/img/computacion/amdahl_4.png)

10 veces más ciclo de reloj o que la capacidad/cache/arquitectura del hardware permiten que la ejecución del servidor web sea más rápido. 

![](/img/computacion/amdahl_5.png)

Tenemos un software que el 80% del programa es paralizado, tenemos un único procesador. Ahora queremos incorporar 4 procesadores para ejecutar la versión paralela del programa. Vale la pena invertir en esta mejora'

Esta ley tiene algunas limitaciones, por lo que ha dado lugar a otras leyes

## Ley de Gustafson 


Es una ley en informática que dice que los cálculos que involucran conjuntos de daots arbitrariamente grandes se pueden paralelizar de manera eficiente. En pocas palbras, cualquier problema suficientemente grande pude ser eficientemente paralelizado. 

Gustafson le dice a Amdahl que da igual la parte en serie, si la cantidad de datos es grande, la paralización de procesos va a ser beneficiosa. 

![](/img/computacion/gustafson.png)

- *S* es la aceleración teórica del programa con paralelismo
- *N* es el número de procesadores 
- *s* y *p* son las gracciones dedicadas a ejecutar las partes en serei y en paralelo del programa en un sistema paralelo, donde s+p =1. 

## ¿Qué es el desarrollo en paralelo?

- Es el desarrollo simultáneo de más de una versión de un objeto. 

Tipos de desarrollo paralelo: 
- Desarrollo concurrente paralelo (Parallel concurrent development)
- Desarollo de plataforma paralela (Parallel platform development)
- Desarrollo de versiones paralelas (Parallel release development)

### Desarrollo concurrente paralelo 

Ocurre cuando varios desarrolladores desarrollan sus propias versiones del trabajo del mismo objeto (Git, GitHub). Frecuentamente es que cada desarrollador trabaje en diferentes secciones del código (ramas). Una vez que los desarrolladores completan su trabajo, las versiones del código se fusionan. 

### Desarollo de plataforma paralela

Ocurre cuando varios desarrolladores están trabajando en diferentes versiones del mismo objeto para diferentes plataformas de hardware o SO (aplicaciones para iOS y Android). Normalmente no se fusionan. 

### Desarrollo de versiones paralelas 

Ocurre cuando una organzación necesita producir simultáneamente varias versiones de su producto de software.

**pedirle el dataset que utilizó en esta clase** 


17/01/2023

``` bash

- Recuperar la configuración inicial del sistema y el URL que debemos introducir para acceder: hdfs getconf -confKey fs.defaultFS (p.ejem. "hudfs://tucan:9000)
- Recuperar el punto de acceso al clúster (en  proceso de extinción): hdfs getconf -confKey fs.default.name
- Observar el nombre de los namenodes: hdfs getconf -namenodes
- Lisa de comandos: hdfs dfs 
- Enlistar los archivos de Hadoop: hdfs dfs -ls <ruta>
- Crear un diretorio: hdfs dfs -mkdir <ruta> <nombre de la carpeta>
- Reemplazar un directorio existente: hdfs dfs -mkdir -p <ruta/nombre de la carpeta>
- Enlistar los ficheros con sus tamaños correspondientes: hdfs fs -ls -h <ruta>
- Listar todos los ficheros y directorios recursivamente (con subdirectorios): hdfs dfs -ls -R /
- Crear un archivo vacío: Hdfs dfs -touchz <ruta> <nombre>.txt
- Copiar de un sistema local a Hadoop: hdfs dfs -copyFromLocal 
- Subir un archivo a HDFS: hdfs dfs -put <ruta/nombre del archivo> <ruta de destino>
- Sobrescribir un archivo existente a HDFS: hdfs dfs -put -f /home/file1 /hadoop
- Copiar el fichero ‘file1’ de hdfs al sistema de ficheros local: hdfs dfs -get /file1 /home/ <ruta destino>	
- Leer un archivo de Hadoop: hdfs dfs -cat <ruta/nombre del texto>
- Eliminar un fichero: rm <ruta/nombre del archivo>
- Copiar el fichero ‘file1’ del sistema de ficheros local a hdfs y luego lo borra del sist. ficheros local: hdfs dfs -moveFromLocal <ruta/nombre del archivo>
- Copiar un archivo dentro Hadoop: hdfs dfs -cp <ruta/nombre archivo origen> <ruta/nombre archivo destino>
- Mover un archivo dentro Hadoop: hdfs dfs -mv <ruta/nombre archivo origen> <ruta/nombre archivo destino>
- Borrar ficheros en un directorio remoto: hdfs dfs -rm -r <ruta/nombre del archivo>
- Ver el tamaño de los ficheros y directorios: hdfs dfs -du <ruta/nombre>
- Ver el tamaño de los ficheros: hdfs dfs -du -s  <ruta/nombre> /* The -s option will result in an aggregate summary of file lengths being displayed, rather than the individual files. */
- Ver los metadatos de los ficheros: hdfs dfs -stat <ruta>/*  /* el asterisco sirve para que nos dé los metadatos individualmente para cada directorio o fichero individualmente contenido en la ruta. 
- Cambiar el factor de replicación recursiamente : hdfs dfs -setrep -w <número de réplicas> <ruta/nombre archivo> /* La w es de Wait y solicita que se espere a la finalización de las réplicas para que el commando se complete. /*
 
```

## Consolidación de servicios

### ¿Qué es la virtualización de los servidores? 

Es un proceso que permite una utilización más eficiente de hardware físico y es la base de la computación en la nube. 

La virtualización utiliza software para crear una capa de abstracción sobre le hardware de la computadora tal que permite que los elementos de hardware se dividan en varias ocmputaodras virtuales comúnmente llamadas máquinas virtuales

![](/img/computacion/consolidacion.png)

Cada máquina virtual ejecuta su propio sistema operativo y se comporta como una computadora independiente, aunque solo tiene acceso a una parte del hardware de la computadora subyacente real. 

De lo anterior se deduce que la virtualización permite una utilización m+ás eficiente del hardware físico y con ello un mayor retorno de la inversión del hardware de una empresa. 

### ¿Cuáles son los beneficios de la virtualización?

La virtualización asporta varios beneficios a los operadores de centros de datos y proveeedores de servicios: 
- Eficiencia de los recursos: Cada servidor de aplicacione srequería su propia CPU física dedicada. Ls recursos sobrantes no se aprovechaban cuando estaban separados.
- Administración mpas sencilla. Reemplazar las computaodras físicas con máquinas virtuales definidas por software facilita el uso y la administración del software. 
- Tiemmpo de inactividad mínimo: Los fallos del SO y de las aplicaciones pueden causar tiempo de inactividad e interrumpir 
- Aprovisionamiento más rápido: Comprar, instalar y configurar hardware para cada aplicación requiere mucho tiempo. Si se dispone de hardware ya instalado, el aprovisionamiento de máquinas virutales es significativamente más rápido. Incluso puede automatizarse utilizando un software de gestión e integrarlo en los flujos de trabajo existentes. 

### ¿Cuántas soluciones de virtualización conoces? 

- **VMware** especializada en virtualización de servidores, escritorios, redes y almacenamiento. 
- **Microsoft Hyper-V** se enfoca en virtualización de servidores y PCs de escriotrio. 
- **Citrix** tiene su nicho en la virtualización de aplicaciones, también ofrece virtualización de servidores y soluciones de escritorio virtual. 
- **Oracle VirtualBox** es un hipervisor que permite crear máquinas x86 virtuales. 
- **IBM Linux for System z** permite ejecutar Linux en un sistema S/390 o System Z

24/01/2023

Se puso a hablar de bare-metal hypervisor

![](/img/computacion/bare-metal-hypervisor.png)