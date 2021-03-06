# Managing Documents

## create an index
```
PUT /product
```

## delete an index
```
DELETE /product
```

## create a document
```
POST /product/default
{
  "name": "Learning elasticsearch",
  "instructor": {
    "firstName": "Ana",
    "lastName": "Buigues"
  }
}
```

## update a document
```
PUT /product/default/1
{
  "name": "Learning elasticsearch con id",
  "instructor": {
    "firstName": "Ana",
    "lastName": "Buigues"
  }
}
```

## obtain a document
```
GET product/default/1
```

## update a document
```
PUT /product/default/1
{
  "name": "Learning elasticsearch con id",
  "instructor": {
    "firstName": "Ana",
    "lastName": "Buigues"
  },
  "price" : 234
}
```

## update a document
```
POST /product/default/1/_update
{
  
  "doc": {
    "price":"94",
    "tags": ["Elasticsearch"]
  }
}
```

## scripted updates
```
POST /product/default/1/_update
{
  
  "script": "ctx._source.price += 10"
}
```

## delete a document
```
DELETE product/default/1
```

## upsert
```
POST product/default/1/_update
{
  "script": "ctx._source.price += 10",
  "upsert": {
    "price": 100
  }
}
```

## deleting by query
```
POST /product/default
{
  "name": "Processing Events with Logstash",
  "category": "course"
}
```

```
POST /product/default
{
  "name": "The Art of Scalability",
  "category": "book"
}
````

```
POST /product/_delete_by_query
{
  "query": {
    "match": {
      "category": "book"
    }
  }
}
```

# Batch processing
### adding documents

```
POST /product/default/_bulk
{ "index": { "_id": "100" } }
{ "price": 100 }
{ "index": { "_id": "101" } }
{ "price": 101 }
```

### updating and deleting documents

```
POST /product/default/_bulk
{ "update": { "_id": "100" } }
{ "doc": { "price": 1000 } }
{ "delete": { "_id": "101" } }
```

### retrieving affected documents

```
GET /product/default/100
```

```
GET /product/default/101
```