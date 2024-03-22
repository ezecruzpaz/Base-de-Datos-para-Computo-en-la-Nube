
## `insertOne` en MongoDB

### Descripción
Inserta un solo documento en una colección de MongoDB.

### Sintaxis
```javascript
db.collection.insertOne(<documento>)
```

## `db.nombreDeLaColeccion.find()` en MongoDB

### Descripción
Recupera documentos de una colección que coincidan con ciertos criterios de consulta.

### Sintaxis
```javascript
db.nombreDeLaColeccion.find(<consulta>, <proyección>)
```

Ejemplo:
```javascript
db.miColeccion.find({}, { _id: 0, campo1: 1, campo2: 1 })
```

## `db.dropDatabase()` En MongoDB

### Descripción
Elimina una base de datos.

### Sintaxis
```javascript
db.dropDatabase('nombreDeLaDataBase')
```


Ejemplo:
```javascript
db.dropDatabase('mydatabase')
```

## `db.nombreDeLaColeccion.insertMany([{  }])` en MongoDB

### Descripción
Inserta múltiples documentos en una colección.

### Sintaxis
```javascript
db.nombreDeLaColeccion.insertMany([
   { documento1 },
   { documento2 },
   ...
])
```
Ejempño:
```javascript
db.miColeccion.insertMany([
   { campo1: "valor1", campo2: "valor2" },
   { campo1: "valor3", campo2: "valor4" }
])
```
## `db.libros.find({ })` En MongoDB

### Descripción
Recupera un solo documento de una colección que coincida con ciertos criterios de consulta.
### Sintaxis
```javascript
db.nombreDeLaColeccion.find({ <filtro> })
```
Ejemplo:
```javascript
db.libros.find({ autor: "Gabriel García Márquez" })
```

Ejemplo:
```javascript
db.libros.find({ año_publicación: { $gte: 1990 } })
```


## `db.nombreDeLaColeccion.findOne()` en MongoDB

### Descripción
El método `findOne()` se utiliza en MongoDB para recuperar un solo documento de una colección que coincida con ciertos criterios de consulta.

### Sintaxis
```javascript
db.nombreDeLaColeccion.findOne(<consulta>, <proyección>)
```


Ejemplo: 
```javascript
db.miColeccion.findOne({ campo: "valor" }, { _id: 0, campo1: 1, campo2: 1 })
```

## `db.nombreDeLaColeccion.updateOne()` en MongoDB

### Descripción
Actualiza un solo documento en una colección que coincida con ciertos criterios de consulta.

### Sintaxis
```javascript
db.nombreDeLaColeccion.updateOne(
   <filtro>,
   <actualización>,
   {
      upsert: <boolean>,
   }
)
```
Ejemplo: 
```javascript
db.miColeccion.updateOne(
   { nombre: "Ejemplo" },
   { $set: { edad: 30 } },
   { upsert: true }
)
```

## `db.nombreDeLaColeccion.updateMany()` en MongoDB

### Descripción
Actualiza múltiples documentos en una colección que coincidan con ciertos criterios de consulta.

### Sintaxis
```javascript
db.nombreDeLaColeccion.updateMany(
   <filtro>,
   <actualización>,
   {
      upsert: <boolean>,
   }
)
```

Ejemplo: 
```javascript
db.miColeccion.updateMany(
   { tipo: "A" },
   { $set: { cantidad: 100 } },
   { upsert: true }
)
```
## `db.nombreDeLaColeccion.deleteOne()` en MongoDB

### Descripción
El método `deleteOne()` se utiliza en MongoDB para eliminar un solo documento de una colección que coincida con ciertos criterios de consulta.

### Sintaxis
```javascript
db.nombreDeLaColeccion.deleteOne(<filtro>)
```


Ejemplo:
```javascript
db.miColeccion.deleteOne({ nombre: "Ejemplo" })
```

## `db.nombreDeLaColeccion.deleteMany()` en MongoDB

### Descripción
El método `deleteMany()` se utiliza en MongoDB para eliminar múltiples documentos de una colección que coincidan con ciertos criterios de consulta.

### Sintaxis
```javascript
db.nombreDeLaColeccion.deleteMany(<filtro>)
```
Ejemplo:
```javascript
db.miColeccion.deleteMany({ tipo: "A" })
```

## `db.nombreDeLaColeccion.replaceOne()` en MongoDB


### Descripción
Este documento ha sido simplificado para una fácil comprensión de los métodos y su sintaxis en MongoDB.




