# Lab 6 – Deploying Algonquin Pet Store to Azure Kubernetes Service (AKS)

This repository contains my work for **Lab 6** of CST8915 – Full‑stack Cloud‑native Development.  
The goal of this lab is to deploy the Algonquin Pet Store application to **Azure Kubernetes Service (AKS)** and expose the microservices through a single LoadBalancer IP.

---

## 🚀 What This Lab Covers

- Creating an AKS cluster  
- Connecting to the cluster using Azure CLI + kubectl  
- Deploying the Algonquin Pet Store using the provided YAML file  
- Accessing the store-front, product-service, order-service, and RabbitMQ  
- Understanding how NGINX routes multiple services through one IP  
- Cleaning up Azure resources  

---

## 📦 Files Included

- **algonquin-pet-store-all-in-one.yaml**  
  Deployment file used to deploy all microservices to AKS.

- **video/**  
  Folder containing the demo video (placeholder added — video will be uploaded later).

---

##  Demo Video

The demo video for this lab will be added here:

 `video/lab6-demo.mp4` *(coming soon)*

---

##  How All Services Share One IP

The store-front container includes an **NGINX reverse proxy**.  
NGINX looks at the URL path and forwards the request to the correct backend service:

- `/products` → product-service  
- `/orders` → order-service  
- `/rabbitmq` → RabbitMQ console  
- `/` → Vue.js frontend  

This allows all services to be accessed through **one LoadBalancer IP**.

---

