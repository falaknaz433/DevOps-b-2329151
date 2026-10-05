# DevOps Final Lab - Set B

## Student Information

- **Name:** Falak Naz
- **Student ID:** JUW34055
- **Seat Number:** 2329151
- **Course:** DevOps

## Repository

- Repository: https://github.com/falaknaz433/DevOps-b-2329151/tree/dev
- GitHub Pages: https://falaknaz433.github.io/DevOps-b-2329151/

The same website is served locally using Docker and Minikube.

| Item | Name |
|------|------|
| Docker image | `devops-b-2329151:v1` |
| Docker container | `devops-b-2329151` |
| Kubernetes Deployment | `devops-b-2329151` |
| Kubernetes Service | `devops-b-2329151` |

### Files

- `Dockerfile`: uses `nginx:alpine` and copies only `site/` into the nginx web root.
- `deployment.yaml`: Deployment with one replica, container port 80 and `imagePullPolicy: IfNotPresent` so the locally loaded image is used.
- `service.yaml`: NodePort Service on port 80, target port 80, selecting the Deployment's Pods by label.

### Run with Docker

```bash
docker build -t devops-b-2329151:v1 .
docker run -d --name devops-b-2329151 -p 8080:80 devops-b-2329151:v1
```

Open http://localhost:8080

### Run with Minikube

```bash
minikube start --driver=docker
minikube image load devops-b-2329151:v1
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
minikube service devops-b-2329151 --url
```

### Scale the Deployment

```bash
kubectl scale deployment devops-b-2329151 --replicas=2
kubectl get pods
kubectl get deployment devops-b-2329151
```

- `main`: final code and the GitHub Pages workflow
- `dev`: second branch
