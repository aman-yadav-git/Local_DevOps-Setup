# Docker + Kubernetes Local DevOps Setup

This project contains my local DevOps practice environment using Docker and Kubernetes on Fedora Linux.  
The main goal of this setup is to practice containerization, orchestration, automation, and deployment workflows locally without depending on cloud infrastructure like AWS.

---

# Why This Setup

Using cloud resources continuously can increase cost, especially during learning and testing.  
To avoid unnecessary cloud charges, this setup provides a lightweight local environment for hands-on DevOps practice.

This environment helps in learning:

- Linux administration
- Containerization
- Kubernetes orchestration
- Networking concepts
- YAML configuration
- Deployment workflows
- Troubleshooting
- Automation practices

---

# Technologies Used

- Fedora Linux
- Docker Engine
- Kubernetes
- Kind (Kubernetes IN Docker)
- kubectl
- Bash
- YAML

---



---
# Docker Setup

- Docker is used to create lightweight containers for running applications and services locally.

# Docker Installation

Installed:

docker-ce
docker-ce-cli
containerd.io
docker compose plugin

# STEP 1 — Update Fedora

sudo dnf update -y     (Updates package metadata & Fixes dependency problems later)

Remove old docker packages
sudo dnf remove docker \
                docker-client \
                docker-client-latest \
                docker-common \
                docker-latest \
                docker-latest-logrotate \
                docker-logrotate \
                docker-engine

# STEP 3 — Add Docker Repository

sudo dnf -y install dnf-plugins-core

sudo dnf config-manager addrepo --from-repofile=https://download.docker.com/linux/fedora/docker-ce.repo       (This adds official Docker packages.)

# STEP 4 — Install Docker Engine

sudo dnf install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-p# lugin -y

# STEP 5 — Start Docker

sudo systemctl enable --now docker

sudo systemctl enable --now docker (Check)

# STEP 6 — Allow Non-root Docker Usage

- Without this, every docker command needs sudo.

- Add user to docker group:-

sudo usermod -aG docker $USER

newgrp docker

# STEP 7 — Test Docker

docker run hello-world   (If successful then Docker is working )

# Docker Features Practiced
- Pulling images
- Running containers
- Building Docker images
- Docker networking
- Docker volumes
- Docker Compose
- Container troubleshooting

# Example Commands
- docker pull ubuntu
- docker run -it ubuntu bash
- docker ps
- docker images
- docker logs

