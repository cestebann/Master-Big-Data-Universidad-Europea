
# Índice

Unidad 0. Objetivos del curso
- Competencias específicas
- Resultados del aprendizaje
Unidad 1. Sistemas altamente distribuidos
- Los sistemas distribuidos en el mundo Big Data
- Introducción a los sistemas distribuidos
- Paradigma de programación paralela
- Tolerancia a fallos en sistemas distribuidos
Unidad 2. Sistemas cloud y virtualización de servicios
- Computación y almacenamiento en la nube
- Consolidación de servicios
- Amazon AWS
- Google Web Services
Unidad 3. Hadoop como sistema de cómputo en plataformas Big Data
- Apache Hadoop
- Hadoop Distributed File System
- Arquitectura de cómputo de Hadoop.
- Ejecución de aplicaciones en Apache Hadoop.
Unidad 4. Programación en Scala
- Introducción al lenguaje Scala
- Estructuras de control y definición de funciones
- Listas y contenedores
- Programación funcional
Unidad 5. Computación distribuida con Apache Spark
- Introducción a Apache Spark
- Programación de aplicaciones con Apache Spark
- Acceso a fuentes de datos con Apache Spark
- Gestión de trabajos Spark con Apache YARN
Unidad 6. Apache Spark avanzado
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

# Resultados de aprendizaje:
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

