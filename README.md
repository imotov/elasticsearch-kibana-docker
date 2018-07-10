# Docker files for starting Elasticsearch and Kibana

## Introduction

This docked stack can be used to quickly bring up Elasticsearch and Kibana for local testing.

## Usage

Specify Elasticsearch setup password in `password.txt` file.

Deploy Elasticsearch and Kibana to currently running swarm by running:

```
$  export ELASTIC_PASSWORD=`cat password.txt`; sudo --preserve-env=ELASTIC_PASSWORD docker stack deploy -c docker-stack.yml elastic-stack
```

After startup you can connect to Elasticsearch at http://localhost:9200/ and Kibana at http://localhost:5601/

Don't forget to delete the `password.txt` file.

When done, stop Elasticsearch and Kibana by running:

```
$ sudo docker stack rm elastic-stack
```

To change redeploy, remove stack, wait for services to exit and redeploy using command above.

```
$ sudo docker stack rm elastic-stack
$ sudo docker stack ps elastic-stack
```

## Troubleshooting

Find the service ids by running

```
$ sudo docker stack ps elastic-stack
```

Check logs by running
```
sudo docker service logs SERVICE_ID
```
