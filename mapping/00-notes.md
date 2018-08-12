# Mappings
* Los mapping se utilizan para definir cómo se deben e almacenar e indexar los documentos y sus campos
	* Qué campos deben tratarse como campos de texto completo
	* Qué campos contienen números, fechas, ubicaciones

* No estamos obligados a definir mapping, ya que elastic tiene la característica de dynamic mapping. Es capaz de detectar fechas, números, texto

* Un atributo puede tener más de un mapeo, por ejemplo los de tipo texto, tienen el type text y también se les puede asociar un conjunto de keywords

# Meta Fields
* \_index: contains the name of the index to which a documents belongs
* \_id: stores the ID of documents
* \_source: contains the original JSON object used when idexing a document
* \_field_names: contains the names of every field that contains a non-null value
* \_routing: stores the value used to route a document to a shard
* \_version: stores the internal version of a document
* \_meta: may be used to store a custom data that is left untouched by elasticsearch

# Fields data types
* *Core data type*: primitive data type as seen in programming languages e.g string etc..
* *Text data type*: used to index full-text value such as descriptions. Values are analyzed
* *Keyword data type*: used for structured data (tags, categories, email addresses). Not analyzed. Tipically used for filtering and aggregations.
* *Numeric data types*: basic numeric data types, most of which are found in varios programming languages (float, long, integers, double...)
* *Date data type*: represents dates as either a string, long or integer. The data format may be configured
* *Boolean data type*: stores boolean values
* *Binary data type*: accepts a Base64 encoded binary value. Not stored by default
* *Range data type*: used for range values such as date ranges or numeric ranges. e.g (10-30) integer_range, {"gte": 10, "lte": 20}
* *Complex data type*: data types that are not primitive, but are more complex in nature e.g. arrays and objects
* *Object data type*: added as JSON objects, stored as key-value pairs internally. May contains nested objects
* *Array data type*: not an actual data type, because each field may contain multiple values by default
* *Array of objects*: associations between object values are lost
* *Nested data type*: specialized version of the object data type. Enables arrays of objects to be querified independently of each other
* *Geo data type*: data types that are used for geographical data
* *Geo-point data type*: accepts latitude-longitude pairs. Used for various geographicals operations
* *Specialized data type*: data types with a very specific purpouse, e.g. storing IP address
* *Completion data type*: used to provide auto-completion ("search-as-you-type") functionality. Optimized for quick lookups
* *Attachment data type*: requires the Ingest Attachment Processor Plugin. Used to make text from various documents formats searchable. Uses Apache Tika internally for text recognition

# Mappings parameters
Visit: 
[Mapping Params](https://www.elastic.co/guide/en/elasticsearch/reference/current/mapping-params.html)
[Date formats](https://www.elastic.co/guide/en/elasticsearch/reference/current/mapping-date-format.html#built-in-date-formats)
[Custom date formats](http://www.joda.org/joda-time/apidocs/org/joda/time/format/DateTimeFormat.html)


















