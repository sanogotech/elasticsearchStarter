# elasticsearchStarter

## Concepts

![All Beats](https://github.com/sanogotech/elasticsearchStarter/blob/main/docs/images/beats-logstash.jpg)

## ELK Docker

- https://github.com/sanogotech/docker-elk-basic

## When to Use Filebeat and When to Use Logstash?

- Filebeat is considered one of the best log shippers as it is lightweight, supports SSL & TLS encryption, and is extremely reliable. However, it cannot transform the logs into easy-to-analyze structured data. 
That's the part performed by Logstash.

- So, if you require advanced log enhancement like filtering out unwanted bits of data or transforming data to another format, you have to go for Logstash.

- But if you are only interested in the timestamp and message content, you can choose Filebeat to act as your log aggregator, especially in a distributed environment.

- Filebeat can either ship data directly to Elasticsearch or first to Logstash, and then Logstash can ingest this data to Elasticsearch. If you want to use the benefit of Filebeat and Logstash, you can very well go with the second approach.
##  Docs
- https://auth0.com/blog/spring-boot-logs-aggregation-and-monitoring-using-elk-stack/
- https://www.elastic.co/fr/downloads/beats/filebeat
- https://blog.lsonline.fr/2020/07/17/how-to-request-and-expose-your-elasticsearch-engine-for-your-ghost-blog/
- http://www.andrew-programming.com/2018/09/18/integrate-springboot-application-with-elk-and-filebeat/
- https://www.elastic.co/fr/support/matrix#show_compatibility
- https://www.elastic.co/guide/en/beats/filebeat/current/filebeat-modules.html
- https://www.elastic.co/guide/en/beats/filebeat/current/configuration-filebeat-options.html
- https://medium.com/@ketan.bhadoriya/how-to-create-a-custom-index-name-in-filebeat-68151138e090
## ElasticSearch command

- http://localhost:9200/_aliases   : list of all indices in your cluster
- http://localhost:9200/_cat/indices : it will display all the indexes that have ever been created inside elasticsearch
- http://localhost:9200/_cluster/state
- http://localhost:5601/app/management/kibana/indexPatterns

## Kibana
- http://localhost:5601/app/discover :  Discover index

## Logstash /Beats
- https://www.javainuse.com/elasticsearch/filebeat-elk
- https://www.javainuse.com/grok  : Online Grok Pattern (+120 pattern)
- https://www.elastic.co/guide/en/elasticsearch/reference/7.8/dissect-processor.html

## There are various Beats for different purposes:

- Filebeat: For file monitoring
- Metricbeat: For metrics monitoring
- Packetbeat: For network data monitoring
- Heartbeat: For uptime monitoring

```
 sudo ./filebeat -e -c filebeat.yml
```

* filebeat.yml
```yml
filebeat.inputs:
  - type: log
    enabled: true
    paths:
        - /ELK/logs/application.log  # Make sure to provide the absolute path of the file

output.elasticsearch:
  hosts: ["localhost:9200"]
  protocol: "http"
  
  ```
## Annexes

![All Beats](https://github.com/sanogotech/elasticsearchStarter/blob/main/docs/images/beats.jpg)


https://github.com/sanogotech/elasticsearchStarter/blob/main/docs/images/beatsELK.jpg