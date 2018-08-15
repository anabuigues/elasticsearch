# Exercises

## Please write a query searching for the sentence `pasta with parmesan and spinach` within the `title field, simulating that this sentence was entered by a user within a search field.

```
GET /recipe/default/_search
{
  "query": {
    "match": {
      "title": "Pasta with parmesan and spinach"
    }
  }
}
```

## Please write a query searching for phrase `pasta carbonara` within the `title` field.

```
GET /recipe/default/_search
{
  "query": {
    "match_phrase": {
      "title": "pasta carbonara"
    }
  }
}
```

## Please write a query searching for the terms `pasta` or `pesto` within the
title` and `description` fields.

```
GET /recipe/default/_search
{
  "query": {
    "multi_match": {
      "query": "pasta pesto",
      "fields": [ "title", "description" ]
    }
  }
}
```