# Contenido del curso 

0. [Objetivos del curso](https://github.com/cestebann/Master-Big-Data-Universidad-Europea/blob/master/Gobernanza.md#objetivos-del-curso)
1. [Gobierno del Dato](https://github.com/cestebann/Master-Big-Data-Universidad-Europea/blob/master/Gobernanza.md#1-gobierno-del-dato)
- [Introducción al Gobierno del Dato](https://github.com/cestebann/Master-Big-Data-Universidad-Europea/blob/master/Gobernanza.md#11-introducci%C3%B3n-al-gobierno-del-dato)
- [Glosario, Diccionario y Catálogo de Datos](https://github.com/cestebann/Master-Big-Data-Universidad-Europea/blob/master/Gobernanza.md#12-glosario-de-negocio-diccionario-de-datos-y-cat%C3%A1logo-de-datos)
- [Gestión de Metadatos y Linaje Técnico.](https://github.com/cestebann/Master-Big-Data-Universidad-Europea/blob/master/Gobernanza.md#objetivos-del-curso)
- [Gestión de la Calidad de Datos y Seguridad del Dato](https://github.com/cestebann/Master-Big-Data-Universidad-Europea/blob/master/Gobernanza.md#14-gesti%C3%B3n-de-la-calidad-de-datos-y-seguridad-del-dato)
2. Modelos de gobernanza
- Gestión de Datos Maestros (MDM) y Datos de Referencia.
- Marcos y Estándares del gobierno del dato
- Estrategia, Roles y Ámbitos de Actuación.
- Herramientas de gobierno del dato
3. Ciclo de Vida del Dato
- Gestión del Ciclo de Vida del Dato
- Gestión del Valor del Dato.
- Gestión de Modelos de Aprendizaje Automático en producción (MLOps).
- Herramientas de operativa de modelos MLOps.


# Objetivos del curso

## Competencias específicas

- Analizar y argumentar los agentes del mercado, empresas y tecnologías que participan en
el sector del análisis de grandes volúmenes de datos en infraestructuras distribuidas.
-  Integrar, implantar y explorar aplicaciones de análisis de datos en plataformas de altas
prestaciones, incluyendo la privacidad y la protección de los datos.

## Resultados del Aprendizaje

- Modelar, diseñar e implantar modelos de gobernanza del dato.
- Definir el ciclo de vida del dato en función del negocio o caso de uso de aplicación

# 1. Gobierno del dato

## 1.1. Introducción al gobierno del dato

### Objetivos de la lección 

- Contexto actual en la gestión de datos por parte de las organizaciones.
- Conceptos generales de qué es un gobierno del dato.
- Conceptos generales sobre los principios de un gobierno del dato.
- Fundamentos sobre principales ventajas y desventajas.

### 1.1.1. Contexto actual en la gestión del dato 

Según Statista, el volumen de datos creados, capturados, copiados y consumidos en todo el mundo en 2025, será de 181 zeta bytes, lo que se duplicarían todos los datos mundiales en apenas 4 años.

Debemos prepararnos para la gestión adecuada de todos estos datos, que debemos estimar que en las próximas décadas podrían llegar a cientos de miles o millones de zeta bytes. ¿Estamos preparados para dicha gestión? ¿Disponemos de metodologías al respecto? ¿Cómo podríamos dar respuesta para poner orden en todo este desorden anárquico digital? ¿Qué hacemos con la falta de microchips de procesadores que existe en el mercado actual? ¿Cuántos más datos mejor o peor? ¿Es sostenible este crecimiento?

#### 1.1.1.1. Crecimiento de los datos abiertos

Data Sharing: término definido por el Centro de Apoyo al Intercambio de Datos como: “recopilación de prácticas, tecnologías, elementos culturales y marcos jurídicos que son pertinentes para las transacciones en cualquier tipo de información en formato digital, entre distintos tipos de organizaciones”.

### 1.1.2. ¿Qué es un Gobierno del dato?

### 1.1.2.1. Definición

> "El Gobierno de Datos es el ejercicio de la autoridad y el control (planificación, el seguimiento y la aplicación) a través de la gestión de los activos de datos. La función de Gobierno de Datos sirve de guía de cómo se llevan a cabo todas las demás funciones de gestión de datos. El Gobierno de Datos es de alto nivel y administra ejecutivamente los datos”. - Asociación Internacional de Gestión de Datos, DAMA.

> “El mapeo de los derechos de decisión y la posterior creación de un marco de responsabilidad para garantizar que se adoptan los comportamientos adecuados en la evaluación, producción, consumo y control de los datos y las prácticas analíticas relacionadas”. - Gartner

> "“el proceso por el que una organización formaliza un deber fiduciario para gestionar los activos de datos críticos para su éxito” - Forrester

#### 1.1.2.2. Áreas del gobierno de datos

- Gestión de arquitectura de datos.
- Gestión de desarrollo de datos.
- Gestión de operación de base de datos.
- Gestión de seguridad de datos.
- Gestión de datos maestro y de referencia.
- Gestión de almacén de datos e inteligencia de negocio.
- Gestión de documentos y contenido.
- Gestión de metadatos.

#### 1.1.2.3. Responsabilidades del gobierno del dato

Los datos no son propiedad de las áreas de tecnologías de la información, sino que deben ser considerados como un activo estratégico de la organización.

El área de gobierno del dato es la autoridad y tiene las competencias sobre las gestión del dato, su calidad, metadatos, seguridad, utilización y distribución, entre otras, sin competencia directa sobre los sistemas tecnológicos en los que se encuentran alojados.

**Data steward**: En ellos recae la responsabilidad de que se asegure el control y uso de datos de manera eficiente en las organizaciones por áreas de negocio.
- Es un perfil perteneciente al área en cuestión.
- Tiene un alto grado de conocimiento funcional sobre los datos.
- Es el encargado de gestionar y administrar los datos correspondientes a su área de experiencia y conocimiento.

### 1.1.3. Principios del Gobierno del Dato

1. **Gobernanza normativa:** Desarrollo y mantenimiento de las políticas, estándares, normativas, comités de gestión del dato de alto nivel.
2. **Gobernanza técnica:** Desarrollo y mantenimiento de los metadatos, linaje técnico, calidad y seguridad de los datos, entre muchos otros, y todo lo relacionado con la gestión de datos desde el comienzo de flujo de datos desde la fuente de origen hasta la llegada de los datos al área funcional de la compañía.
3. **Gobernanza funcional:** Desarrollo y mantenimiento de la gestión de los datos, desde la llegada a su área funcional o de negocio hasta la utilización por el usuario final, facilitando el entendimiento de los mismos mediante *diccionario de datos*, *glosario y catálogos de datos*, así como las personas autorizadas para su consulta.


### 1.1.3.1. Objetivos del Gobierno del Dato

1. Útil
2. Focalizado al negocio y no a Tecnologías de Información
3. Iterativo
4. Decentralizado y no centralizado
5. Centrado en el empleado
6. Sin parálisis burocráctica

## 1.2. Glosario de negocio, diccionario de datos y catálogo de datos

- Conceptos generales sobre qué es y cómo actúa un glosario de negocio.
- Conceptos generales sobre qué es y cómo actúa un diccionario de datos.
- Conceptos generales sobre qué es y cómo actúa un catálogo de datos. 
- Conceptos generales de cómo implementar estas tres piezas en un gobierno del dato dentro de las organizaciones.

### 1.2.1. Glosario de negocio

**Glosario de negocio:** un listado de términos y definiciones que contextualizan y ayudan a las organizaciones a establecer conocimiento de negocio y definir los datos en todas las unidades de la organización y a todas las terceras partes externas a la organización.

Un glosario de negocio ayuda a evitar confusiones y a crear un lenguaje común para que todas las personas conozcan y utilicen los mismos términos a la hora de referirse a un dato y a un elemento derivado del dato de la misma manera en toda la organización.

#### 1.2.1.1. Engranajes del Glosario de negocio

1. Términos de negocio. 
2. Datos de referencia. 
3. Políticas y estándares. 
4. Clasificación de términos

#### 1.2.1.2. Alfabetización de datos

> Alfabetización de datos: “la capacidad de leer, escribir y comunicar datos en contexto, incluida la comprensión de las fuentes y construcciones de datos, los métodos analíticos y las técnicas aplicadas, y la capacidad de describir el caso de uso, la aplicación y el valor resultante”. - Gatner. 

1. Comprensión de los datos:
2. Visibilidad de los datos
3. Colaboración con los datos
4. Búsqueda de los datos
5. Gobernanza de los Datos: El glosario de negocio, junto al diccionario de datos y catálogos de datos, actúa como herramientas para implementar un gobierno del dato de manera exitosa en las organizaciones.


### 1.2.2. Diccionario de datos

> **El diccionario de datos**: es una herramienta que recoge información técnica a nivel de conjunto de datos y de campos de datos, como por ejemplo el nombre físico, ID, sistema, tabla, formato, etc. Esta información se utiliza para contextualizar y ayudar a la correcta identificación de los datos dentro de las áreas de negocio u organizaciones.

El diccionario de datos está compuesto por conjuntos de metadatos usados por los perfiles técnicos de la organización, identificando donde es necesario acceder a la información en cada momento.

El **Technical Data Steward** y otros puestos de tecnologías de la información son el rol responsable del  diccionario de datos debido a  sus capacidades que les permiten interpretar los metadatos. 

>**Metadatos**: "Los metadatos son información que describe varias facetas de un activo de información para mejorar su usabilidad a lo largo de su ciclo de vida. Son los metadatos los que convierten la información en un activo. En términos generales, cuanto más valioso es el activo de información, más crítico es administrar los metadatos sobre él, porque es la definición de metadatos la que proporciona la comprensión que desbloquea el valor de los datos”.

### 1.2.2.1. Ejemplo de diccionario de datos
#### 1.2.2.2. Beneficios del diccionario de datos

1. Elimina documentación 
2. Búsquedas de datos rápidas
3. Detalles de características de datos: permite conocer casuísticas y detalles relevantes de los datos a través de los metadatos, y también permite conocer los flujos de procesos en los sistemas de información a través de diferentes artefactos y su frecuencia a través de todos esos procesos, generando un conocimiento exhaustivo del ciclo de vida de los datos a través de todos y cada uno de sus registros.
4. Visión de alto nivel en la gestión: 
conocer la índole de las transacciones llevadas a cabo por los sistemas de información y conocer qué área de negocio se encuentra más digitalizada y en qué nichos se concentran las operaciones de dichos sistemas y correspondientes datos. También permite conocer el volumen de datos en cada sistema de información y estimar su capacidad de procesamiento y almacenaje de datos, anticipando y previendo posibles fallos en los procesos.

### 1.2.3. Catálogo de datos 

El catálogo de datos es un directorio único y transversal a toda la organización, que pretende ser utilizado para buscar los datos como activos clave, disponiendo de todos los metadatos de cada dato y su correspondiente trazabilidad con el glosario de negocio y con el diccionario de datos. 

Si una de estas tres piezas faltara en una organización, las otras dos piezas perderían gran valor y quedarían infrautilizadas. 

Es preciso disponer de un catálogo de datos para generar sinergias entre todas las áreas interesadas en los datos en cuestión, mejorando la operativa del negocio, con los respectivos etiquetados de seguridad, ya que en muchas ocasiones no debe permitirse el visionado de todos los datos en el catálogo, debido a que las organizaciones deben someterse y aplicar las normativas vigentes en materia de datos, según su criticidad y contenido.


#### 1.2.3.1. Aplicación del catálogo de datos en las organizaciones 

Existen dos tipos de estrategias para para implementar la estrategia, según el tipo de organización: 
- Organizaciones tradicionales en la gestión del dato. 
- Organizaciones disruptivas en la gestión del dato. 

## 1.3. Gestión de Metadatos y Linaje Técnico 

### Objetivos

Los objetivos que se pretenden alcanzar en este recurso son los siguientes:
- Conceptos generales sobre qué es y cómo influye la gestión de metadatos.
- Conceptos generales sobre qué es y por qué es importante el linaje técnico.

### 1.3.1. Gestión de los metadatos

La gestión de metadatos está compuesta por la generación, el almacenamiento, la vinculación y la supervisión de los metadatos en los sistemas de información. 

La gestión de metadatos es una tarea dominada por las políticas y estándares del marco de los gobiernos del dato.

**Los metadatos son conceptos que reflejan la información que existe alrededor de los datos y muestran las transacciones de su ciclo de vida a través de los flujos en los sistemas de información.**

#### 1.3.1.1. Tipos de metadatos

- Metadatos técnicos: hacen referencia principalmente a donde están alojados los datos.
  - Identificación de campos de las fuentes de datos de origen.
  - Nomenclaturas de tablas de datos, los datos claves PK, índices de tablas, formatos de los campos, etc.
  - Metodología de las copias de seguridad para la recuperación de datos.
  - Versiones e iteraciones que han sufrido los datos.
- Metadatos funcionales:hacen referencia principalmente a los conceptos y terminologías de negocio.
  - Descripción de los términos de negocio.
  - Reglas de negocio aplicadas y a la calidad de los datos.
  - Indicadores de la calidad de datos de negocio.
  - Datos por los que está comos.puesto un cuadro de mando.
  - Fechas de carga y creación de los datos.
- Metadatos operativos
  - Transformaciones en los procesos de los datos, conocido como linaje técnico y tiempo de ejecución.
  - Fechas de los últimos cambios realizados en los datos.
  - Calendarización de los procesos de transformación y almacenamiento.
  - Usabilidad de acceso de los usuarios, frecuencia de uso por los usuarios y horas de mayor uso de los datos.
- Metadatos adminsitrativos
  - Personas responsables de la custodia de datos, como por ejemplo los Data Business Steward.
  - Usuarios que han accedido a los datos.
  -  Responsabilidades y políticas sobre los datos.
  - Etiquetado de datos sobre características y peculiaridades de los mismos.
  - Leyes, regulaciones y normativas sobre el tratamiento y la gestión del dato.

#### 1.3.1.3. Arquitectura de metadatos

Los tres enfoques arquitectónicos para el desarrollo del repositorio de metadatos global son la arquitectura de metadatos centralizada, la arquitectura de metadatos descentralizada y la arquitectura de metadatos híbrida.

1. Arquitectura de metadatos centralizada: la arquitectura centralizada dispone de un único repositorio de metadatos con la información correspondiente a todos los sistemas de información.
2.  Arquitectura de metadatos descentralizada: la arquitectura distribuida dispone de un único punto de acceso que conecta con los diferentes repositorios de metadatos, sin un repositorio persistente.
3. Arquitectura híbrida:  la arquitectura híbrida es una mezcla entre la arquitectura centralizada y la arquitectura descentralizada, que traslada los metadatos directamente de los sistemas de información a un repositorio común de manera persistente.

#### 1.3.1.4. Los beneficios de los metadatos

1. **Mejora la toma de decisiones** respecto a los datos, al disponer de mayor información sobre el entorno de cada dato, potenciando su valor y aumentando el Data Value.
2. **Disminuye los costes de personal y horas trabajadas**, al eliminar toda la documentación compleja y utilizando herramientas de gobierno de los datos más eficaces y con recopilación activa de metadatos, eliminando la maraña documental.
3. **Apoya en la indagación sobre características relevantes y de gran importancia sobre los datos**, disminuyendo el tiempo de estudio para llegar a la conclusión u obtener mayor información sobre los datos.
4. **Reduce el gap de conocimiento, colaboración y comunicación entre las partes de áreas de sistemas de la información y las áreas funcionales o de negocio**, aumentando la credibilidad y seguridad sobre los datos por esta última parte y agilizando las tareas técnicas de la primera parte.
5. **Reduce el Time-To-Market de los desarrollos de productos de datos con plazos de entrega más cortos**, ciclos de vida más cortos y análisis de incidencias más cortos.
6. **Detecta y ayuda a eliminar tablas, flujos y datos duplicados en procesos redundantes, así como a eliminar datos obsoletos y sin uso** por parte de la organización, ayudando a eliminar el síndrome de Diógenes de datos. 

### 1.3.2. Linaje técnico

La mayoría de organizaciones utilizan datos de diferentes sistemas de información y necesitan trasladarlos en diferentes softwares. En estos casos, para planificar la migración de los datos a su destino debemos conocer con claridad el mapeo de los datos.

> El linaje o trazabilidad de datos es la materialización de los metadatos técnicos en un formato visual que permite dibujar un mapa que traza el origen del dato, sus transformaciones y el destino. 

Aportan valor mediante el análisis de impacto y visibilidad del dato en el proceso end to end. 
Facilita una mejor gobernabilidad, calidad y cumplimiento regulatorio.
Es una herramienta con gran potencial para los usuarios, ya que pueden realizar un análisis de impacto detallado tanto en los datos ascendentes, como en los descendentes.

#### 1.3.2.1. Operativa de la gestión de de metadatos del linaje técnico 

las herramientas de gobierno son capaces de conectarse, escanear y representar de forma autónoma, lo que les permite convertirse en trabajos donde hay poca intervención humana. 

- Origen: Fuente junto con el nombre del dataset del que proviene el dato. 
- Tranformación: Contempla todos los componentes técnicos asociados. 
- Destino:Fuente junto con el nombre del dataset hacia donde el dato viaja.

#### 1.3.2.2. Obtención del linaje técnico

Podemos utilizar las siguientes técnicas

1. **Relaciones entre objetos**: obtener el linaje técnico a través de las relaciones entre objetos, las cuales vienen representadas a través de los metadatos. Esto es habitual en procesos de ETL
2. **Código fuente:** obtener el linaje técnico a través del código fuente no es fácil de llevar a cabo y tiene una gran dependencia de las capacidades del perfil técnico asignado y del lenguaje de programación
3. **Registros:** obtener el linaje técnico a través de los registros, integrando de forma nativa los repositorios de datos y las herramientas activando funciones como archive-log, para comprender y capturar la información de la metadata en los registros generados por los sistemas de información.

#### 1.3.2.3. Beneficios de una correcta gestión del linaje técnico

1. Mejora el conocimiento de la morfología de los flujos de datos a lo largo de toda la organización.
2. Mejora la comprensión de la cadena de valor de los datos en toda la organización.
3. Mejora la comprensión del ciclo de vida de los datos en toda la organización.
4. Identifica las dependencias entre datos y procesos a lo largo del flujo de datos para la mejora de la gestión y actualizaciones.
5. Proporciona una búsqueda de fallos en los procesos, problemas asociados a la calidad de los datos, etc.


## 1.4. Gestión de la Calidad de Datos y Seguridad del Dato

### Objetivos


Conceptos generales sobre las principales definiciones de calidad del dato.
1. Conceptos generales sobre metodologías de controles de calidad.
2. Conceptos generales sobre la implementación de reglas de calidad de datos.
3. Conceptos generales sobre la monitorización de calidad de datos.

Sesión 4. 9/12/2022

De acuerdo con investigaciones de las consultoras internacionales Experian plc y Clear Strategic IT Partners, estiman que los costes de datos incorrectos suponen entre el 15% y el 25% de los ingresos para la mayoría de las organizaciones.

Disponer de una buena gestión de datos y unos datos de calidad en los repositorios de la organización se ha convertido en una obligación, más que en un requisito con el creciente almacenamiento y procesamiento de grandes cantidades de datos. 

### 1.4.1. Calidad del dato

> **Calidad del dato** Se refiere al estado de la información cualitativa o cuantitativa. Los datos son de alta calidad si son *aptos para usos previstos en las operaciones, la toma de decisiones y la planificación.* 

!   [](/img/gobernanza/propiedades_calidad_datos.png)


#### 1.4.1.1. Definiciones sobre calidad del dato

- **Regla de calidad**: la regla define la forma funcional de cómo deben estar presentes los datos para servir a los propósitos de las áreas de negocio.
- **Control de calidad:** es la correlación de la regla de calidad con la información real;. Los controles son únicos y mantienen una relación uno a uno respecto a las notas de calidad (las KQI).
- **KQI (nota de calidad)**: un indicador porcentual que establece una nota de calidad en positivo y que explica de manera cuantitativa la adecuación de un dato a una regla de calidad establecida en un determinado sistema. *La agregación de varios KQI de la misma jerarquía permite monitorizar y establecer objetivos la calidad a nivel dato, métrica y reporte*. 
- **Problema de calidad de datos:** son inconsistencias en los datos, según lo definido en las reglas de calidad. Puede surgir en cualquier momento del ciclo de vida de los datos, desde la creación hasta la eliminación.
- **Plan de remediación**: acción correctiva de una inconsistencia de calidad. Pueden ser acciones puntuales de corrección, modificación en los procesos de origen o redefinición/creación de reglas de calidad.
- **Dimensión de calidad:** la dimensión de la calidad hace referencia al tipo o profundiad del control en términos de coherencia, completitud, duplicidad, formato, etc.
- **Perímetro de control:** los conjuntos de datos de objetos a ser perfilados y las localizaciones en el proceso donde deben implementarse.

Ejemplo:

![](/img/gobernanza/google_dataprep.png)

### 1.4.2. Metodología de control de calidad

1. **Perfilado de datos**: proceso de estudio, análisis y creación de resúmenes de datos útiles, siendo generalmente el primer paso crítico para asegurar la calidad de los datos. Esto se restringe únicamente para los atributos críticos o que generan valor. 
2. **Evaluación del perfilado:**  la identificación de los datos críticos y se analizan los resultados de aquellos conjuntos de datos que han obtenido un resultado que se aleja del estándar esperado.
2. **Definición de reglas y controles de calidad:** definición de las pruebas de calidad que se quieren implementar sobre los datos críticos. Se definirán los umbrales o resultados objetivos.
- **Definición de acciones a tomar:** definición de la toma de decisiones desde negocio (avisos, escalar, detener la operación) si un dato rebasa las tolerancias de error admisibles prestablecidos. 
- **Implementación de controles:** una vez validados los controles por los expertos de negocio, se implementan técnicamente en los puntos críticos del proceso, tanto manuales, como automáticos.
- **Diseño de un cuadro de mando:** definición de los cuadros de mando (dashboards), sistemas de alertas y avisos para las áreas de negocio. 
- **Monitorización de resultados:** visualización de los resultados reales de los QKI en reuniones/informes periódicos, que refleja el principal conocimiento sobre el estado de la calidad.
- **Evaluación de resultados:** activación de los planes de remediación, toma de decisiones por los actores poertinentes,  y definición de propuestas de mejoras en base a los resultados obtenidos.
- **Remediación:** Aplicación de las acciones correctivas correspondientes y de las propuestas de mejora, a la vez que se realizan las pruebas de validación correspondientes.

![](/img/gobernanza/metologia_controles.png)

#### 1.4.1.1 Perfilado y Evaluación de los Datos

La principal salida que presenta este proceso son resúmenes de datos (la media, moda, el mínimo, el máximo, el percentil, número de nulos, % de valores atípicos, distribución o la frecuencia) que serán de utilidad para la identificación de bloques de información críticos, así como un primer paso que active acciones básicas de limpieza y tratamiento de datos. 

Adicionalmente, la información obtenida ayuda a identificar si los datos obtenidos y recibidos **son coherentes con lo esperado** y están alineados con los intereses y normas de las diferentes áreas de negocio de la organización.

#### 1.4.1.2. Operativización del perfilado de datos

Para llevar a cabo el proceso de perfilado y evaluación de datos se ejecutan los siguientes pasos:

1. Selección del conjunto de datos
2. Ejecución del perfilado de datos: es una acción automatizada. 
  - Resumen general de tablas
  - Análisis de variables
4. Análisis de resultados: el resultado generado requiere del estudio y análisis del equipo de negocio conocedor de los datos y de los equipos técnicos para detectar inconsistencias. 
  - Análisis de la estructura: Se evalúa la consistencia a nivel de dataset (número de filas/de campos, registros, rangos, campos nulos, etc).
  - Análisis del contenido: máximo, mínimo, cuartiles, media, etc.
  - Análisis de la relación: se aplican técnicas de descubrimiento de relación entre diferentes variables.
6. Categorización de los bloques de información críticos: la identificación de la criticidad de los datos debe etiquetarse, categorizarse en base a los criterios de negocio que apliquen,
7. Priorización de bloques críticos: El objetivo es que se mantenga el foco de la calidad en aquellos datos que son realmente importantes y, además, ayudan a mantener una relación coste-beneficio eficiente.

![](/img/gobernanza/dashboard_monitorizacion.png)

### 1.4.3. Implementación de Reglas de Calidad

La definición de las pruebas de calidad que se quieren implementar empieza con **la identificación y definición de las reglas de negocio** para controlar la calidad de la información gestionada.

Una vez categorizados los datos, según criticidad a través del perfilado, se debe decidir qué se necesita controlar (regla de calidad), cómo se debe controlar (control de calidad) y sobre qué entidad se debe controlar (dato, tabla, métrica, informe, etc.).

#### Reglas técnicas
- Completitud
- Duplicidad 
- Formato: garantizan la tipología de los datos

#### Reglas de negocio: conocimiento funcional del negocio
- Rango
- Coherencia:validan la relación lógica entre dos o más campos
- Distribución/tendencia
- Conciliación 

Con el fin de establecer un marco común de definición de reglas de calidad, se establecen los siguientes pasos para asegurar la correcta identificación, definición e implementación de reglas de calidad.

#### 1.4.3.1. Operativización de las reglas de calidad

1. Identificación de áreas/stakeholders involucrados: se debe localizar a todos los stakeholders productores de datos vinculados con el desarrollo, y que participan y dan soporte en la definición de reglas de negocio.
2. Definición de las reglas de calidad: descripción funcional y técnica de las necesidades de negocio que sirvan como demanda de controles de calidad.
  a. ID Regla de calidad (IDRX): identificador de la regla de calidad.
  b. Descripción: definición funcional de la regla de calidad.
  c. Dimensión de la regla: tipología de la regla (completitud, formato, rango, coherencia, métrica agregada, informe, etc.).
4. Definición de los controles de calidad:acciones que se tienen que llevar a cabo para asegurar el cumplimiento de una regla de negocio. **El resultado de la aplicación del control es el KQI.**
  a. ID control de calidad: identificador del control (IDCX).
  b. Descripción: definición funcional del control.
  c. Departamento responsable: área responsable del control, que identifica el área involucrada para la trazabilidad del control.
  d. Responsable del control: persona responsable del control de calidad.
  e. Tipología: control simple o agregado de otros controles.
  f. Rangos: rango esperado que solo aplica a la dimensión de calidad “Rango”.
  g. Controles asociados: niveles inferiores, solo aplica en controles agregados.
  h. Umbral verde: rango de aceptación.
  i. Umbral ámbar: rango de aviso.
  j. Umbral rojo: rango de alerta.
  k. Acción para tomar: definición de la acción a tomar específica según resultado.
  l. Conjunto de datos del control: conjunto de datos sobre el que se aplica el control.
  m. Tabla del control: tabla sobre la que se aplica el control.
  n. Campo del control: campo sobre el que se aplica el control.
  o. Algoritmo de cálculo: fórmula de cálculo de la nota.
  p. Numerador: número de registros de control simple y sumatorio de indicadores clave de calidad con control agregado.
  q. Denominador: número de registros totales de control simple y número de controles implicados con control agregado.
  r. Indicador clave de calidad (KQI): resultado expresado en % y en positivo.
  s. Periodicidad de cálculo: frecuencia de cálculo.
  
 ### 1.4.4. Monitorización de Calidad de Datos
 
 Para tener disponibles los resultados de los procesos de calidad, se requiere de una visualización que permita monitorizar estos resultados, hacer analítica de los indicadores clave de calidad y accionar los planes de remediación.
 
 #### 1.4.4.1. Metodología de Agrupación de las KQIs
 
Wl proceso de visualización requiere la definición de una metodología de agrupación de las KQI. Este punto es crítico, puesto que permite la agregación y desagregación de indicadores clave de calidad, facilitando a las áreas de negocios un análisis de los problemas de calidad identificados en los cuadros de mando.
 
 El objetivo es dotar a las áreas de negocio identificar ágilmente los problemas de calidad. 

![](/img/gobernanza/agregacion_kqi.png)

#### Controles sobre calidad del dato

![](/img/gobernanza/controles_tipos.png)


# 2. Modelos de gobernanza

## Gestión de Datos Maestros (MDM) y Datos de Referencia

### Definición de datos maestros

Un dato maestro es un dato relevante a la actividad de la compañía y es una fuente de verdad indiscutible (ingresos,)

 > “La administración de datos maestros es el control de los valores de los datos maestros para asegurar el uso consistente, compartido y contextual de la versión de la verdad sobre las entidades esenciales del negocio, en los diferentes sistemas de la empresa” - DAMA

> "**La gestión de datos maestros (MDM)** es una disciplina tecnológica en la que las empresas y los departamentos de TI colaboran para garantizar la uniformidad, la precisión, la gestión, la coherencia semántica y la responsabilidad de los activos de datos maestros compartidos de la empresa."

> "**Los datos maestros** son el conjunto coherente y uniforme de identificadores y atributos ampliados que describen las **entidades principales de la empresa** (como clientes, clientes potenciales, ciudadanos, proveedores, centros, jerarquías y planes de cuentas)”. - Gartner 

### Metodología de la gestión de datos maestros

El procedimiento debe asegurar la gestión, asegurando su actualización y calidad.

Las tres fases principales para la gestión de datos maestros y de las diferentes actividades a llevar a cabo en cada una de ellas para una correcta gestión de datos maestros son las siguientes. 

![](/img/gobernanza/metodologia_datos_maestros.png)

![](/img/gobernanza/golden_record.png)

#### Fase 0. Descubrimiento de datos maestros

![](/img/gobernanza/fase0.descubrimiento_dmaestros.png)

### Beneficios de la gestión de los datos maestros

![](/img/gobernanza/beneficios_dmaestros.png)



## Gestión de Datos de Referencia

> "la administración de datos referenciales es el control del dominio de los valores definidos (también conocido como vocabulario), incluyendo el control sobre los términos estándares, los valores de los códigos y otros identificadores únicos, las definiciones de negocio para cada valor, las relaciones de negocios dentro y entre las listas de los dominios de valores; así como también el uso consistente y compartido de los valores de los datos referenciales relevantes, precisos y **oportunos para la clasificación y categorización los datos**”.- DAMA

### Diferencias entre un Dato de Referencia y Datos Maestros

**IMPORTANTE** Los datos maestros representan términos claves para las áreas de negocio, con datos relacionados con clientes y actividades de negocio. Los datos de referencia representan un conjunto de datos aplicables y obtenidos de los datos maestros.

Son cualquier dato que se utiliza para caracterizar, clasificar y catalogar otros datos, o para relacionar datos con información externa a una organización.

![](/img/gobernanza/proceso_dmaestros.png)

### Beneficios de Datos de Referencias 

![](/img/gobernanza/beneficios_dreferencia.png)

![](/img/gobernanza/ciclo_metadatos.png)



**Sesión 5. 15/12/2022 pendiente**


Sesión 6. 22/12/2022

# Ciclo de vida del dato y modelos analíticos 

## Ciclo de vida del dato

![](/img/gobernanza/ciclo-de-vida.png)

### Tipos de datos

- **Datos calientes.** Se refiere a los datos almacenados en la plataforma por un tiempo determinado y durante ese tiempo nunca se borran. 
- **Datos fríos.** orientado a datos históricos, hacen referencia a los datos de que pasado un tiempo sin uso no requieren ocupar espacio en el almacén de datos calientes, por lo que pasan a un estado de almacenamiento secundario.

## Gestión de Modelos de Aprendizaje Automático (MLOps)

> Es un conjunto de prácticas que tiene como objetivo implementar y mantener modelos de aprendizaje automático en producción de manera confiable y eficiente. La palabra es un compuesto de aprendizaje automático y la práctica de desarrollo continuo de DevOps en el campo de software. 

### Fases de un modelo de aprendizaje automático 

1. **Reprocesamiento de datos.**
2. **Separación del conjunto de datos.**
3. **Entrenamiento del modelo.**
4. **Evaluación del modelo.**
5. **Ajustes de hiperparámetros.**
6. **Evaluación final y despliegue.**

- Matriz de confusión

![](/img/computacion/matriz_confusion.png)

### Elementos de un modelo analítico 

![](/img/gobernanza/elementos_modelo_analitico.png)

### Entrenamiento 

![](/img/gobernanza/entrenamiento.png)

### Ejecución de un modelo analítico

El modelo ya compara datos reales, está ya desplegado

![](/img/gobernanza/ejecucion_m_analitico.png)

### Ciclo de vida de un modelo analítico 

Esta metodología tiene partes en común con las buenas prácticas de devops y es a veces llamada MLOps (Machine Learning Operations), pues estandariza todo el proceso de gestión el ciclo de vida de los proyectos analíticos, dentro de los cuales se generan activos analíticos. También está alineada con las formas de trabajo ágiles, pudiendo ser el objetivo de un sprint el recorrer al menos una vez todo el ciclo e ir mejorando el modelo continuamente, sprint a sprint. El siguiente diagrama ilustra la metodología, poniendo de relieve la naturaleza iterativa del proceso:

![](/img/gobernanza/ciclo-de-vida-m-analitico.png)


### MLflow 

Es una plataforma de código abierto para administrar el ciclo de vida de ML, incluida la experimentación

## Control de versiones 

> El método de git-flow



- El examen son 20 preguntas tipo test. (Son 4 opciones, solo hay una opción correcta )
- No hay factor de corrección.
- Para estudiar el examen lo mejor es estudiar los PDFs. 

