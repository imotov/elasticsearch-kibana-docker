# Docker files for starting Elasticsearch and Kibana

## Introduction

This docked compose setup can be used to quickly bring up Elasticsearch and Kibana for local testing.

## Usage

Specify Elasticsearch setup password in `.env` file:

```
# For elasticsearch
ELASTIC_PASSWORD=changeme
# For kibana
ELASTICSEARCH_PASSWORD=changeme
```

Start Elasticsearch and Kibana by running:

```
$ docker-compose up -d
```

After startup you can connect to Elasticsearch at http://localhost:9200/ and Kibana at http://localhost:5601/

When done, stop Elasticsearch and Kibana by running:

```
$ docker-compose down
```
