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
- $in: Es un operador de consulta que se utiliza para encontrar documentos donde el valor de un campo coincida con cualquiera de los valores especificados en una lista. La sintaxis básica del operador $in es la siguiente: { campo: { $in: [valor1, valor2, ..., valorN] } }
- upsert: Es una banderilla para el metodo updateOne/all. Con esto se puede insertar o actualizar un documento. Si no existe lo inserta, si existe lo actualiza.
- $eq y $ne: Son operadores de comparación en MongoDB. El operador $eq se utiliza para comparar si un campo es igual a un valor específico. El operador $ne se utiliza para comparar si un campo no es igual a un valor específico. Ejemplo:

```
db.usuarios.find({ edad: { $eq: 30 } })
db.usuarios.find({ edad: { $ne: 30 } })
```

