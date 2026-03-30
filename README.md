# 🎨 Multi-Environment Cloud Deployment — Go Web App on GKE

![Google Cloud](https://img.shields.io/badge/Google_Cloud-4285F4?style=for-the-badge&logo=google-cloud&logoColor=white)
![Go](https://img.shields.io/badge/Go-00ADD8?style=for-the-badge&logo=go&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white)

---

## 📌 About This Project

A **Go-based web application** deployed across separate **development and production environments** on Google Kubernetes Engine (GKE) using Google Cloud Build pipelines.

This project demonstrates a real-world **multi-environment deployment strategy** — a core DevOps practice used by professional engineering teams to safely test changes before they reach production users.

Completed as part of the **Google Cloud Arcade program**.

---

## 🌐 What the App Does

The app is a lightweight HTTP server that serves dynamically generated PNG images based on the endpoint called:

| Endpoint | Response |
|---|---|
| `/blue` | Returns a 100×100 blue PNG image |
| `/red` | Returns a 100×100 red PNG image |

Simple by design — the focus of this project is the **deployment pipeline**, not the application itself.

---

## ⚙️ How the Pipeline Works

```
Code pushed to GitHub
        ↓
Cloud Build triggered automatically
        ↓
Docker image built from Go app
        ↓
Image pushed to Google Artifact Registry
        ↓
        ├── Dev pipeline  → deploys to DEV environment on GKE
        └── Prod pipeline → deploys to PROD environment on GKE
```

Two separate Cloud Build pipelines ensure that:
- **Development** changes are tested in an isolated environment first
- **Production** only receives stable, verified builds
- Each environment has its own Kubernetes configuration

---

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| **Go (Golang)** | Web server & image generation |
| **Docker** | Containerisation |
| **Google Cloud Build** | Automated CI/CD pipelines |
| **Google Artifact Registry** | Docker image storage |
| **Google Kubernetes Engine** | Container deployment & orchestration |
| **Kubernetes Manifests** | Environment configuration (dev/prod) |

---

## 📁 Repository Structure

```
sample-app/
├── main.go                # Go web server — /blue and /red endpoints
├── Dockerfile             # Container image definition
├── cloudbuild.yaml        # Production Cloud Build pipeline
├── cloudbuild-dev.yaml    # Development Cloud Build pipeline
├── dev/                   # Kubernetes manifests for dev environment
└── prod/                  # Kubernetes manifests for prod environment
```

---

## 💡 What I Learned

- How to write and deploy a **Go web application** in a containerised environment
- How to set up **separate dev and prod pipelines** using Cloud Build YAML configs
- The importance of **environment isolation** in professional software delivery
- How **Kubernetes manifests** differ between environments
- How **Artifact Registry** stores and versions container images across deployments

---

## 🔗 Related

- 👩‍💻 [My GitHub Profile](https://github.com/Proyanshi)
- 🏅 [My Google Cloud Skills Profile](https://www.skills.google/public_profiles/cc359b71-f029-470d-9680-3b25471ce990)
- 🚀 [CI/CD Pipeline Repo](https://github.com/Proyanshi/hello-cloudbuild-app)
- 💼 [LinkedIn](https://www.linkedin.com/in/priyanshi-chaudhary-466508328)

---

<p align="center"><em>Built with ☁️ on Google Cloud | Part of Google Cloud Arcade — Diamond League</em></p>
