# Que es mongo DB:
Es una DB orientada a documentos y colecciones.
## Colección: 
Podemos verla como si fuera una tabla en un DB relacional.
## Documentos
Podemos verla como si fueran las filas en las tablas relacionales. Es la entidad que queremos almacenar.
## Entidades
Son los "documentos" o "registros". Cada entidad en una base de datos NoSQL se representa mediante un documento o registro que contiene toda la información relacionada con esa entidad. Se representan en formato JSON.
## Listado de operadores:
- $inc: Incrementa el valor de un atributo numérico en una cantidad específica.
- $mul: Multiplica el valor de un atributo numérico por un factor específico.
- $rename: Cambia el nombre de un atributo.
- $set: Asigna un valor específico a un atributo.
- $unset: Elimina un atributo de un documento.
- $min: Actualiza el valor de un atributo con el valor mínimo especificado, sólo si el valor actual es mayor que el valor especificado.
- $max: Actualiza el valor de un atributo con el valor máximo especificado, sólo si el valor actual es menor que el valor especificado.
- $currentDate: Establece el valor de un atributo como la fecha y hora actual.
- $addToSet: Añade un valor a un atributo de tipo conjunto (array), sólo si el valor no existe en el conjunto.
- $pop: Elimina el primer o último elemento de un atributo de tipo conjunto (array). 1 o -1 para inicio/final
- $pull: Elimina un valor específico de un atributo de tipo conjunto (array).
- $push: Añade un valor a un atributo de tipo conjunto (array).
- $pullAll: Elimina varios valores específicos de un atributo de tipo conjunto (array).
- $all: Es un operador de consulta que se utiliza para seleccionar los documentos que contienen un campo que incluye todos los elementos especificados en un array. Ejemplo:
```
    db.productos.find({ tags: { $all: ["frutas", "orgánico"] } })
```
- $in: (Sirve para values(numbers), arrays y objects) Es un operador de consulta que se utiliza para encontrar documentos donde el valor de un campo coincida con cualquiera de los valores especificados en una lista. La sintaxis básica del operador $in es la siguiente: { campo: { $in: [valor1, valor2, ..., valorN] } }
- upsert: Es una banderilla para el metodo updateOne/all. Con esto se puede insertar o actualizar un documento. Si no existe lo inserta, si existe lo actualiza.
- $eq y $ne: Son operadores de comparación en MongoDB. El operador $eq se utiliza para comparar si un campo es igual a un valor específico. El operador $ne se utiliza para comparar si un campo no es igual a un valor específico. Ejemplo:

```
    db.usuarios.find({ edad: { $eq: 30 } })
    db.usuarios.find({ edad: { $ne: 30 } })
```
- $gt: (Mayor que). Se utiliza para seleccionar documentos donde el valor de un campo es mayor que un valor específico. Por ejemplo:
```
    db.usuarios.find({ edad: { $gt: 30 } })
```
- $gte: (Mayor o igual). Se utiliza para seleccionar documentos donde el valor de un campo es mayor o igual que un valor específico. Por ejemplo:
```
    db.usuarios.find({ edad: { $gte: 30 } })
```
- $lt: (menor que) Se utiliza para seleccionar documentos donde el valor de un campo es menor que un valor específico. Por ejemplo:
```
    db.usuarios.find({ edad: { $lt: 30 } })
```
- $lte: (Menor o igual que). Se utiliza para seleccionar documentos donde el valor de un campo es menor o igual que un valor específico. Por ejemplo:
```
    db.usuarios.find({ edad: { $lte: 30 } })
```
- Consulta mixta con operadores de consulta: 
```
    // Traer documentos donde el anno sea mayor o igual que 25 pero menor o igual que 35
    db.inventory.find({annos:{$gte: 25, $lte: 35}})
```


## Otros operadores
- $nin: (no en)
- $and: (y)
- $or: (o)
- $not: (no)
- $exists: (existe)
- $type: (tipo)
- $regex: (expresión regular). Ejemplo:
```
    db.inventory.find({"item.description":{ $regex: /text/ }})
```
- $size: (tamaño). Trae todos los documentos que contengan el numero exacto especificado de valores en un array.
- $elemMatch: Es un operador de consulta que se utiliza para seleccionar documentos que contienen un arreglo que cumple con ciertos criterios específicos.Es importante tener en cuenta que $elemMatch se utiliza cuando se desea especificar múltiples condiciones dentro de un solo elemento de un arreglo. Si se desea especificar condiciones en diferentes elementos del arreglo, se deben utilizar otros operadores de consulta, como $in o $all.

- $expr: Es un operador de agregación que permite utilizar expresiones de agregación en la definición de un pipeline de agregación. El pipeline de agregación es una de las características más poderosas y flexibles de MongoDB, y permite realizar operaciones de procesamiento y análisis de datos avanzadas, sin necesidad de tener que transferir los datos fuera del servidor de base de datos.


Este operador permite utilizar expresiones de agregación en diferentes etapas de un pipeline, como $match, $project, $group, $sort, $skip y $limit. 


## Aggregation Framework
Contiene los operadores ($sort, $skip y $limit), estos operadores pueden servir como estrategias de paginación. Es mucho más grande que el Mono Query Language. Se puede usar para procesar los pipelines, conexiones etc... Es para analizar datos a gran escala. Para usarlo se llama la función .aggregate()

## Projections: 
Las proyecciones son una forma de especificar qué campos de un documento se deben incluir o excluir en una consulta. Es decir, son una manera de seleccionar un subconjunto específico de los datos de un documento para que se muestren en la consulta, en lugar de mostrar todo el documento.


Solo es necesario especificar los que se quieren traer. Con 0 se desactiva y 1 activa.