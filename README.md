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


curl -X GET "localhost:9200/product/default/1?pretty"
