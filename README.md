# DevOps Pipeline Series

A hands-on series where I build a complete, production-grade DevOps pipeline from scratch — step by step, part by part.

Each part of this series builds directly on the previous one. By the end, the pipeline covers local infrastructure, automated deployments, security scanning, monitoring, and real-time alerting.

---

## Series Progress

| Part | Topic | Status | Article |
|------|-------|--------|---------|
| 1 | Local Deployment with Vagrant, Docker & Nginx | ✅ Complete | [Read on Dev.to](https://dev.to/desmondgoldsmith) |
| 2 | CI/CD Pipeline with GitHub Actions | 🔄 In Progress | Coming soon |
| 3 | Security Scanning with Trivy | 🔜 Planned | Coming soon |
| 4 | Monitoring and Logging | 🔜 Planned | Coming soon |
| 5 | Slack Alerting for Failed Builds & Deployments | 🔜 Planned | Coming soon |

---

## Architecture (Part 1)

```
Your Browser
     |
  localhost:8080
     |
  Vagrant VM (Ubuntu 22.04)
     |
  Port 80
     |
  Nginx (Reverse Proxy)
     |
  ┌──────────────────────┐
  │                      │
React Frontend     Express Backend
(port 3000)          (port 5000)
                         |
                    MySQL Database
                      (port 3306)
```

---

## Repository Structure

```
devops-pipeline-series/
├── part-1-vagrant-docker-nginx/
│   ├── Vagrantfile          ← VM blueprint
│   ├── compose.yaml         ← Docker Compose config
│   ├── nginx/
│   │   └── nginx.conf       ← Reverse proxy config
│   └── README.md
├── part-2-github-actions/   ← coming soon
├── part-3-trivy-security/   ← coming soon
├── part-4-monitoring/       ← coming soon
├── part-5-slack-alerting/   ← coming soon
└── README.md
```

---

## Tech Stack

| Tool | Purpose |
|------|---------|
| Vagrant | Local VM provisioning |
| VirtualBox | VM engine |
| Ubuntu 22.04 | Server OS (mirrors AWS EC2) |
| Docker & Docker Compose | Container orchestration |
| Nginx | Reverse proxy |
| React | Frontend |
| Node.js / Express | Backend API |
| MySQL / MariaDB | Database |
| GitHub Actions | CI/CD (Part 2) |
| Trivy | Security scanning (Part 3) |
| Slack | Alerting (Part 5) |

---

## Getting Started (Part 1)

### Prerequisites
- [Vagrant](https://www.vagrantup.com/downloads)
- [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
- [Git](https://git-scm.com/)

### Run Locally

```bash
# Clone this repo
git clone https://github.com/Desmondgoldsmith/devops-pipeline-series.git
cd devops-pipeline-series/part-1-vagrant-docker-nginx

# Clone the app code
git clone https://github.com/docker/awesome-compose.git
cd awesome-compose/react-express-mysql

# Follow the procedures as outlined in part 1 of the blog series 
# Then start the stack
docker compose up --build -d
```

Visit `http://localhost:8080` in your browser.

### Useful Commands

```bash
vagrant up           # Start the VM
vagrant ssh          # Connect to the VM
vagrant halt         # Stop the VM
vagrant destroy      # Delete the VM

docker compose up --build -d    # Start all containers
docker compose down             # Stop all containers
docker compose ps               # Check container status
docker compose logs -f nginx    # Stream Nginx logs
docker stats                    # Monitor resource usage
```

---

## Blog Series

All articles are published on Dev.to and cross-posted to LinkedIn.

- **Part 1** — [Building a DevOps Pipeline from Scratch: Local Deployment with Vagrant, Docker & Nginx](https://dev.to/desmond_goldsmith/building-a-devops-pipeline-from-scratch-local-deployment-with-vagrant-docker-nginx-part-1-11ae)

---

## Connect

If you find this series useful, feel free to connect:

- Dev.to: [dev.to/desmond_goldsmith](https://dev.to/desmond_goldsmith)
- LinkedIn: [linkedin.com/in/desmondgoldsmith](https://linkedin.com/in/desmondgoldsmith)
- GitHub: [github.com/Desmondgoldsmith](https://github.com/Desmondgoldsmith)

---

*This series is actively being built. Follow along and drop questions in the issues tab.*
