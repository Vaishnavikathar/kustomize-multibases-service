# Kustomize Multi-Environment Deployment

This repository demonstrates a **multi-base Kustomize** setup for Kubernetes deployments across different environments — **dev**, **staging**, and **production**.

---

## 📁 Project Structure

```
kustomize-multibases-service/
├── base/
│   ├── deployment.yaml
│   ├── service.yaml
│   └── kustomization.yaml
├── dev/
│   └── kustomization.yaml
├── staging/
│   └── kustomization.yaml
├── production/
│   └── kustomization.yaml
```

---

## ⚙️ How to Use

### 1. Build Environment Manifests

```bash
kustomize build dev/
kustomize build staging/
kustomize build production/
```

### 2. Apply to Kubernetes

```bash
kubectl apply -k dev/
# or
kubectl apply -k staging/
kubectl apply -k production/
```

Each overlay customizes:
- `namePrefix` per environment
- Replica count (`2`, `1`, `3`)
- NodePort (`32000`, `31000`, `31005`)

---

## 🧠 Author

Created by [Vaishnavi Kathar](https://github.com/Vaishnavikathar)

---

## 🧰 Git Setup

To push this to your GitHub:

```bash
git init
git add .
git commit -m "Initial Kustomize multi-env setup"
git branch -M main
git remote add origin https://github.com/Vaishnavikathar/kustomize-multibases-service.git
git push -u origin main
```
