  `cd myapp/`   
   `docker build -t myapp .`   
  `ls` 
   `mv Dokerfile Dockerfile`  
  `docker build -t myapp .`  
 `docker tag gcr.io/dilip-rathod/myapp-blue`  
`docker tag myapp gcr.io/dilip-rathod/myapp-blue`  
`docker image ls`  
`docker push gcr.io/dilip-rathod/myapp-blue`  
`docker push gcr.io/playground-s-11-984d7f62/myapp-blue`  
`docker tag myapp gcr.io/playground-s-11-984d7f62/myapp:blue`  
`docker push gcr.io/playground-s-11-984d7f62/myapp:blue` 
`docker build -t myapp .`  
`docker tag myapp gcr.io/playground-s-11-984d7f62/myapp:green`   
`docker image ls`  
`docker push gcr.io/playground-s-11-984d7f62/myapp:green`  
`docker build -t myapp .`   
`docker tag myapp gcr.io/playground-s-11-984d7f62/myapp:bad` 
`37  docker push gcr.io/playground-s-11-984d7f62/myapp:bad
`38  ls` 
`39  kubectl apply -f myapp-deployment.yaml` 
`41  kubectl get pods` 
`42  kubectl describe deployment myapp-deployment` 
`43  kubectl get deploymentv
`44  kubectl describe deployment mayapp-deployment` 
`46  kubectl apply -f myapp-service.yaml` 
`47  kubectl get svc` 
`48  kubectl get pods` 
`49  kubectl delete pod mayapp-deployment-56cfcdf9df-pfxpp` 
`50  kubectl get pods` 
`52  kubectl get pods -o=custom-columns=NODE:.spec.nodeName,NAME:.metadata.name` 
`54  kubectl taint nodes gke-cluster-02-default-pool-ce7e5c41-v3f8 key=value:NoSchedule` 
`kubectl get pods -o=custom-columns=NODE:.spec.nodeName,NAME:.metadata.namev
`kubectl delete pod mayapp-deployment-56cfcdf9df-5bx7c` 
Untaint the node
`kubectl taint nodes gke-cluster-02-default-pool-ce7e5c41-v3f8 key=value:NoSchedule-` 

It is deployment controllers job to make sure that we have correct no of replicas in our replicaset
 
kubectl deployment -f myapp-deployment.yaml --recordv
--record to log that it was this command that updated the deployment

We can view the status of rollout status 
kubectl rollout status deployment.v1.apps/myapp-deployment` 
kubectl rollout history deployment.v1.apps/myapp-deployment` 
kubectl rollout undo deployment.v1.apps/myapp-deployment` 
