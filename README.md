 dev
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

# DevOps Final Lab — Question 1

## Student Information

**Name:** Falak Naz
**Student ID:** JUWV34055
**Seat Number:** 2329151
**Course:** DevOps


## Repository

**DevOps-b-2329151**

**https://github.com/falaknaz433/DevOps-b-2329151**



## Implementation

The required webpage was created at:

```text
site/index.html
```

The page contains:

* An event heading
* Three planned activities
* Seat number `2329151` displayed visibly

## Planned Activities

The webpage contains the following three activities:

1. Opening Ceremony
2. Technical Workshop
3. Closing Ceremony

## Evidence / Screenshots

### 1. Repository Structure

Screenshot showing the GitHub repository and the `site/index.html` file.



<img width="1081" height="734" alt="image" src="https://github.com/user-attachments/assets/9b26ffb5-3ec3-437b-9631-82a9f630bb3e" />

<img width="1081" height="734" alt="image" src="https://github.com/user-attachments/assets/7c39b66b-3f3c-4dad-be3f-b9ee5ff068ec" />

<img width="975" height="675" alt="image" src="https://github.com/user-attachments/assets/a26224b5-9f5f-4718-ab00-4c17c8a314da" />

<img width="975" height="741" alt="image" src="https://github.com/user-attachments/assets/a21d126a-1698-4a3f-9acc-c19d863b3680" />


### 2. index.html Code

Screenshot showing the contents of `site/index.html`, including the event heading, three planned activities, and visible seat number.


<img width="505" height="493" alt="image" src="https://github.com/user-attachments/assets/f0930c52-5bd2-4f7e-a0f6-4741a5755c95" />


### 3. Website Output

Screenshot showing the completed webpage in the browser with the event heading, three activities, and seat number `2329151` visibly displayed.

<img width="588" height="337" alt="image" src="https://github.com/user-attachments/assets/b4095258-7673-4154-ab59-0f8a49099458" />

main
