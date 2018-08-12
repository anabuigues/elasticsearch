# create an index
```
PUT /product
```

# delete an index
```
DELETE /product
```

# create a document
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

# update a document
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

# obtain a document
```
GET product/default/1
```

# update a document
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

# update a document
```
POST /product/default/1/_update
{
  
  "doc": {
    "price":"94",
    "tags": ["Elasticsearch"]
  }
}
```

# scripted updates
```
POST /product/default/1/_update
{
  
  "script": "ctx._source.price += 10"
}
```

# delete a document
```
DELETE product/default/1
```

# upsert
```
POST product/default/1/_update
{
  "script": "ctx._source.price += 10",
  "upsert": {
    "price": 100
  }
}
```

# deleting by query
```
POST /product/default
{
  "name": "Processing Events with Logstash",
  "category": "course"
}

POST /product/default
{
  "name": "The Art of Scalability",
  "category": "book"
}

POST /product/_delete_by_query
{
  "query": {
    "match": {
      "category": "book"
    }
  }
}
```
