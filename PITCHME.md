### Kubernetes @ DMSC


Gareth Murphy

ESS DMSC

2018-02-05

---

### What is Kubernetes

- Kubernetes is an open-source system for automating deployment, scaling, and management of containerized applications.
- https://kubernetes.io/
- KubeCon in Cph https://events.linuxfoundation.org/events/kubecon-cloudnativecon-europe-2018/

---

### What do we want to deploy?


- SciCat Data Catalogue
- Make ESS metadata available to users
- Easily findable, accessible
- Open source - https://github.com/ScicatProject

---
### SciCat is not a single app

- Database (MongoDB)
- Web frontend (catanie - Angular based)
- Data catalogue backend (catamel- Automatically generated using loopback)
- Message/job queuing system (currently RabbitMQ -> migrating to Kafka)
- Dataflow interface (Node-Red)


---

### Kubernetes Deployment



- Minikube
- For local testing only
- Working minikube config at github.com/ScicatProject/localdeploy
- RBAC disabled by default - can renable


---

## Helm

- Package manager for Kubernetes
- Equivalent of apt or yum
- Prepackaged k8s deployments available
- https://github.com/kubernetes/charts
- helm install stable/mongodb
- helm install dacat-api-server --name catamel  --set image.tag=$CATAMEL_IMAGE_VERSION --set image.repository=dacat/catamel





---

### MongoDB

- Database requires persistent storage
- Currently we store on k8s nodes, not a longterm solution






---

### Catanie

![nodered](assets/catanie.png)


---

### Node-RED

![nodered](assets/nodered.png)

### Catamel

![catamel](assets/catamel.png)

---

## MongoDB


