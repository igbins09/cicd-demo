# DevOps Portfolio Project
A simple end-to-end DevOps pipeline showcasing CI/CD, containerization, Kubernetes deployment, and monitoring.

## Tools Used
- Git & GitHub
- GitHub Actions (CI/CD)
- Docker
- Kubernetes (Minikube)
- Prometheus & Grafana

## Setup Instructions
1. Clone the repo: `git clone <repo-url>`
2. Run locally: `npm install && node index.js`
3. Build Docker image: `docker build -t myapp .`
4. Update `deployment.yaml` with your Docker Hub username: `sed -i 's/DOCKER_USERNAME/<your-username>/g' deployment.yaml`
5. Deploy to Kubernetes: `kubectl apply -f deployment.yaml`

## Skills Demonstrated
- CI/CD automation
- Containerization
- Kubernetes orchestration
- Monitoring setup
