# Arquitecturas Cloud Computing

Profesor: Miguel Torres Porta
- Data Scientist at Cognizant

## Distribución de la calificación

- Lab 1 - Finales de febrero | 20%
- Lab 2 - Mediados de marzo  | 20% 
- Test / Examen Lab | 25/03  | 60%

Grupos de 3 ó 4 personas    

# Contenido del curso

Unidad 1. Plataformas y Modelos de Servicio Cloud
- Sistemas distribuidos
- Modelos de servicios en la nube
- Aspectos económicos y ventajas de la computación en la nube.
- Escalabilidad
Unidad 2. Infraestructura para computación en la nube
- Virtualización
- Contenedores
- Infraestructura de red y sistemas de almacenamiento
- Plataformas y Servicios
Unidad 3. Gestión de la infraestructura en Plataformas Cloud
- Componentes básicos de diseño.
- Arquitecturas Cloud e Híbridas.
- Seguridad en sistemas cloud
- Responsabilidad Compartida

# Objetivos

## Competencias específicas:
- Diseñar y aplicar algoritmos de análisis basados en sistemas e infraestructuras de almacenamiento y acceso a grandes volúmenes de datos.
- Aplicar las bases técnicas del funcionamiento de plataformas cloud computing y virtualizadas.
## Resultados de aprendizaje:
- Comparación y contraste críticos de múltiples modelos de sistemas distribuidos y sus tecnologías habilitantes asociadas.
- Realizar diferentes tipos de niveles de virtualización, estructuras y herramientas en sistemas Cloud.

# Unidad 1. Plataformas y Modelos de Servicio Cloud

## ¿Qué es el cloud computing? 

Conjunto de recursos virtuales compartidos bajo demanda, que ofrecen servicios de computación, almacenamiento, bases de datos y redes. Estos servicios pueden ser desplegados rápidamente y a escala.

- Computación: El cerebro de la carga de trabajo. 
- Almacenamiento: La bodega de los datos. 
- Bases de datos: Almacenamiento de conjuntos de datos estructurados. 
- Red: Servicios que permiten la conectividad y comunicación entre recursos. 

## Modelos Cloud

- **Cloud pública** Un proveedor ofrece infraestructura, bajo demanda. 
    - El hardware no está físicamente disponible y no se conoce la posición exacta de esto. 
    - El proveedor ofrece todo el mantenimiennto del hardware. 
- **Cloud privada**: La infraestructura es privada y gestionada por la empresa.
    - El hardware suele estar "on-premises".
- **Híbrida** 
    - Puede ser usada para casos de recuperación en en casos de desastres  o una migración. 
    - Normalmente usadas durante cortos periodos de tiempo. 

## Conceptos importantes de Cloud

- Recursos bajo demanda
- Escalabilidad
- Economía de escala
- Pago por uso
- Flexibilidad y elasticidad
- Alta disponibilidad
- Growth 
- Seguridad

![](/img/arquitectura/onpremises-cloud.png)

![](/img/arquitectura/arquitecturas_cloud.png)

![](/img/arquitectura/cuotas_mercado.png)

![](/img/arquitectura/AWS_foundations.png)


## 1.1. Sistemas distribuidos

### Objetivos 
- Analizar el concepto de sistemas distribuidos
- Introducir el concepto básico de clúster y sistemas mallados
- Introducir el concepto de computación en la nube

### 1.1.1. Sistemas distribuidos

![](/img/arquitectura/tipos%20de%20sistemas.png)

**Sistemas centralizados**: son aquellos en los que todos los recursos del sistema, como memoria, procesadores, discos, etc., están contenidos en una sola entidad física y son gestionados por un único sistema operativo, este tipo de sistema podría a su vez formar parte de un sistema distribuido o de nube.

**Sistemas para multiprocesamiento simétrico (SMP)** se caracterizan por tener varios procesadores que compiten en igualdad de condiciones por el acceso a una memoria principal, de forma que cualquier procesador ejecute cualquier tarea sin importar en qué lugar o bloque de memoria se encuentra almacenada esta tarea. La mayoría de los procesadores actuales permiten SMP siempre y cuando tengamos un sistema operativo debidamente configurado para ello


**Sistemas para procesamiento masivamente paralelo**: se caracterizan en cambio por tener cientos o miles de procesadores que disponen de su propia memoria, así como de su correspondiente copia de sistema operativo, lo que permite que ejecuten tareas de forma simultánea.

Las máquinas que permiten **procesamiento vectorial** su utilizan para aplicaciones multimedia, así como de criptografía o compresión, sus procesadores se basan en ejecutar conjuntos de instrucciones como si fuesen vectores de números lo que permite alcanzar altas velocidades de procesamiento, compañías que fabrican este tipo de máquinas son Cray, Fujitsu o Nec y su uso es también restringido a laboratorios de investigación.

**Los sistemas distribuidos** se componen de varios sistemas computacionales autónomos, cada uno de los cuales tiene sus propios elementos de procesamiento, memoria y su sistema de almacenamiento, estando conectados entre ellos a través de una red de comunicaciones de datos. El sistema en su conjunto debe aparecer ante el usuario como un único sistema.

### 1.1.2. Sistemas tipo clúster 

Un cluster consiste en un grupo de ordenadores de relativo bajo costo conectados entre sí mediante un sistema de nred de alta velocidad y un software que realiza la distribución de la carga de trabajo entre los equipos. 
Por lo general, este tipo de sistemas cuentan con un centro de almacenamiento de datos único. Los clusters tienen la ventaja de ser sistemas redundantes, al estar fuera de servicio el procesador principal, el segundo se dispara y actúa como un Fail Over.

![](/img/arquitectura/sistemas_tipo_clusters.png)

### 1.1.3. Sistemas tipo grid 

La computación en grid es un nuevo paradigma de computación distribuida en el cual todos los recursos de un     número indeterminado de ordenadores son englobados para ser tratados como un único superordenador de manera   transparente. 

Estos ordenadores englobados no están enlazados firmemente, es decir no tienen por qué estar en el mismo lugar geográfico.

Su punto de seguridad es delicado en este tipo de computación distribuida pues las conexiones se hacen de       forma remota y no local, entonces suelen surgir problemas para controlar el acceso a los otros nodos; aunque la red no va a dejar de funcionar porque uno falle.

![](/img/arquitectura/sistemas_grid.png)

#### Diferencias con los clústers

En un clúster todos los nodos se encuentran en el mismo lugar, conectados por una red local para así englobar todos los recursos.  En cambio, en un grid no tienen por qué estar en el mismo espacio geográfico: pueden estar en diferentes puntos del mundo. 

#### 1.1.2.1.Clústeres más importantes

1. Beowulf (1994)
2. Centro de Supercomputación de Barcelona (2004)
3. Mare Nostrum 4 (2017)

#### 1.1.2.2. Entornos para la creación de clústeres

- Open Mosix
- HT Condor
- OpenSSI
- Linux-HA

### 1.1.3. Sistemas distribuidos tipo grid

conjunto de recursos distribuidos e interconectados por una red, estos recursos están a disposición de los usuarios y se asemeja a lo que sería una red de suministro eléctrico con un único punto de acceso a los elementos distribuidos en regiones geográficas diferentes.

### 1.1.4. Sistemas Peer to Peer (P2P)

En un sistema distribuido entre pares, P2P.

Cada nodo actúa como un cliente y servidor al mismo tiempo, proporcionando parte de recursos al sistema. Las máquinas son simplemente ordenadores, en la mayoría de los casos de tipo personal, conectadas a internet.

En este tipo de sistema no hay relación maestro-esclavo existente entre pares. No se necesita una coordinación central ni tampoco una base de datos centralizada. En otras palabras, ninguna máquina par tiene una vista global de todo el sistema P2P. El sistema es autoorganizado.

A diferencia del clúster o la malla, una red P2P no dispone de una red de interconexión dedicada. La red física es simplemente una red ad hoc formada en varios dominios de internet utilizando los protocolos TCP/IP por lo que la red varía en tamaño y topología dinámicamente.

![](/img/arquitectura/sistemas_p2p.png)

#### 1.1.4.1. Clasificación 

- Compartir contenidos digitales (música, videos, etc.), como Gnutella, Napster y BitTorrent, entre otras.
- Realizar actividades colaborativas incluyendo aplicaciones tipo chat como Messenger o Skype.
- Aplicaciones específicas de tipo científico o académico. 

### 1.1.5. Sistemas de Computación en la Nube

Trabajar con grandes conjuntos de datos implicará, en el futuro cercano, enviar los programas a las máquinas que contienen los datos, en lugar de copiar los datos a las estaciones de trabajo, esto refleja una tendencia en la industria de las Tecnologías de la Información que consiste en mover tanto los procesos computacionales como los datos desde ordenadores de escritorio o estaciones de trabajo a grandes centros de datos, donde existe una provisión bajo demanda de software, hardware y datos como servicios.

> "Una nube es un conjunto de recursos computacionales virtualizados que puede albergar una variedad de cargas de trabajo diferentes, incluidos trabajos por lotes, así como aplicaciones”. - IBM

Un sistema de computación en la nube es también capaz de monitorear el uso de los recursos en tiempo real para permitir el balance de cargas de trabajo cuando sea necesario, es lo que se denomina la “computación elástica”.

En todo caso, **la idea general subyacente es mover la computación sobre máquinas de escritorio a una plataforma orientada a servicios, utilizando clústeres de servidores y enormes sistemas de almacenamiento en centros de datos ubicados en zonas geográficas distintas.**

#### 1.1.6. Ventajas de la computación en la nube

La computación en la nube nos ofrece acceso a hardware y a aplicaciones a un coste razonable que incluye el hecho de pagar solo por aquello que utilicemos.

- **Ubicación de los centros de datos** en áreas con espacio protegido y mayor eficiencia energética. La capacidad de cómputo se comparte entre una gran cantidad de usuarios, mejorando la efectividad global.
- Separación de las **tareas de mantenimiento de infraestructuras** y enfoque en el desarrollo de aplicaciones específicas.
- Reducción significativa del coste de la computación, en comparación en la nube con los paradigmas de computación tradicionales.
- Proporciona almacenamiento de datos elásticos y distribución de contenidos y servicios.
- Privacidad, seguridad, derechos de autor y confiabilidad.

## 1.2. Modelos de Servicios en la Nube

### Objetivos 

- Describir los diferentes tipos de sistemas de computación en la nube existentes.
- Describir los diferentes tipos de modelos de servicio que puede ofrecer la nube.

### 1.2.1. Nubes públicas, privadas e híbridas

La computación en la nube es un paradigma de computación de alto rendimiento (HTC) mediante el cual la infraestructura proporciona los servicios a través de un centro de datos, o bien, de lo que se conoce como granjas de servidores.

#### 1.2.1.1. Nubes públicas

Una nube pública se crea utilizando la infraestructura de red de internet y puede acceder a ella cualquier usuario que haya pagado por un servicio determinado.

Las nubes públicas son propiedad de los proveedores de servicios y se puede acceder a ellas a través de una suscripción que incluye información de facturación, etc.

#### 1.2.1.2. Nubes privadas 

Una nube privada se crea dentro del dominio de una intranet propiedad de una única organización, por lo tanto, es propiedad y es gestionada por sus dueños y su acceso está limitado a los propietarios y sus socios.

#### 1.2.1.3. Nube híbrida

Una nube híbrida se genera mediante una combinación entre nubes públicas y privadas. Las nubes privadas también pueden soportar un modelo de nube híbrida al complementar su infraestructura local con capacidad informática residente en una nube pública externa.

### 1.2.2. Modelo de coste en una nube

En un entorno de informática tradicional, los usuarios deben adquirir:
- su propio ordenador 
- equipo periférico 
- asumir los costos de la obra civil para la instalación del equipo 
- los gastos operacionales (electricidad, etc)
- el mantenimiento del sistema informático
- costes de personal
- servicios auxiliares

### 1.2.3. Infraestructura como servicio (IaaS)


Un usuario puede implementar y ejecutar sus aplicaciones sobre un entorno de procesamiento elegido y que tiene unas características determinadas, pero no administra ni controla la infraestructura subyacente en la nube, sí tiene control sobre el sistema operativo, el almacenamiento, las aplicaciones instaladas en la máquina y componentes de red.

![](/img/arquitectura/cloud_as_a_service.svg)


En el caso de Amazon Web Services (AWS), uno de los proveedores de recursos de nube más conocidos, la Infraestructura como Wervicio se presta a través de clústeres de máquinas virtuales que se denominan EC2 (Elastic Cloud Computing) mientras que el almacenamiento se denomina Amazon Simple Storage Service o S3.

Una vez que tenemos operativa nuestra instancia de computación podremos acceder a ella a través de una dirección IP pública utilizando como protocolo SSH (Secure Shell).

### 1.2.4. Plataforma como Servicio (PaaS)

Si queremos ser capaces de desarrollar, desplegar y gestionar la ejecución de aplicaciones utilizando recursos de la nube sin preocuparnos por las licencias ni la aplicación de revisiones para los sistemas operativos y las bases de datos, necesitamos de una plataforma que nos proporcione un entorno de software que incluya sistemas operativos, así como librerías de soporte, incluyendo entornos y modelos de programación, etc., por ejemplo, en el caso de AWS disponemos de una PaaS denominada Amazon Elastic MapReduce en la que podemos disponer de un modelo de programación distribuido del tipo Map Reduce, incluyendo herramientas como lenguajes de programación Java, Phyton, etc., y que podemos usar para procesamiento de datos o aplicaciones de comercio electrónico.

La plataforma incluye todos los componentes necesarios para el desarrollo de aplicaciones basadas en este modelo de programación, el usuario únicamente se encarga de definir el tipo de procesamiento deseado y proporcionar los datos requeridos para ello, en el caso de Microsoft Azure se dispone de herramientas .NET o Microsoft Visual Studio que nos permite desarrollar aplicaciones para empresa o para Web. 

![](/img/arquitectura/paas.png)

### 1.2.5. Software como Servicio (SaaS)

Software como servicio (SaaS) es el modelo de servicio en la nube más completo desde el punto de vista del producto. Con SaaS, básicamente la que hace es alquilar o usar una aplicación totalmente desarrollada. El correo electrónico, el software financiero, las aplicaciones de mensajería y el software de conectividad son ejemplos comunes de una implementación de SaaS.

Saas cambia la forma en que se ofrecen aplicaciones a los clientes. En el modelo de software tradicional, el software se entrega como un producto basado en licencia que debe instalarse en el dispositivo del usuario final. En el caso del SaaS el software se entrega como un servicio bajo demanda a través de internet, no es necesario instalar el software en los dispositivos del usuario final. 

Se puede acceder a los servicios de SaaS desde cualquier navegador web en cualquier dispositivo, como ordenadores personales, portátiles, tabletas y teléfonos inteligentes. Ejemplos conocidos de servicios tipo SaaS incluyen por ejemplo Google Gmail o Google Docs, Microsoft Share Point o Software tipo CRM disponible en salesforce.com.

#### 1.2.5.1. Aplicaciones de una plataforma SaaS

- Servicios empresariales: CRM, ERP.
- RRSS
- Gestión de documentos
- Servicios de correo 

#### 1.2.5.2. Beneficios de una plataforma SaaS

La utilización de plataformas SaaS nos aporta los siguientes beneficios:
- **Menor mantenimiento de las aplicaciones** los servicios de SaaS eliminan la sobrecarga adicional de mantener el software desde el lado del cliente. En el modelo de desarrollo de software tradicional, el usuario final es responsable de realizar actualizaciones masivas, sin embargo, en el caso de una plataforma SaaS, el propio proveedor de servicios mantiene las actualizaciones automáticas, la supervisión y otras actividades de mantenimiento de las aplicaciones.
- **Facilidad de acceso**, ya que se puede acceder a los servicios de SaaS desde cualquier dispositivo si está conectado a internet. La accesibilidad de los servicios de SaaS no está restringida a ningún dispositivo en particular. Es adaptable a todos los dispositivos, ya que únicamente se requiere de un navegador.
- **Escalado dinámico**, es muy difícil para las aplicaciones en local disponer de capacidad de escalado dinámico (trabajar con más datos o atender a más usuarios de forma concurrente) ya que se requiere hardware adicional. Dado que los servicios SaaS aprovechan los recursos provistos por la infraestructura de nube, podemos manejar cualquier tipo de carga de trabajo sin alterar el comportamiento normal de la aplicación.
- **Recuperación de desastres mediante mecanismos de copia de seguridad y recuperación adecuados**, se mantienen réplicas para cada servicio de SaaS. Las réplicas se distribuyen en muchos servidores. Si algún servidor falla, el usuario final puede acceder a la plataforma SaaS a través de otros servidores. Elimina el problema del punto único de falla. También asegura la alta disponibilidad de la aplicación.






# 23/02/23

## Elastic Compute Cloud (EC2)

EC2 permite desplegar servidores virtuales en tu enorno AWS. Con las siguientes características: 
- Amazone Machine Image: Plantillas de instancias EC2 preconfiguradas. Es un punto de partida para crear una máquina con un SO y aplicaciones junto con cualquier configuración personalizada. 
- Tipos de instancias: Tamñao de la instancia. Tipo procesador, velocidad...
- Opciones de compra: On demand (más común), reserva, programada, sport (unused). 

### Almacenamiento
- Persistente -> Volúmenes EBS. Están conectados de manera lógica a trabés de la red. Se puede desconectar y mantener los datos. 
- Efímero (Almacenamiento local) --> Físicamente conectados a la instancia. Cuando la máquina se para o se elimina, se pierden los datos. Con la excepción de reiniciar. 

### Seguridad 
 - Security Groups: Firewall de seguridad. Reglas de entradas y salida de tráfico. 
 - Key Pairs: Claves de acceso. 
 - Es responsabilidad de la empresa o del usuario mantener y actualizar las instancias, como se indica en el modelo de responsabilidad compartida. 

## Elastic Block Storage (EBS)
- Almacenamiento persistente para instancias EC2. 
- Ofrecen mayor flexibilidad con los datos. 
- Son independientes. 
- Están conectados de manera lógica. 
- Un volumen solo puede estar conectado a una instancia. Pero una instancia puede tener muchos volúmenes. 
- Posibilidad de realizar backups (almacenados en S3). 
- Tipos: SSD (más rápidos, pero más caros), HDD (mayor capacidad). 
- Seguridad: Cifrado disponible automático con AWS KMS (AES-256). 

## Elastic Files System 
### Storage Services 
- Sistema de almacenamietno de archvios. 
- Permite la conexción de múltiples instancias en única instancia a través de los puntos de montaje. 

