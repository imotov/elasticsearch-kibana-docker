# Docker files for starting Elasticsearch and Kibana

## Introduction

This docked stack can be used to quickly bring up Elasticsearch and Kibana for local testing.

## Usage

Specify Elasticsearch setup password in `password.txt` file.

Deploy Elasticsearch and Kibana to currently running swarm by running:

```
$ mkdir -p data/elasticsearch data/filebeat data/metricbeat
$ export ELASTIC_PASSWORD=`cat password.txt`; docker stack deploy -c docker-stack.yml elastic-stack
```

After startup you can connect to Elasticsearch at http://127.0.0.1:9200/ and Kibana at http://127.0.0.1:5601/

Don't forget to delete the `password.txt` file.

When done, stop Elasticsearch and Kibana by running:

```
$ docker stack rm elastic-stack
```

To redeploy, remove stack, wait for services to exit and redeploy using command above.

```
$ docker stack rm elastic-stack
$ docker stack ps elastic-stack
```

## Troubleshooting

Find the service ids by running

```
$ docker stack ps elastic-stack
```

Check logs by running
```
docker service ps "elastic-stack_elasticsearch"
docker service logs SERVICE_ID
```
