# Metric aggregations

## Calculating statistics with `sum`, `avg`, `min`, and `max` aggregations
Size es 0 porque en este caso no nos interesan los resultados, solamente los agregados.

```
GET /order/default/_search
{
  "size": 0,
  "aggs": {
    "total_sales": {
      "sum": {
        "field": "total_amount"
      }
    },
    "avg_sale": {
      "avg": {
        "field": "total_amount"
      }
    },
    "min_sale": {
      "min": {
        "field": "total_amount"
      }
    },
    "max_sale": {
      "max": {
        "field": "total_amount"
      }
    }
  }
}
```

## Retrieving the number of distinct values
Realiza un count sobre el atributo para distintos valores

```
GET /order/default/_search
{
  "size": 0,
  "aggs": {
    "total_salesmen": {
      "cardinality": {
        "field": "salesman.id"
      }
    }
  }
}
```

## Retrieving the number of values

```
GET /order/default/_search
{
  "size": 0,
  "aggs": {
    "values_count": {
      "value_count": {
        "field": "total_amount"
      }
    }
  }
}
```

## Using `stats` aggregation for common statistics

```
GET /order/default/_search
{
  "size": 0,
  "aggs": {
    "amount_stats": {
      "stats": {
        "field": "total_amount"
      }
    }
  }
}
```