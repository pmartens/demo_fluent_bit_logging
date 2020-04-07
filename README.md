# demo_fluent_bit_logging
Small demonstration using Fluent-Bit to forward Docker PHP-FPM and Nginx logs to ElasticSearch

The reason we are not using FileBeat and Logstash is because Fluent-Bit is very very light weight on system resources. We are talking about barely a few KB/MB compared to hundreds of MBs! It has build-in persistence mechanism as well such as memory and filesystem. FileBeat and Logstash solution will require something like Redis for persistence.

## How to start

### Start Monitor enviroment
1. Navigate to `/monitor` and execute the following command:

``` bash
docker-compose up
```

### Start Demo applications
1. Open a new bash screen.
2. Navigate to `/app` and execute the following command:

``` bash
docker-compose build
```

2. If the build is done please exit with `CTRL+c` and execute the following command:

``` bash
docker-compose up
```

### Access 
|Service|Url|
|---|---|
|Kibana|http://localhost:5601|
|ElasticHQ|http://localhost:5000|
|Demo Application|http://localhost:8080|

### Commands
You can use `$ curl -X GET 0.0.0.0:9200/_cat/indices` to list all indexes and `$ curl -X GET 0.0.0.0:9200/wait/_search` to see the content of `wait` index. 