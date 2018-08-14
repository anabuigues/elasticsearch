# Using the `_analyze` API

## Tokenizing text with the `standard` tokenizer

```
POST _analyze
{
  "tokenizer": "standard",
  "text": "I'm in the mood for drinking semi-dry red wine!"
}
```

## Using the `lowercase` token filter

```
GET _analyze
{
  "tokenizer" : "keyword",
  "filter" : ["lowercase"],
  "char_filter" : ["html_strip"],
  "text" : "I'm in the mood for drinking semi-dry red wine!"
}
```

## Using the `standard` analyzer

```
POST _analyze
{
  "analyzer": "standard",
  "text": "I'm in the mood for drinking semi-dry red wine!"
}
```