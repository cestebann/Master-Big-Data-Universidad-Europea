# Arquitecturas Cloud Computing

Miguel Torres Porta
- Data Scientist at Cognizant


# Contenidos 

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

## Distribución 

Lab 1 - Finales de febrero | 20%
Lab 2 - Mediados de marzo  | 20% 
Test / Examen Lab | 25/03  | 60%

Grupos de 3 ó 4 personas    


# ¿Qué es el cloud computing? 

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

## Concpetos importantes de Cloud

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

