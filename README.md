# Docker & Kubernetes Notes
Containirize dotnet core web Api using Docker, push to Azure Container Registry and deploy to Kubernetes cluster in AKS


## Pre-requisites
1. Install docker desktop on windows machine

2. Install Azure CLI on windows machine

3. Create Service Principal in Azure AD

4. Create Azure Container Registry

5. Configure RBAC in Azure Container Registry (Acrpull) for the Service Principal



## [Docker - Containerize dotnet core Web Api](https://github.com/nidhisht/DockerKubernetesNotes/blob/master/README-Docker.md)



## Service Principal

1. az login

2. az account show

3. az ad sp create-for-rbac --skip-assignment


## Azure Container Registry - Push Docker images

1. az acr login --name retailcontainerregistry

2. docker images

3. docker tag orderservice:v2 retailcontainerregistry.azurecr.io/orderservice:v2

4. docker images

5. docker push retailcontainerregistry.azurecr.io/orderservice:v2

## Azure Kubernetes Service - Create Kubernetes Cluster & run containers

1. az aks get-credentials --resource-group rg-cosmos --name retailkubernetescluster

2. kubectl get nodes

3. kubectl apply -f .\Deployment.yml

4. kubectl get deployment

5. kubectl get pods

6. kubectl apply -f .\Service.yml

7. kubectl get services

### [Reference](https://www.youtube.com/watch?v=vBx7WY25fM0)
