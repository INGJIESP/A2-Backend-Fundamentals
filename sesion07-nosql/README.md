# NoSQL y MongoDB

## OBJETIVOS

Que el alumno comprenda los beneficios y desventajas de una base de datos no estructurada

Que el alumno instale y ejecute comandos de MongoDB

## Requerimientos

Terminal de Linux

## DESARROLLO

En sus inicios el prefijo "No" significó negación, pero pronto evolucionó a "Not Only". Por lo tanto, con las bases de datos NoSQL podemos definir una base de datos con una estructura fija o hacerla relacional... o no.

### SQL vs NoSQL

* **Simplicidad de diseño**

Al no requerir un esquema que limite el contenido de nuestras tablas o colecciones, es posible empezar simple e ir evolicionando \(sin tener que copir, borrar, volver a crear\) poco a poco nuestra arquitectura de datos. Ideal para un MVP y metodología ágiles

* **Esquemas dinámicos**

Las bases de datos relacionales requieren que se defina un esquema con tipos de datos para cada tabla antes de empezar a ingresar registros, las bases de datos NoSQL **no**.

La manera en que se desarrolla software ha cambiado mucho desde que se desarrollaron las bases de datos SQL. Ahora, no se tienen requerimientos perfectamente delimitados y etapas largas de desarrollo \(años\), más bien se tienen requerimientos básicos y ciclos cortos, por lo tanto agilidad para cambiarlos dependiento de cómo vayan evolucionando.

La flexibilidad es arma de doble filo: por un lado puede permitir que nuestra arquitectura de datos evolucione o no sea necesaria, pero por otro lado puede llegar a ser dificil de mantener \(Hay maneras de poner estructura via esquemas, pero es opcional\). Se podría decir que se sacrifica la **consistencia** en pro de la velocidad de desarrollo y la flexibilidad de evolución, pero en realidad esa consistencia se obtiene eventualmente en otras capas de la arquitectura \(Ej. utilizando Mongoose\)

* **Capacidad de guardar no sólo tipos de datos simples \(string, int, date, etc\), sino también datos complejos \(arreglos, objetos, funciones, grafos\)**

Para guardar una relación `uno-muchos` ya no es necesario crear una tabla relación, como en SQL. Las bases de datos NoSQL permiten guardar arreglos, simplificando así los queries y evitando los "JOIN hells". También es posible guardar objetos JSON y/o funciones de Javascript.

* **Escalamiento horizontal \(clusters\)**

A diferencia de las principales bases de datos SQL, que requieren escalamiento vertical \(más procesamiento, más almacenamiento en un mismo servidor o configuraciónes complejas de Sistemas Distrubuidos\), algunas bases de datos NoSQL están diseñadas para automáticamente multiplicarse en distintos servidores e interconectarse, a esto se le llama **Auto-shardiing**. Esto permite que el poder de procesamiento pueda fácilmente expandirse sin necesidad de un nuevo diseño.

* **La mayoría son Open Source**

Permite así que una comunidad afín tenga la capacidad de colaborar y verificar el desarrollo de estas tecnologías.

* **Ideales para la Programación Orientada a Objetos**

### Tipos de bases de datos SQL

* **Document databases** Pares de llaves \(**key**\) con estructuras de datos complejos: **Documentos**. Pueden ser datos simples, arreglos o incluso documentos anidados. Ej. **MongoDB**, CouchDB, ElasticSearch
* **Graph stores** Se usan para guardar datos de redes interconectadas, por ejemplo: conexiones de redes sociales, mapas, información organizada. Ej. AllegroGraph, Giraph, Neo4j
* **Key-value** Son las más simples de las bases de datos NoSQL. Similiarmente a un diccionario, guardan datos en pares de llaves \(**keys**\) y sus valores primitivos \(**values**\). Ej. Redis, Ignite, OrientDB
* **Wide-column stores** tienen la capacidad de hacer consultas \(**queries**\) sobre grandes cantidades de datos. Se utilizan para ciencias de datos. Ej. Cassandra, DynamoDB, Druid

### MongoDB

La más popular de las bases de datos NoSQL es MongoDB y es la que usaremos en el curso. Escogimos esta base de datos por su amplia documentación, por su activa comunidad y porque ocupa la misma sintaxis que Javascript para realizar consultas.

[Ejemplo 1: Instalación de MongoDB](ejemplo-01.md)

[Ejemplo 2: Crea carpeta para almacenar bases de datos](ejemplo-02.md)

#### Comparaciódata-analysis-1n de terminos entre MariaSQL y MongoDB

```text
TABLE = COLLECTION

ROW = DOCUMENT

COLUMN = FIELD

JOIN = $lookup o embedded docuemnts
```

> [Aquí](https://docs.mongodb.com/manual/reference/sql-comparison/) puedes leer más sobre esto

#### Levandar ambiente de desarrollo

[Ejemplo 3: Levanta el servicio o **deamon** de MongoDB](ejemplo-03.md)

[Ejemplo 4: Abrir el cliente de MongoDB \(CLI\)](ejemplo-04.md)

#### Comandos básicos

> Los siguientes ejemplos se correrán dentro del Cliente \(CLI\) de MongoDB

**Configuración de base de datos a usar**

[Ejemplo 5: Mostrar bases de datos existentes](ejemplo-05.md)

[Ejemplo 6: Cambiar/Crear base de datos](ejemplo-06.md)

**Inserción y creación**

[Ejemplo 7: Crear una nueva colección insertando un nuevo documento](ejemplo-07.md)

[Reto 1: Crea una nueva base de datos con una nueva colección e inserta 3 documentos](reto-01.md)

[Ejemplo 8: Insertar un nuevo documento con un campo con un arreglo](ejemplo-08.md)

[Ejemplo 9: Insertar un nuevo documento con un campo con un subdocumento](https://github.com/beduExpert/A2-Backend-Fundamentals-Expert/tree/b6372027b4f4c925d723a517f723b2e12085d98d/Sesion07-NoSQL/Ejemplo-9/README.md)

[Reto 2: Agrega 3 documentos con campos con arreglos y objetos](reto-02.md)

**Lectura y filtrado**

[Ejemplo 10: Ejecutar un **query** para leer todos documentos de una colección](ejemplo-10.md)

[Ejemplo 11: Ejecutar un **query** para leer filtrando documentos de una colección](ejemplo-11.md)

[Reto 3: Ejecuta un query para filtrar usando como condición la pertenencia a un arreglo](reto-03.md)

[Reto 4: Filtra los documentos según un campo en un subdocumento](reto-04.md)

**Modificación y eliminación de documentos**

[Ejemplo 12: Modificar, según cierta condición, uno o varios documentos de una colección](ejemplo-12.md)

[Reto 5: Modifica un documento de tu colección](reto-05.md)

[Ejemplo 13: Borrar, según cierta condición, uno o varios documentos de una colección](ejemplo-13.md)

**Referencias / Relaciones**

[Ejemplo 14: Agregar un documento con un campo que haga referencia a otro documento](ejemplo-14.md)

[Reto 6: Agrega otra colección e inserta un documento que tenga una campo que haga referencia al ObjectId de la primera colección](reto-06.md)

[Reto 7: Averigua en la documentación de MongoDB cómo hacer un **query** para introducir el documento que hace referencia, en el resultado \(similar a un JOIN en SQL\)](reto-07.md)

