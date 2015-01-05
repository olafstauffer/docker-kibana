# docker-kibana

Build a docker image with a kibana (v4) dashboard.

This Dockerfile builds a image based on Kibana4 (beta).

It uses [docker-starter](https://github.com/olafstauffer/docker-starter) to resolve the connection to a elasticsearch node at runtime.

### Examples

#### Connect to a running elasticsearch container (that exports port 9200)

    docker run -d -P --link CONTAINER:elasticsearch ollo/kibana


#### Setup Elasticsearch and Kibana using fig:

fig.yml

    kibana:
        image: ollo/kibana
        ports:
        - "5601:5601"
        links:
        - elasticsearch
    elasticsearch:
        image: dockerfile/elasticsearch
        ports:
        - 9200
        - 9300

