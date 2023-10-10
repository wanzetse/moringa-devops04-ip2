# Devops-04 IP2 PROJECT Explanation
#  Contents:

>- ### [Project Setup](#project-setup-1) 
>- ### [Client Docker File](#client-docker-file-1)
>- ### [Server Docker File](#server-docker-file-1)
>- ### [Docker Compose File](#docker-compose-file-1) 
>- ### [Github Workflows](#github-workflows-1)
>- ### [Images](#images-1)
>
# Project Setup:
-  ### Fork The repository (https://github.com/Vinge1718/yolo.git)
*  ### Clone the repository to a local environment:
 > - git clone https://github.com/Vinge1718/yolo.git
* ###  Install all project dependencies:
> - cd backend && npm install
> - cd client && npm install
* ###  Run the server and frontend app 
> - cd  backend && npm start
> - cd  client && npm start
* ###  Test the functionalities to ascertain the app works  as intendend.

# _______________________________________________________
# Client Docker File
> #### 
>- Navigate to client folder and create a dcokefile [ Client Docker File](client/Dockerfile)
>- Used **node:14-slim**  and **alpine:3.16.7** as base images
>- This was useful in getting node npm and nodjs commands installed and set up in the container
>
# _______________________________________________________

# Server Docker File
> #### 
>- Navigate to backend folder and create a dockefile [Client Docker File](backend/Dockerfile)
>- Used **node:14-slim**  and **alpine:3.16.7** as base images
>- This was useful in getting node npm and nodjs commands installed and set up in the container
>
# _______________________________________________________

# Docker Compose File

> ### [Docker Compose File](docker-compose.yaml)
> - #### Build 3 Services
>> - ###### Backend Service
>>> - Pulls and builds An image from docker hub [wanzetsemaloba/moringa-devops-04-ip2-server:v1.1.1](https://hub.docker.com/layers/wanzetsemaloba/moringa-devops-04-ip2-server/v1.1.1/images/sha256-cd4df338f5a60f83d00c33587df5d3329022f3ead2c1268c92d13ce8ced9c481?context=repo)
>>> -  Exposes port 5000
>>> - Specifies that it depends on [Mongo database service](#mongo-database-service)
 and  network as [creates-a-network-moringa-devops-04-ip2-net](#creates-a-network-moringa-devops-04-ip2-net)
>> - ###### Client Service
>>> - Pulls and Builds [wanzetsemaloba/moringa-devops-04-ip2-ui:v0.1.1](https://hub.docker.com/layers/wanzetsemaloba/moringa-devops-04-ip2-ui/v0.1.1/images/sha256-a1c95b90c43b7c02b977f6b243e690f897f818033c9a00c725470b4f5124f038?context=repo) Image from dockerhub
>>> - Exposes Port 3000
>>> - Specifies network as [creates-a-network-moringa-devops-04-ip2-net](#creates-a-network-moringa-devops-04-ip2-net)
>> - ###### Mongo Database Service
> - #### Creates A Network (**moringa-devops-04-ip2-net**)
> - #### Creates A docker Volume for Persistence of data (**moringa-devops-04-ip2-vol**)
# _______________________________________________________

# Github Workflows
### Git Workglows used
> ### The project has one workflow [ Github Build and Push](.github/workflows/moringa-devops-04-ip2-actions.yml)
>> - Triggered By a push to the repository
>> - Pulls the repository from github
>> - Builds both the client and server images
>> - Logins in to docker-hub
>> - Pushes the the two images to docker-hub
>> - Runs **docker compose down && docker compose up** to refresh the application 
>
# _____________________________________________________
# Images
## ![Server Docker-hub Image](/images/server-dh-image.png)
## ![Client Docker-hub Image](/images/ui-dh-image.png)