# elasticsearchStarter


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

## ElasticSearch command

- http://localhost:9200/_aliases   : list of all indices in your cluster
- http://localhost:9200/_cluster/state

## Kibana
- http://localhost:5601/app/discover :  Discover index

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
