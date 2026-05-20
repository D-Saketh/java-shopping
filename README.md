# Java Shopping Microservices Deployment using Docker & Kubernetes

## Tech Stack
- Java
- Maven
- Docker
- Kubernetes
- Docker Desktop Kubernetes

## Services
- Shopfront
- Product Catalogue
- Stock Manager

## Docker Images
- saketh125/shopfront:latest
- saketh125/productcatalogue:latest
- saketh125/stockmanager:latest

## Kubernetes Deployment
kubectl apply -f shopfront-service.yaml
kubectl apply -f productcatalogue-service.yaml
kubectl apply -f stockmanager-service.yaml

## Features
- Containerized microservices deployment
- Kubernetes orchestration
- Service exposure using NodePort
