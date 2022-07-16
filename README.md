# elasticsearchStarter

##  Docs
- https://auth0.com/blog/spring-boot-logs-aggregation-and-monitoring-using-elk-stack/
- https://www.elastic.co/fr/downloads/beats/filebeat
- http://www.andrew-programming.com/2018/09/18/integrate-springboot-application-with-elk-and-filebeat/

## ElasticSearch command

- http://localhost:9200/_aliases   : list of all indices in your cluster
- http://localhost:9200/_cluster/state

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
