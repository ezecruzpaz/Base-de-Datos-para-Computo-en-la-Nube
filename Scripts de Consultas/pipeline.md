## `Pipeline 2` hecho en clase con 2 stages

`Agrupación y Ordenamiento`:

Este pipeline agrupa los documentos por la editorial y cuenta cuántos documentos hay en cada grupo, luego los ordena por el número de documentos.

Explicación:

`$group`: Agrupa los documentos por la editorial y cuenta cuántos documentos hay en cada grupo.

`$sort`: Ordena los resultados por el número de documentos en orden ascendente.

```javascript
[
  {
    $group:
      /**
       * _id: The id of the group.
       * fieldN: The first field name.
       */
      {
        _id: "$editorial",
        "Numero Documentos": {
          $count: {},
        },
      },
  },
  {
    $sort:
      /**
       * Provide any number of field/order pairs.
       */
      {
        "Numero Documentos": 1,
      },
  },
]
```

## `Pipeline 3` hecho en clase con 2 stages

`Agrupación, Cálculo de Medias y Ordenamiento`

Este pipeline agrupa los documentos por la editorial y calcula el número de documentos, la media de los precios y el precio máximo en cada grupo, luego los ordena por el precio máximo.

Explicación:

`$group`: Agrupa los documentos por la editorial y calcula el número de documentos, la media de los precios y el precio máximo en cada grupo.

`$sort`: Ordena los resultados por el precio máximo en orden ascendente.

```javascript
[
  {
    $group:
      /**
       * _id: The id of the group.
       * fieldN: The first field name.
       */
      {
        _id: "$editorial",
        "Numero de Documentos": {
          $count: {},
        },
        media: {
          $avg: "$precio",
        },
        "Precio Maximo": {
          $max: "$precio",
        },
      },
  },
  {
    $sort:
      /**
       * Provide any number of field/order pairs.
       */
      {
        "Precio Maximo": 1,
      },
  },
]
```

## `Pipeline 4 con out` hecho en clase con 2 stages

`Agrupación, Cálculo de Medias y Salida a una Colección`

Este pipeline es similar al anterior, pero además de calcular la media de los precios, redondea la media a dos decimales y guarda los resultados en una nueva colección llamada "Media_Editoriales".

Explicación:

`$group`: Agrupa los documentos por la editorial y calcula el número de documentos y la media de los precios.

`$set`: Redondea la media de los precios a dos decimales.

`$out`: Guarda los resultados en una nueva colección llamada "Media_Editoriales".

```javascript
[
  {
    $group:
      /**
       * _id: The id of the group.
       * fieldN: The first field name.
       */
      {
        _id: "$editorial",
        Numero: {
          $count: {},
        },
        media: {
          $avg: "precio",
        },
      },
  },
  {
    $set:
      /**
       * field: The field name
       * expression: The expression.
       */
      {
        "Media Total": {
          $trunc: ["$media", 2],
        },
      },
  },
  {
    $out:
      /**
       * Provide the name of the output collection.
       */
      "Media_Editoriales",
  },
]
```

## `Pipeline 5 con unset y count` hecho en clase con 4 stages

`Agrupación, Cálculo de Medias, Eliminación de Campo y Count`

Este pipeline es similar al anterior, pero además de calcular la media de los precios, elimina el campo "media" y cuenta cuántos documentos hay en cada grupo.

Explicación:

`$group`: Agrupa los documentos por la editorial y calcula el número de documentos y la media de los precios.

`$set`: Redondea la media de los precios a dos decimales.

`$unset`: Elimina el campo "media" de los resultados.

`$count`: Cuenta cuántos documentos hay en cada grupo.

```javascript
[
  {
    $group:
      /**
       * _id: The id of the group.
       * fieldN: The first field name.
       */
      {
        _id: "$editorial",
        Numero: {
          $count: {},
        },
        media: {
          $avg: "precio",
        },
      },
  },
  {
    $set:
      /**
       * field: The field name
       * expression: The expression.
       */
      {
        "Media Total": {
          $trunc: ["$media", 2],
        },
      },
  },
  {
    $unset:
      /**
       * Provide the name of the output collection.
       */
      "media",
  },
]
```
Espero que te sirva :wink: :computer: :100:

Por: Benjamin Peña Marin :sunglasses: :+1:



















