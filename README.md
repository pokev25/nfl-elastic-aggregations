# NFL Elasticsearch Aggregations

This repository contains the files for the [data visualization tutorial](http://www.elasticsearch.org/blog/data-visualization-elasticsearch-aggregations/) using Elasticsearch aggregations (1.0 release) and D3.


# for ES 5.2.0
Fire up Elasticsearch from your localhost. Now, let's add an index and some data. From the terminal:

```
curl -XPUT "localhost:9200/nfl?pretty"
curl -XPUT "localhost:9200/nfl/2013/_mapping?pretty" -d @nfl_mapping.json
curl -XPOST "localhost:9200/nfl/2013/_bulk?pretty" --data-binary @nfl_2013.json
```

[fielddata set true](https://www.elastic.co/guide/en/elasticsearch/reference/5.2/fielddata.html)

```
curl -XPUT "localhost:9200/nfl/_mapping/2013?pretty" -d'
{
  "properties": {
    "description": {
      "type":     "text",
      "fielddata": true
    }
  }
}'
```
