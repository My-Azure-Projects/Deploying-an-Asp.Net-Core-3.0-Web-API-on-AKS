# Containerize .NET Core 3.1 Web API using Docker


## Prerequisites
1. Install docker desktop on windows machine

2. Install Azure CLI on windows machine

3. Create Service Principal in Azure AD

4. Create Azure Container Registry

5. Configure RBAC in Azure Container Registry (Acrpull) for the Service Principal


## Docker Commands

### Get docker version details
docker version

### Get docker version number
docker --version

### Get list of docker images
docker images

### Remove a docker image
docker rmi -f 46e18b10d5fe

### Build docker image
docker build -t weatherapi:v1 .

*NOTE: . denotes the current directory*

### Retag docker image to ACR (Azure Container Registry)
docker tag weatherapi:v1 acrweather.azurecr.io/weatherapi:v1

### Login to Azure Portal
az login

*NOTE: This opens up the Azure AD login page, enter the credential & login should happen*

### Login to Azure Container Registry
az acr login --name acrweather

*NOTE: Login to the Azure Container Registry. This step is important, else you will get unauthorized error while pushing images to ACR*

### Push docker images to ACR
docker push acrweather.azurecr.io/weatherapi:v1


