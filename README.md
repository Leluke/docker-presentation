# docker-presentation
Prerequisites

Make sure your local system has VirtualBoxand docker-machine installed.

$ docker-machine ls

$ docker-machine create -d virtualbox local

$ eval "$(docker-machine env local)"

$ docker run swarm create

This command returned a token like this f03e229c51d22c966b5523f53b58e3ad. Save it.

A single system in your network is known as your Docker Swarm manager. 
The swarm manager orchestrates and schedules containers on the entire cluster.

$ docker-machine create \
        -d virtualbox \
        --swarm \
        --swarm-master \
        --swarm-discovery token://<TOKEN-FROM-ABOVE> \
        swarm-master

$ docker-machine create \
    -d virtualbox \
    --swarm \
    --swarm-discovery token://<TOKEN-FROM-ABOVE> \
    swarm-agent-00


$ docker-machine create \
    -d virtualbox \
    --swarm \
    --swarm-discovery token://<TOKEN-FROM-ABOVE> \
    swarm-agent-01

Direct the Swarm

$ eval $(docker-machine env --swarm swarm-master)



