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
