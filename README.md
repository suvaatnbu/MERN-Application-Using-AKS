# MERN Application on AKS

## 📌 Project Overview

This project is a **MERN (MongoDB, Express, React, Node.js)** stack application deployed on **Azure Kubernetes Service (AKS)**.
It demonstrates:

* Containerization with **Docker**
* Orchestration with **Kubernetes**
* Deployment on **Azure Kubernetes Service (AKS)**
* CI/CD ready structure for automation

---

## 🛠 Tech Stack

* **Frontend**: React + Nginx
* **Backend**: Node.js + Express
* **Database**: MongoDB (managed on Azure CosmosDB or external)
* **Containerization**: Docker
* **Orchestration**: Kubernetes
* **Cloud**: Azure Kubernetes Service (AKS)

---

## 📂 Project Structure

```
MERN-Application-Using-AKS/
│── frontend/         # React app
│   ├── app/
│   ├── Dockerfile
│── backend/          # Node.js + Express app
│   ├── src/
│   ├── server.js
│   ├── Dockerfile
│── k8s/              # Kubernetes manifests
│── helm/             # Helm chart (if applicable)
│── Dockerfile        # Root Dockerfile (if any)
│── package.json
│── README.md         # Documentation
```

---

## 🚀 Local Development

### 1. Clone Repository

```bash
git clone https://github.com/suvaatnbu/MERN-Application-Using-AKS.git
cd MERN-Application-Using-AKS
```

### 2. Run Backend Locally

```bash
cd backend
npm install
node server.js
```

### 3. Run Frontend Locally

```bash
cd frontend/app
npm install
npm start
```

---

## 🐳 Docker Setup

### Build and Run Backend

```bash
docker build -t suvaatnbu/mern-backend:latest ./backend
docker run -p 5000:5000 suvaatnbu/mern-backend:latest
```

### Build and Run Frontend

```bash
docker build -t suvaatnbu/mern-frontend:latest ./frontend
docker run -p 3000:80 suvaatnbu/mern-frontend:latest
```

---

## ☸️ Kubernetes Deployment

### 1. Apply Manifests

```bash
kubectl apply -f k8s/ -n mern-app
```

### 2. Check Resources

```bash
kubectl get pods -n mern-app
kubectl get svc -n mern-app
```

### 3. Access Frontend

Get **EXTERNAL-IP** of the `frontend-service`:

```bash
kubectl get svc frontend-service -n mern-app
```

Then open it in browser.

---

## 📦 Push to Docker Hub

```bash
docker push suvaatnbu/mern-backend:latest
docker push suvaatnbu/mern-frontend:latest
```

---

## 🌐 Deployment on AKS

1. Create AKS Cluster
2. Connect via `az aks get-credentials`
3. Deploy manifests with `kubectl`
4. Access application via LoadBalancer external IP

---

## 📝 Author

👤 **Suvabrata Guharay**
📌 Repository: [MERN-Application-Using-AKS](https://github.com/suvaatnbu/MERN-Application-Using-AKS)

---

Would you like me to make this documentation **lightweight (only setup instructions)** or **detailed (with diagrams + screenshots placeholders + step-by-step Azure setup)**?
