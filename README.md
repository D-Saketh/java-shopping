# Cloud-Native Java Shopping Microservices using Docker & Kubernetes

A cloud-native microservices project demonstrating the deployment of Java applications using **Docker**, **Kubernetes**, and **Maven**. The application is divided into multiple services and deployed locally using Kubernetes running on Docker Desktop.

## Project Overview

This project focuses on containerizing Java microservices, creating Docker images, pushing them to Docker Hub, and deploying them using Kubernetes.

The application follows a microservices architecture where each service is independently built, containerized, and deployed.

---

## Architecture

```text
                    +------------------+
                    |    Shopfront     |
                    |   Port : 8010    |
                    +---------+--------+
                              |
            ------------------------------------
            |                                  |
            v                                  v

+----------------------+        +----------------------+
| Product Catalogue    |        | Stock Manager        |
| Port : 8020          |        | Port : 8030          |
+----------------------+        +----------------------+

```

---

## Technologies Used

### Backend

- Java
- Spring Boot
- Maven

### Containerization

- Docker
- Docker Hub

### Orchestration

- Kubernetes
- Docker Desktop Kubernetes
- kubectl

### Version Control

- Git
- GitHub

---

## Project Structure

```text
java-shopping/
│
├── kubernetes/
│   ├── shopfront-service.yaml
│   ├── productcatalogue-service.yaml
│   └── stockmanager-service.yaml
│
├── shopfront/
│   ├── Dockerfile
│   ├── pom.xml
│   └── src/
│
├── productcatalogue/
│   ├── Dockerfile
│   ├── pom.xml
│   └── src/
│
├── stockmanager/
│   ├── Dockerfile
│   ├── pom.xml
│   └── src/
│
└── README.md
```

---

## Services Implemented

### 1. Shopfront Service

Handles frontend interactions and communicates with backend services.

**Docker Image**

```bash
saketh125/shopfront:latest
```

**Port**

```text
8010
```

---

### 2. Product Catalogue Service

Maintains product information and inventory details.

**Docker Image**

```bash
saketh125/productcatalogue:latest
```

**Port**

```text
8020
```

---

### 3. Stock Manager Service

Handles stock availability and updates.

**Docker Image**

```bash
saketh125/stockmanager:latest
```

**Port**

```text
8030
```

---

## Build Process

### Clone Repository

```bash
git clone https://github.com/D-Saketh/java-shopping.git
cd java-shopping
```

---

### Maven Build

Run for each microservice:

```bash
mvn clean install -DskipTests
```

---

### Build Docker Images

Shopfront:

```bash
docker build -t saketh125/shopfront:latest .
```

Product Catalogue:

```bash
docker build -t saketh125/productcatalogue:latest .
```

Stock Manager:

```bash
docker build -t saketh125/stockmanager:latest .
```

---

### Push Images to Docker Hub

```bash
docker push saketh125/shopfront:latest

docker push saketh125/productcatalogue:latest

docker push saketh125/stockmanager:latest
```

---

## Kubernetes Deployment

Move into deployment directory:

```bash
cd kubernetes
```

Deploy services:

```bash
kubectl apply -f shopfront-service.yaml

kubectl apply -f productcatalogue-service.yaml

kubectl apply -f stockmanager-service.yaml
```

---

## Verify Deployment

Check Pods:

```bash
kubectl get pods
```

Check Deployments:

```bash
kubectl get deployments
```

Check Services:

```bash
kubectl get svc
```

Check all resources:

```bash
kubectl get all
```

---

## Running Services

Use port forwarding:

### Shopfront

```bash
kubectl port-forward service/shopfront 8010:8010
```

Access:

```text
http://localhost:8010
```

### Product Catalogue

```bash
kubectl port-forward service/productcatalogue 8020:8020
```

Access:

```text
http://localhost:8020
```

### Stock Manager

```bash
kubectl port-forward service/stockmanager 8030:8030
```

Access:

```text
http://localhost:8030
```

---

## Docker Images Published

```text
saketh125/shopfront:latest

saketh125/productcatalogue:latest

saketh125/stockmanager:latest
```

---

## Features

- Microservices-based architecture
- Java application containerization
- Docker image creation and publishing
- Kubernetes deployment orchestration
- Service exposure using NodePort
- Local Kubernetes environment using Docker Desktop
- Maven build automation
- Docker Hub integration

---

## Learning Outcomes

This project demonstrates:

- Building Java microservices
- Docker image creation
- Container orchestration using Kubernetes
- Deployment configuration using YAML
- Docker Hub publishing workflow
- Managing multi-service applications

---

## Author

**Saketh**

GitHub:

https://github.com/D-Saketh

---

## Credits

Original reference project inspired from:

https://github.com/danielbryantuk/oreilly-docker-java-shopping

Modified, containerized, built, deployed, and documented for Docker and Kubernetes deployment practice.
