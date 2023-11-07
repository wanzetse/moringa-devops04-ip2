### IP$ Explanation.
Created  Directory Manifiests..

-- Added files 
    client.yml --Frontent Ui
    database.yml ---For Mongo Db Deploynent
    server.yml ----Backend UI

-- commands used To deploy The applications in order of execution
        cd manifets.
        kubectl apply database.yml
        kubectl apply  server.yml 
        kubectl apply client.yml
        minikube start.
    
## Testing.
kubectl get all -w --- List avaialble pods and watch their statuses.
kubectl describe {pod-name}   --- for all pod names


# Deployment to the world.

-- kubectl expose deployment appserver --name=app-service-server --type=LoadBalancer --port 80 --target-port 5000
-- kubectl expose deployment client-app --name=app-service-client --type=LoadBalancer --port 80 --target-port 3000

## to get Exposed Deployements foe=r world reading.
  kubectl get service



## Google cloud Deployment (GKE Cluster)

- Start Shell
- Git Clone The project. (git clone https://github.com/wanzetse/moringa-devops04-ip2.git ip4)
- cd ip2/manifests
- kubectl version   -- check that kubectl is enabled. 
# Run All previous commands as run locally
# Expose The deployment 
- kubectl expose deployment appserver --name=app-service-server --type=LoadBalancer --port 80 --target-port 5000

### Exposed Url  (http://34.162.9.196/)


