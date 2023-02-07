Los siguientes apuntes son referentes al contenido colgado en el campus solamente. 

# Unidad 3. Hadoop como sistema de cómuto en plataformas Big Data



## Apache Hadoop 

### Objetivos

1. Presentar el framework de procesamiento distribuido y paralelo Apache Hadoop. 
2.  Introducir las principales características y ventajas de este sistema 
3. Abordar los primeros pasos con el modelo de programación basado en MapReduce.


> Cada vez que escuchamos hablar de Big Data, la mayoría de las empresas y de las personas pensamos en Hadoop.

El Big Data es un conjunto de técnicas informáticas que nos van a servir para almacenar, procesar y gestionar grandes cantidades de datos.

Una de las soluciones para procesamiento basado en Big Data más conocidas y afianzadas en el mercado es Apache Hadoop.

- Apache Hadoop es un proyecto de software open source para computación distribuida, escalable y de confianza. 
- Además, ofrece un framework que permite la computación distribuida de grandes conjuntos de datos, usando clústeres de ordenadores y mediante el uso de modelos de programación simples.
- Apache Hadoop está diseñado para poder pasar de un solo servidor a miles de máquinas (scale-up), donde cada una ofrece tanto computación como capacidades de almacenamiento.
- El framework está diseñado para detectar y tratar fallos a nivel de aplicación. Esto permite ofrecer servicios con alta disponibilidad sobre un clúster de ordenadores, aunque estos presenten fallos durante la ejecución de las aplicaciones. Los fallos pueden ser debidos tanto por software, una mala implementación, o por hardware, fallo en algún componente, como la memoria o la red de interconexión.

### Breve historia

Actualmente, Hadoop es un proyecto de código abierto bajo licencia Apache. Su licencia ha facilitado que sea adoptado por un importante número de empresas. El apoyo de IBM, Oracle o EMC ha acelerado su implantación y su mejora en prestaciones. A día de hoy, Apache Hadoop tiene un gran uso en proyectos basados en Big Data. JPMorgan Chase, una de las mayores multinacionales de servicios bancarios y financieros, declaró que contratan y pagan un 10 % más que otras compañías a aquellos aspirantes con conocimientos de Apache Hadoop.

### Características generales

- Es una solución open source.
- fue inicialmente desarrollado por Yahoo. 
- Es administrado por Apache Software Foundation. 
- Está diseñado para trabajar con petabytes de datos. 
- Además está pensado para implementarse con software y hardware económico. 
- Ofrece una alta disponibilidad. 
- Podemos escalar horizontalmente, 
- Muchas tecnologías de desarrollo están basadas en Apache Hadoop como Apache Pick, y además, tiene buena aceptación en el mercado. 
- Es importante aclarar que no es una base de datos y no es un sistema de procesamiento en tiempo real, ya que no se pueden garantizar plazos fijos de ejecución.

### Componentes princiaples 

![](/img/computacion/componentes_hadoop.png)


1. **MapReduce** es una implementación del paradigma de procesamiento MapReduce basado en datos y provista por Hadoop, la cual opera directamente sobre HDFS, aprovechando la escalabilidad que ofrece este sistema de almacenamiento.
2. **Hadoop Common** es un conjunto de funcionalidades utilizada para dar soporte a aquellos proyectos que funcionan sobre Hadoop.
3. **HDFS** es un sistema de ficheros, que provee el ecosistema de Hadoop.


#### Modelo de Programación basado en MapReduce 

Empezaremos detallando las características principales del modelo de programación Map Reduce. 

- Primero, fue creado por Doug Cutting, quien también es el creador de Lucene
- MapReduce fue introducido por Google en 2004 y a posteriori, en 2006, por Yahoo para poder dar soporte al procesamiento paralelo de datos.
- MapReduce es el nombre dado a la combinación de dos procesos separados y necesarios para la extracción de valores de un gran número de orígenes de datos distintos. 
    1. La etapa *map* funciona como extractor y asigna valores a determinadas claves para un único documento. 
    2. La etapa *reduce* realiza la función de acumulación y combina las claves de múltiples documentos para crear un valor reducido, o combinado, único para cada clave a partir de los múltiples valores generados.

**Paralelismo**
Un trabajo grande puede dividirse en varias tareas, razón por la cual se pueden emplear varias máquinas para resolver cada una de estas. 

**Escalabilidad**
Debido a que el trabajo realizado puede ser dividido en varias tareas y a su vez, estas tareas pueden ser ejecutadas en paralelo en diversas máquinas diferentes, se provee un enorme poder de procesamiento, lo cual brinda una gran escalabilidad horizontal.

**Tolerancia a fallos**
Como los datos se encuentran replicados en las máquinas que conforman el clúster, tiene una alta tolerancia a fallos, de tal forma que, si uno de los nodos deja de estar disponible por algún motivo, otro nodo se puede ocupar de su lugar.

**Curva de aprendizaje elevada**
Finalmente, abstraerse en el modelo MapReduce por lo general, es una tarea difícil que lleva bastante tiempo, teniendo una curva de aprendizaje inicialmente elevada.


Hadoop proporciona un entorno de ejecución bajo el modelo de programación MapReduce. En este modelo, la ejecución de una aplicación se presenta en dos etapas: map y reduce.
- En la etapa *map* es donde se realiza la ingestión y la transformación de los datos de entrada, en la cual, los registros de entrada pueden ser procesados en paralelo dependiendo del particionamiento de los datos de entrada. 
- Por otro lado, en la etapa *reduce* procesaremos la agregación o resumen de los datos de la etapa Map, donde todos los registros asociados entre sí deben ser procesados juntos por una misma entidad.

##### MapReduce: etapa Map

Como fue explicado previamente, las tareas de mapping se pueden ejecutar en paralelo, lo cual brinda una enorme escalabilidad. El número de tareas que serán capaces de correr en paralelo, depende del número de nodos que conforman el clúster, teniendo en cuenta el número de slots configurado para las tareas de mapping de cada nodo.
Para hacer más simple de comprender el funcionamiento de map, se ha dividido en dos partes: en el primer caso, se recibe como valor de entrada un par (clave, valor) y genera como resultado intermedio uno o varios pares (clave, valor) donde cada uno de estos pares es una lista de elementos clave valor, como se puede observar en el diagrama.


![](/img/computacion/etapa_map.png)

En la segunda etapa del mapping, se mezclan y ordenan los resultados intermedios en función de las claves en un mismo nodo. Esta etapa es de vital importancia, ya que permite optimizar y reducir el uso de la red durante la siguiente etapa.

![](/img/computacion/map_segunda_etapa.png)


##### MapReduce: etapa Reduce 

Como se observa en el diagrama, durante la etapa reduce se combina la lista de valores de cada una de las claves en un único par (clave, valor). Al igual que en la etapa map, el reduce se ejecuta en paralelo y el número de reducers que componen se pueden correr al mismo tiempo dependiendo del número de nodos que conformen el clúster, considerando el número de slots disponible para las tareas de reducing de cada nodo.

![](/img/computacion/etapa_reduce.png)


## Arquitectura de Hadoop

### Objetivos

- Presentar los componentes principales de la arquitectura de Apache Hadoop
- Mostrar la integración entre el motor MapReduce y el sistema de ficheros HDFS
- Identificar las diferencias entre las distintas versiones de Apache Hadoop.


### Integración de componentes

![](/img/computacion/Integracion_componentes.png)

El siguiente diagrama muestra la integración de componentes de un ecosistema típico basado en Hadoop.
En naranja, mostramos los elementos fundamentales de la arquitectura de Hadoop, MapReduce y HDFS. En rojo, se muestran las distintas soluciones que hacen uso de Hadoop para el manejo procesamiento de datos. Por ejemplo, Apache Hive, el cual proporciona un sistema de acceso a la información basado en consultas SQL de datos que son almacenados en HDFS. Por último, en color verde, podemos tener paquetes adicionales. Por citar algunos: procesamiento de grafos con Pegasus, análisis estadístico con RHadoop o incluso aprendizaje automático gracias a Mahout.

### Tarea como abstracción de cómputo 

El pilar del procesamiento paralelo de las aplicaciones en Hadoop es la tarea. Hadoop dividirá de forma automática nuestro conjunto de datos inicial en tareas de tipo map y reduce. Inicialmente y simplificando, Hadoop creará al menos tantas tareas de tipo map como bloques de datos existentes en nuestro conjunto de datos almacenado en HDFS. Típicamente los bloques del sistema de ficheros tienen un tamaño de 64 a 128 megabytes.

![](/img/computacion/tarea_abstraccion_computo.png)

Por lo tanto, precisaremos de un administrador de recursos que se encargue de generar, asignar y monitorizar todas las tareas sobre los distintos recursos hardware, en este caso, los nodos esclavos que forman parte de nuestro clúster Hadoop.

A su vez, cada vez que una tarea es completada, y con el objetivo de garantizar la tolerancia a fallos, los datos intermedios son almacenados temporalmente en el sistema HDFS.

Por último, Hadoop creará un fichero de salida en HDFS por cada una de las tareas reduce creadas durante el proceso de ejecución. La escritura del conjunto de datos resultante se puede hacer de forma paralela, reduciendo significativamente los tiempos de escritura en HDFS.

### MapReduce:cómputo distribuido

El motor de ejecución MapReduce está completamente integrado con Hadoop y, por lo tanto, este provee de funcionalidades para ejecutar tareas map y reduce.

Básicamente, por tratarse de un componente de Hadoop, MapReduce opera directamente sobre el componente de almacenamiento HDFS.

En el diagrama se puede observar cuáles son las partes que constituyen la arquitectura software de MapReduce en Hadoop, y cómo estas partes interactúan entre sí. Nos centraremos en los componentes JobTracker y TaskTracker.

![](/img/computacion/computo_distribuido.png)



### Planificación de tareas 


### Job Tracker 
El JobTracker es un **planificador de tareas** encargado de **asignar y distribuir el trabajo entrante a los nodos que conforman el clúster**. **Mantiene los trabajos lo más cerca** posible de la máquina que emitió la información a procesar, de forma que se pueda reducir el tráfico en la red principal del clúster. 

Si se da el caso que el total de slots disponibles en el nodo para la tarea a realizar se encuentren ocupados, el JobTracker intentará asignar los trabajos en los nodos del mismo rack o armario.

![](/img/computacion/job_tracker.png)

### Task tracker 

Los TaskTracker son los nodos que conforman el clúster, y estos aceptan operaciones de **map, reduce y mezcla**, tarea que se mencionó antes durante la etapa map. 
Cada TaskTracker es configurado con un número de slots que indican el número de tareas que se pueden aceptar. 
**Se especifica un número de slots para las tareas de map y otro para las de reduce**, típicamente el número de slots disponibles para hacer el map es mayor que para ejecutar tareas de reduce. 

Además, el número de slots en cada nodo no necesariamente será el mismo, ya que no todas las máquinas deben tener expresamente la misma capacidad de cómputo.
El TaskTracker lleva un control de las tareas que se encuentran en ejecución y notifica al JobTracker cuando estas tareas terminan. 


![](/img/computacion/task_tracker.png)

Así mismo, el TaskTracker envía al JobTracker una señal de still alive o latido, cada cierto tiempo para notificar que está operativo. Estos mensajes también le informan al JobTracker acerca del número de slots disponibles para que este pueda delegar nuevos trabajos en caso de ser necesario. 

Si un TaskTracker falla o se produce un timeout, esta parte del trabajo se replanifica en otro TaskTracker.
Finalmente, en caso de que sea necesario, los TaskTrackers puede compartir información.

### Apache 1.0.

Este diagrama muestra la configuración típica de un sistema basado en Apache Hadoop 1.0. Como se observa, cada nodo o servidor aloja un componente del sistema de cómputo, TaskTracker, y un componente del sistema de almacenamiento, Datanode. La idea es llevar el cómputo donde están almacenados los datos que precisan estas tareas generadas por el JobTracker.

![](/img/computacion/apache1.png)


En este diagrama se muestra la composición de componentes en el caso de contar con Apache Hadoop 2.0.


![](/img/computacion/apache2.png)

En primer lugar, los clientes solicitan recursos al componente ResourceManager donde a su vez, residirá el componente NameNode, que forma parte del sistema de almacenamiento HDFS. 

En el componente ApplicationMaster es donde residirán nuestros JobTracker, en caso de usar Apache Hadoop. Los ApplicationMasters son específicos de cada framework de procesamiento y, por lo tanto, MapReduce es solo una de las posibilidades. 

En este caso, contaremos con dos ApplicationMaster distintos, y sobre cada uno de ellos, ejecutaremos una aplicación distinta. Finalmente, en los nodos esclavos desplegaremos el componente NodeManager que se encargará de gestionar los recursos de cada nodo en forma de contenedores. En estos nodos esclavos, convivirá tanto el cómputo como el almacenamiento, en forma de contenedores o DataNodes.

### Comparación entre versiones

La mayor diferencia entre las versiones 1 y 2 de Apache Hadoop es la incorporación del sistema YARN, de las siglas en inglés Yet Another Resource Negociator. En YARN nos permite ofrecer un sistema multi-usuario y multi-aplicación dentro de Hadoop.

![](/img/computacion/comparacion_versiones.png.png)

 Además,facilita el despliegue de distintos tipos de aplicaciones, como aplicaciones basadas en procesamiento batch, interactivas o en streaming o pseudo tiempo real.
