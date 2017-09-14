## Logagent Plugin: Apache Kafka

Input plugin for [@sematext/logagent](http://sematext.com/logagent/). The plugin acts as message consumer for Apache Kafka.
Install @sematext/logagent npm packge: 

```
npm i -g @sematext/logagent 
npm i -g logagent-input-kafka
```
 
### Configuration

```
# Global options
options:
  includeOriginalLine: false

input:
  kafka: 
    module: logagent-input-kafka
    kafkaHost: localhost:9092
    groupId: ExampleTestGroup
    topic: test
    autoCommit: true
    sessionTimeout: 15000
    sslEnable: false
    #For init sslOptions please refer to to https://nodejs.org/api/tls.html
    sslOptions: 
      - rejectUnauthorized: false
    
output:
  stdout: yaml # use 'pretty' for pretty json and 'ldjson' for line delimited json (default)
  elasticsearch: 
  	module: elasticsearch
  	url: http://localhost:9200
  	index: test

```

Start logagent

```
logagent --config logagent-kafka-input.yaml
```

## Contributions

Original author: [Filippo Balicchia](https://github.com/fbalicchia) logagent-js [PR#75](https://github.com/sematext/logagent-js/pull/75) [PR#77](https://github.com/sematext/logagent-js/pull/77) [PR#81](https://github.com/sematext/logagent-js/pull/81)

