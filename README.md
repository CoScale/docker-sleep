# Docker sleep

This image is used in environments run by CoScale to connect to external services. 

## Deployment

### Docker

`docker run -d coscale/docker-sleep`

### Docker Swarm

`docker service create --name coscale-external coscale/docker-sleep`

### Kubernetes

```
apiVersion: v1
kind: ReplicationController
metadata:
  name: coscale-external
spec:
  replicas: 1
  selector:
    app: coscale-external
  template:
    metadata:
      name: coscale-external
      labels:
        app: coscale-external
    spec:
      containers:
      - name: coscale-external
        image: coscale/docker-sleep
```
