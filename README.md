# elastic-course

curl -X PUT "localhost:9200/product?pretty"



curl -X POST "localhost:9200/product/default?pretty" -H 'Content-Type: application/json' -d'
{
  "name": "Processing events with Logstash",
  "instructor": {
  "firstName":"Bo",
  "lastName": "Andersen"
  }
}'


curl -X PUT "localhost:9200/product/default/1?pretty" -H 'Content-Type: application/json' -d'
{
  "name": "Guide to Elasticsearch",
  "instructor": {
  "firstName":"Bo",
  "lastName": "Andersen"
  }
}'

curl -X PUT "localhost:9200/product/default/1?pretty" -H 'Content-Type: application/json' -d'
{
  "name": "Guide to Elasticsearch2",
  "instructor": {
  "firstName":"Bo",
  "lastName": "Andersen"
  }
}'


curl -X GET "localhost:9200/product/default/1"


curl -X POST "localhost:9200/product/default/1/_update" -H 'Content-Type: application/json' -d'
{
  "doc": {
  "price":95
  }
}'

curl -X POST "localhost:9200/product/default/1/_update" -H 'Content-Type: application/json' -d'
{
  "script": "ctx._source.price += 10"
}'



curl -X POST "localhost:9200/product/default/_bulk?pretty" -H 'Content-Type: application/json' --data-binary "@/Users/ernestortuno/Documents/courses/elastic/test-data.json"

{"index":{"_id":1}}
{"name":"Wine - Maipo Valle Cabernet","price":152,"in_stock":38,"sold":47,"tags":["Alcohol","Wine"],"description":"Aliquam augue quam, sollicitudin vitae, consectetuer eget, rutrum at, lorem. Integer tincidunt ante vel ipsum. Praesent blandit lacinia erat. Vestibulum sed magna at nunc commodo placerat. Praesent blandit. Nam nulla. Integer pede justo, lacinia eget, tincidunt eget, tempus vel, pede. Morbi porttitor lorem id ligula.","is_active":true,"created":"2004\/05\/13"}
{"index":{"_id":2}}
{"name":"Tart Shells - Savory","price":99,"in_stock":10,"sold":430,"tags":[],"description":"Pellentesque at nulla. Suspendisse potenti. Cras in purus eu magna vulputate luctus. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vivamus vestibulum sagittis sapien. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Etiam vel augue. Vestibulum rutrum rutrum neque. Aenean auctor gravida sem.","is_active":true,"created":"2007\/10\/14"}
{"index":{"_id":3}}
....

curl -X GET "localhost:9200/_cat/indices?v"

