# Source filtering

Lo utilizamos cuando no necesitemos devolver todo el contenido del documento.

## Excluding the `_source` field altogether
Ningún campo del documento.

```
GET /recipe/default/_search
{
  "_source": false,
  "query": {
    "match": { "title": "pasta" }
  }
}
```

## Only returning the `created` field
Solamente el campo created del documento.

```
GET /recipe/default/_search
{
  "_source": "created",
  "query": {
    "match": { "title": "pasta" }
  }
}
```

## Only returning an object's key

```
GET /recipe/default/_search
{
  "_source": "ingredients.name",
  "query": {
    "match": { "title": "pasta" }
  }
}
```

## Returning all of an object's keys

```
GET /recipe/default/_search
{
  "_source": "ingredients.*",
  "query": {
    "match": { "title": "pasta" }
  }
}
```

## Returning the `ingredients` object with all keys, __and__ the `servings` field

```
GET /recipe/default/_search
{
  "_source": [ "ingredients.*", "servings" ],
  "query": {
    "match": { "title": "pasta" }
  }
}
```

## Including all of the `ingredients` object's keys, except the `name` key

```
GET /recipe/default/_search
{
  "_source": {
    "includes": "ingredients.*",
    "excludes": "ingredients.name"
  },
  "query": {
    "match": { "title": "pasta" }
  }
}
```