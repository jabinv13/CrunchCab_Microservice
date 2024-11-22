# 🚀 Modern Microservices Architecture

![CSS3](https://img.shields.io/badge/css3-%231572B6.svg?style=flat&logo=css3&logoColor=white) ![JavaScript](https://img.shields.io/badge/javascript-%23323330.svg?style=flat&logo=javascript&logoColor=%23F7DF1E) ![HTML5](https://img.shields.io/badge/html5-%23E34F26.svg?style=flat&logo=html5&logoColor=white) ![AWS](https://img.shields.io/badge/AWS-%23FF9900.svg?style=flat&logo=amazon-aws&logoColor=white) ![Vercel](https://img.shields.io/badge/vercel-%23000000.svg?style=flat&logo=vercel&logoColor=white) ![Context-API](https://img.shields.io/badge/Context--Api-000000?style=flat&logo=react) ![NodeJS](https://img.shields.io/badge/node.js-6DA55F?style=flat&logo=node.js&logoColor=white) ![Express.js](https://img.shields.io/badge/express.js-%23404d59.svg?style=flat&logo=express&logoColor=%2361DAFB) ![NPM](https://img.shields.io/badge/NPM-%23CB3837.svg?style=flat&logo=npm&logoColor=white) ![Next JS](https://img.shields.io/badge/Next-black?style=flat&logo=next.js&logoColor=white) ![Nodemon](https://img.shields.io/badge/NODEMON-%23323330.svg?style=flat&logo=nodemon&logoColor=%BBDEAD) ![React](https://img.shields.io/badge/react-%2320232a.svg?style=flat&logo=react&logoColor=%2361DAFB) ![SASS](https://img.shields.io/badge/SASS-hotpink.svg?style=flat&logo=SASS&logoColor=white) ![JWT](https://img.shields.io/badge/JWT-black?style=flat&logo=JSON%20web%20tokens) ![Socket.io](https://img.shields.io/badge/Socket.io-black?style=flat&logo=socket.io&badgeColor=010101) ![Vite](https://img.shields.io/badge/vite-%23646CFF.svg?style=flat&logo=vite&logoColor=white) ![React Query](https://img.shields.io/badge/-React%20Query-FF4154?style=flat&logo=react%20query&logoColor=white) ![React Router](https://img.shields.io/badge/React_Router-CA4245?style=flat&logo=react-router&logoColor=white) ![React Hook Form](https://img.shields.io/badge/React%20Hook%20Form-%23EC5990.svg?style=flat&logo=reacthookform&logoColor=white) ![Redux](https://img.shields.io/badge/redux-%23593d88.svg?style=flat&logo=redux&logoColor=white) ![Nginx](https://img.shields.io/badge/nginx-%23009639.svg?style=flat&logo=nginx&logoColor=white) ![Jenkins](https://img.shields.io/badge/jenkins-%232C5263.svg?style=flat&logo=jenkins&logoColor=white) ![MongoDB](https://img.shields.io/badge/MongoDB-%234ea94b.svg?style=flat&logo=mongodb&logoColor=white) ![MySQL](https://img.shields.io/badge/mysql-4479A1.svg?style=flat&logo=mysql&logoColor=white) ![GitLab](https://img.shields.io/badge/gitlab-%23181717.svg?style=flat&logo=gitlab&logoColor=white) ![GitHub](https://img.shields.io/badge/github-%23121011.svg?style=flat&logo=github&logoColor=white) ![Git](https://img.shields.io/badge/git-%23F05033.svg?style=flat&logo=git&logoColor=white) ![GitHub Actions](https://img.shields.io/badge/github%20actions-%232671E5.svg?style=flat&logo=githubactions&logoColor=white) ![Kubernetes](https://img.shields.io/badge/kubernetes-%23326ce5.svg?style=flat&logo=kubernetes&logoColor=white) ![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=flat&logo=docker&logoColor=white)

## 📋 Overview
A modern, scalable microservices architecture with independent databases for each service, ensuring complete data isolation and service autonomy.

## Service Repositories

* **Frontend Admin:** [https://github.com/jabinv13/mernstack-c-admin-ui]
* **Frontend Client:** [https://github.com/jabinv13/mernstack-c-client-ui]
* **Backend Catalog:** [https://github.com/jabinv13/mernstack-c-catalog-service]
* **Backend Auth:** [https://github.com/jabinv13/mernstack-c-auth-service]
* **Backend Order:** [https://github.com/jabinv13/mernstack-c-order-service]
* **Backend Notification:** [https://github.com/jabinv13/mernstack-c-notificationservice]
* **Backend Websocket:** [https://github.com/jabinv13/mernstack-c-websocketservice]


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
  - MongoDB (catalog & Orders)
  - PostgreSQL (Auth service)
- **DevOps:** Docker, Kubernetes,Aws
- **Message Broker:** Kafka
- **Gateway:** Nginx
- **CI/CD:** Gitops,Argocd

## 🚀 Screenshots 

<p align="center">
  
  <img src="https://i.postimg.cc/NFRrZr8q/Screenshot-2024-11-21-201716.jpg" title="hover text">
  <img src="https://i.postimg.cc/fRCYwXGM/Screenshot-2024-11-21-172149.jpg" title="hover text">
  <img src="https://i.postimg.cc/wBbJNzxP/Screenshot-2024-11-21-173436.jpg" title="hover text">
  <img src="https://i.postimg.cc/zBbhSQVf/Screenshot-2024-11-21-173527.jpg">
  <img src="https://i.postimg.cc/4dD9819Q/Screenshot-2024-11-21-173616.jpg" title="hover text">
  <img src="https://i.postimg.cc/VLjjV24r/Screenshot-2024-11-21-150319.jpg" title="hover text">
</p>
