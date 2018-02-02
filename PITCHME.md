### Kubernetes @ DMSC


Gareth Murphy

ESS DMSC

2018-02-05

---

### What is Kubernetes

> Kubernetes is an open-source system for automating
> deployment, scaling, and management of containerized
> applications.

- https://kubernetes.io/
- [KubeCon in Cph 2018](https://events.linuxfoundation.org/events/kubecon-cloudnativecon-europe-2018/)


---

### Kubernetes/K8s

- from greek word for helmsman/rorsman/timonier/steuermann/κυβερνήτης
- also root of cybernetics, governor



---

### What do we want to deploy?


- SciCat Data Catalogue
- Make ESS metadata available to users
- Easily findable, accessible, interoperable, reusable (FAIR)
- Open source - https://github.com/ScicatProject

---
### SciCat is not a single app

- Database [MongoDB](https://www.mongodb.com/)
- Web frontend (catanie - [angular](http://angular.io) based)
- Data catalogue backend (catamel- Automatically generated using IBM's [loopback.io](http://loopback.io)
- Message/job queuing system (currently RabbitMQ -> migrating to [Kafka](http://kafka.apache.org))
- Dataflow interface [Node-Red](https://nodered.org/)


---

### Kubernetes Deployment

- Can do test deployment on minikube
- For local testing only
- Working minikube config at http://www.github.com/ScicatProject/localdeploy
- RBAC disabled by default - can renable

---

### Deployment on scicat0x.esss.lu.se

- still outstanding:
- Ingress
- persistent storage
- Active directory





---

## Kubernetes

- Applications are deployed to "pod"s, which are made available using services, which are accessed using ingress
- We need to separately
- Deployments
- Services
- Pods (can be groups of containers, we typically use single containers)
- Ingress


---

## Install packages via Helm

- Package manager for Kubernetes
- Equivalent of apt or yum
- Prepackaged k8s deployments available
- https://github.com/kubernetes/charts
- A chart includes template .yaml files for deployment, service etc.
- helm install stable/mongodb
- helm install dacat-api-server --name catamel  --set image.tag=$CATAMEL_IMAGE_VERSION --set image.repository=dacat/catamel
---

### MongoDB

- NoSQL storage of metadata, login, jobs
- Database requires persistent storage
- Currently we store on k8s nodes, not a longterm solution






---

### Catanie

- Angular website
- Javascript generated static html
- Data served by catamel
- Viewable on PC, phone etc

---

### Catanie
![catanie](assets/catanie2.png)


---

### Node-RED

- Translate metadata from Kafka stream XML to catamel format (JSON)
- can be used to add in extra data cleaning  or processing


---

### Node-RED

![nodered](assets/nodered.png)

---

### Catamel

- Loopback generated API
- Models defined in JSON
- connectivity to authentication server


---

### Catamel

![catamel](assets/catamel.png)

---

### Dashboard Overview

![kube1](assets/overview.png)
---

### Pods Overview

![kube2](assets/pods.png)
---

###  Pod CPU & Memory

![kube3](assets/kuberabbit.png)


---

## DEMO

---

> The future offers very little hope for those who
> expect that our new mechanical slaves will offer
> us a world in which we may rest from thinking.

Norbert Wiener




