# DevOps CI/CD Project
A simple end-to-end DevOps pipeline showcasing CI/CD, containerization, Kubernetes deployment, and monitoring.

## Tools Used
- Git & GitHub
- GitHub Actions (CI/CD)
- Docker
- Kubernetes (Minikube for local deployment, Kind for GitHub Actions testing)
- Prometheus & Grafana (optional, for local monitoring)

## Setup Instructions
1. **Clone the repo**: `git clone <repo-url>`
2. **Run locally**: `npm install && node index.js`
3. **Build Docker image**: `docker build -t myapp .`
4. **Update `deployment.yaml`**: Replace the placeholder with your Docker Hub username:  
   `sed -i 's/DOCKER_USERNAME/<your-username>/g' deployment.yaml`
5. **Deploy to Kubernetes locally**: 
   - Start Minikube: `minikube start`
   - Apply deployment: `kubectl apply -f deployment.yaml`
   - Access the app: `minikube service myapp-service --url`

## CI/CD Pipeline
- **Build**: Builds and pushes the Docker image to Docker Hub.
- **Test**: Runs application tests.
- **Deploy**: Deploys the app to a temporary Kubernetes cluster using Kind in GitHub Actions for testing. For local deployment, use Minikube with `kubectl apply -f deployment.yaml`.

*The deploy job uses Kind to create a temporary Kubernetes cluster in GitHub Actions for testing the deployment. This replaces the commented-out Minikube step, which was designed for local use, ensuring the pipeline runs fully in the cloud.*

## Monitoring (Local Setup - Optional)
- Prometheus and Grafana are configured locally with Minikube for monitoring.
- Access Grafana at `http://localhost:3000` to view metrics like CPU usage.
- **To set up monitoring**:
  1. Install Helm: [Helm Installation Guide](https://helm.sh/docs/intro/install/)
  2. Add Prometheus Helm repo: `helm repo add prometheus-community https://prometheus-community.github.io/helm-charts`
  3. Install Prometheus: `helm install prometheus prometheus-community/prometheus`
  4. Install Grafana: `helm install grafana grafana/grafana`
  5. Get Grafana URL: `minikube service grafana --url`
  6. Log in to Grafana with default credentials (`admin/admin`) and configure Prometheus as a data source.

## Skills Demonstrated
- CI/CD automation with GitHub Actions
- Containerization with Docker
- Kubernetes orchestration (local and in CI/CD)
- Monitoring setup with Prometheus and Grafana
