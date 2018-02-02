### Kubernetes @ DMSC


Gareth Murphy

ESS DMSC

2018-02-05

---

### What is Kubernetes

Kubernetes is an open-source system for automating deployment, scaling, and management of containerized applications.


---

### What do we want to deploy?


- SciCat Data Catalogue
- Make ESS metadata available to users
- Easily findable, accessible


---
### SciCat

- Database (MongoDB)
- Web frontend (Angular based)
- Data catalogue backend (Automatically generated using loopback)
- Message/job queuing system (RabbitMQ -> Kafka)

---

### Kubernetes Deployment

- Minikube
- For local testing only
- Working minikube config at github.com/ScicatProject/localdeploy
- RBAC disabled by default - can renable



---

### MongoDB

- Database requires persistent storage
- Currently we store on k8s nodes, not a longterm solution






---?image=assets/catanie.png&size=auto 90%


---

### Node-RED

---

## MongoDB

---

## Helm

- Package manager for Kubernetes
- Equivalent of apt or yum
- Prepackaged k8s deployments available


