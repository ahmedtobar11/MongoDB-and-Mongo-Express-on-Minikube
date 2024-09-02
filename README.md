# MongoDB and Mongo Express on Minikube 🚀

## Overview

This project provides a detailed guide for deploying MongoDB and Mongo Express within a Minikube Kubernetes environment. The setup leverages Kubernetes features such as Secrets , ConfigMaps , Persistent Volumes , and Ingress to manage and expose MongoDB and Mongo Express efficiently.

By following this guide, you'll set up:
- **MongoDB**: A scalable, document-oriented database. 🗄️
- **Mongo Express**: A web-based UI for managing MongoDB. 🖥️
- **Secrets**: For securely managing database credentials. 🔐
- **ConfigMaps**: For configuring application settings. ⚙️
- **Persistent Volumes**: For data persistence using Minikube’s `hostPath`. 💾
- **Ingress**: For accessing Mongo Express via a custom domain. 🌐

## 🛠️Features

- **Secure Credentials Management**: Store MongoDB credentials securely using Kubernetes Secrets. 
- **Configuration Management**: Define and manage MongoDB connection settings with Kubernetes ConfigMaps.
- **Persistent Storage**: Ensure data persistence with Persistent Volumes in Minikube.
- **Custom Domain Access**: Access Mongo Express through a user-friendly domain name via Ingress. 
- **Local Development**: Fully functional setup for development and testing on Minikube. 

## Prerequisites

**Ensure you have the following tools installed:**

1. **Minikube**: For creating and managing a local Kubernetes cluster.
   ```bash
   minikube start
2. **Kubectl**: The command-line tool for interacting with Kubernetes clusters. 🖥️
   ```bash
   kubectl version
3. **Docker**: Required for pulling container images. 🐳
   ```bash
   docker --version
4. **Base64** Encoding Tool: For encoding sensitive data. 🔢
   ```bash
   base64 --version
5. **Ingress Controller:** Enable Ingress in Minikube. 🚪
   ```bash
   minikube addons enable ingress

## Setup Instructions

Clone the Repository 💻
  ```bash
  git clone https://github.com/ahmedtobar11/MongoDB-and-Mongo-Express-on-Minikube.git
  cd <repository-directory>
```

## Configure Kubernetes Resources
**Apply the following Kubernetes configurations:**

  ```bash
kubectl apply -f mongodb-pv.yaml
kubectl apply -f mongodb-pvc.yaml
kubectl apply -f mongo-secrets.yaml
kubectl apply -f mongo-config.yaml
kubectl apply -f mongodb.yaml
kubectl apply -f mongo-express.yaml
kubectl apply -f mongo-express-ingress.yaml
```
**Update /etc/hosts 📝**
Add an entry to map your custom domain to Minikube’s IP address:
  ```bash
  <minikube-ip> mongo-express.local
  ```

**Accessing Mongo Express** 🌐
After deploying the resources and updating your /etc/hosts file, access Mongo Express in your browser at:
  ```bash
http://mongo-express.local
  ```
## Project Structure

- **mongodb-pv.yaml:** Defines the Persistent Volume for MongoDB data. 📁
- **mongodb-pvc.yaml:** Defines the Persistent Volume Claim. 📦
- **mongo-secrets.yaml:** Stores MongoDB credentials securely. 🔐
- **mongo-config.yaml:** Configures MongoDB connection settings. ⚙️
- **mongodb.yaml:** Deploys MongoDB in Kubernetes and Exposes MongoDB internally within the cluster . 🛠️
- **mongo-express.yaml:** Deploys Mongo Express in Kubernetes and Exposes Mongo Express externally. 🌐
- **mongo-express-ingress.yaml:** Configures Ingress for domain access. 🚪

![Architecture](https://github.com/user-attachments/assets/3a2b133b-8e0d-4974-a206-06efbcdfd931)
