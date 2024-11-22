# 🚀 Modern Microservices Architecture

[![Node.js](https://img.shields.io/badge/Node.js-18.x-green.svg)](https://nodejs.org/)
[![React](https://img.shields.io/badge/React-18.x-blue.svg)](https://reactjs.org/)
[![Docker](https://img.shields.io/badge/Docker-Latest-blue.svg)](https://www.docker.com/)

## 📋 Overview
A modern, scalable microservices architecture with independent databases for each service, ensuring complete data isolation and service autonomy.

## 🎥 Service Demonstrations
### Example of a service and how scaling works in k8s
<p align="center">
  <img src="https://i.postimg.cc/4yyzM3LX/argo.jpg" title="hover text">
</p>

## 🏗️ Architecture
```mermaid
graph TD
    Client[Client Application] --> Gateway[API Gateway]
    AdminUI[Admin Application] --> Gateway[API Gateway]
    Gateway --> Auth[Auth Service]
    Gateway --> Products[Catalog-Service]
    Gateway --> Orders[Order-Service]
    Gateway --> Payments[Payment Service]
    Gateway --> Notification[Notification-service]
    WenSocket[Web socket] --> Client[Client Application]
    WenSocket[Web socket] --> AdminUI[Admin Application]
    WenSocket[Web socket] --> Products[Catalog-Service]
    Products[Catalog-Service] --> WenSocket[Web socket]
    WenSocket[Web socket] -->  Orders[Order-Service]
     Orders[Order-Service] --> WenSocket[Web socket] 
    Auth --> AuthDB[(Auth DB - PostgreSQL)]
    Products --> ProductDB[(Product DB - MongoDB)]
    Orders --> OrderDB[(Order DB - MongoDB)]
    Payments --> PaymentDB[(Payment DB - MongoDB)]
    
    subgraph Message Queue
        Kafka
    end
    
    
    Products -.-> Kafka
    Orders -.-> Kafka
    Payments -.-> Kafka
    Notification -.-> Kafka
```

## 💾 Database Architecture

| Service | Database Type | Purpose | Scaling Strategy |
|---------|--------------|---------|------------------|
| Auth | PostgreSQL | User profiles, credentials | Sharding |
| Products | MongoDB | Product catalog, inventory | Read replicas |
| Orders | MongoDB | Order processing, history | Sharding |
| Payments | MongoDB | Transaction records | Read replicas |

## ⚡ Key Features
- 🔐 Secure Authentication & Authorization
- 📦 Product Catalog Management
- 🛒 Order Processing
- 💳 Payment Integration
- 📡 Real-time Updates
- 🔄 Service Orchestration
- 🗄️ Independent Databases

## 🛠️ Tech Stack
- **Frontend:** React.js, Redux, Axios
- **Backend:** Node.js, Express.js
- **Databases:** 
  - MongoDB (Auth & Orders)
  - PostgreSQL (Products & Payments)
- **DevOps:** Docker, Kubernetes
- **Message Broker:** Kafka
- **Gateway:** Nginx

## 🚀 Screenshots 

<p align="center">
  
  <img src="https://i.postimg.cc/NFRrZr8q/Screenshot-2024-11-21-201716.jpg" title="hover text">
  <img src="https://i.postimg.cc/fRCYwXGM/Screenshot-2024-11-21-172149.jpg" title="hover text">
  <img src="https://i.postimg.cc/wBbJNzxP/Screenshot-2024-11-21-173436.jpg" title="hover text">
  <img src="https://i.postimg.cc/fRCYwXGM/Screenshot-2024-11-21-172149.jpg" title="hover text">
  <img src="https://i.postimg.cc/zBbhSQVf/Screenshot-2024-11-21-173527.jpg">
  <img src="https://i.postimg.cc/4dD9819Q/Screenshot-2024-11-21-173616.jpg" title="hover text">
  <img src="https://i.postimg.cc/VLjjV24r/Screenshot-2024-11-21-150319.jpg" title="hover text">
</p>
