# Global Operations with Docker Enterprise, DockerCon2017

**Docker Swarm Networking Tool** is [here](https://github.com/alexmavr/swarm-nbt)

**Demo 1: Automating Secure Image Caching** 

will open-source soon!

**Demo 2: Geo-Aware Application Deployment**

topology aware scheduling docs are [here](https://github.com/docker/docker/blob/master/docs/reference/commandline/service_create.md#specify-service-placement-preferences---placement-pref).

Geo-DNS: I used Route53 geo-dns features to resolve US users DNS requests to the US cluster and EU users DNS requests to the EU cluster. 

sample deployment command:
```
 docker service create \
  --name pets \
  --replicas 5 \
  --mount type=bind,source=/etc/hostname,destination=/tmp/worker/hostname \
  --publish mode=host,target=5000,published=32000,protocol=tcp \
  --constraint 'node.role==worker' \
  --placement-pref 'spread=node.labels.region' \
  --placement-pref 'spread=node.labels.zone' \
  dtr.us-west.dcus17.dckr.org/dockercon/pets:v2
```





