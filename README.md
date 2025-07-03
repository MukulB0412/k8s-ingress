# 🍕🍰 Pizza-Cake App on Kubernetes with Ingress

This project demonstrates how to deploy two simple Python Flask apps — `pizza-app` and `cake-app` — on **Kubernetes (Minikube)** using:
- Docker
- Deployments & Services
- Ingress Controller (NGINX)
- Custom domain using `/etc/hosts`

---

## 📁 Project Structure

```
pizza-cake/
│
├── pizza-app/
│   ├── app.py
│   ├── Dockerfile
│   └── requirements.txt
│
├── cake-app/
│   ├── app.py
│   ├── Dockerfile
│   └── requirements.txt
│
├── k8s/
│   ├── pizza-deployment.yml
│   ├── pizza-service.yml
│   ├── cake-deployment.yml
│   ├── cake-service.yml
│   └── ingress.yml
```

---

## 🚀 Tech Stack

- [x] Python Flask (for both apps)
- [x] Docker (image creation)
- [x] Kubernetes (Minikube setup)
- [x] Ingress Controller (NGINX)
- [x] Domain routing via `/etc/hosts`

---

## 🧑‍🍳 App Details

| App Name   | URL Path        | Message Output            |
|------------|------------------|----------------------------|
| pizza-app  | `/pizza`         | `Hello from Pizza App!`    |
| cake-app   | `/cake`          | `Hello from Cake App!`     |

---

## 🛠️ Setup Instructions

### 1. Start Minikube
```bash
minikube start
```

---

### 2. Enable Ingress Controller
```bash
minikube addons enable ingress
```

---

### 3. Build Docker Images
```bash
docker build -t pizza-app:latest ./pizza-app
docker build -t cake-app:latest ./cake-app
```

---

### 4. Load Images into Minikube
```bash
minikube image load pizza-app:latest
minikube image load cake-app:latest
```

---

### 5. Apply Kubernetes Configs
```bash
kubectl apply -f k8s/
```

---

### 6. Add `mukul.com` to `/etc/hosts`
```bash
sudo nano /etc/hosts
# Add this line (use the IP from minikube ip):
192.168.49.2 mukul.com
```

---

### 7. Access the App

- 🍕 Pizza: [http://mukul.com/pizza](http://mukul.com/pizza)  
- 🍰 Cake: [http://mukul.com/cake](http://mukul.com/cake)

---

## 📸 Screenshots

### ✅ Final Output - Pizza:
![Pizza App](./screenshots/pizza.png)

### ✅ Final Output - Cake:
![Cake App](./screenshots/cake.png)

---

## 🧠 Concepts Covered

- Creating and using custom Docker images in Minikube
- Kubernetes Deployments and Services
- Ingress resource with custom routing
- Domain mapping using `/etc/hosts`

---
