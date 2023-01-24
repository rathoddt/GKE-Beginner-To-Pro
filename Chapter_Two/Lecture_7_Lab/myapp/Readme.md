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

# Monitoring, Logging, and Debgugging
`gcloud container clusters get-credentials cluster-1 --zone us-central1-c --project playground-s-11-b12d2812`  
`kubectl create deployment nginx --image nginx`  
`kubectl get deployments`  
`kubectls get pods`  
`kubectl get pods`  
`kubectl get all`  
`kubectl get events`  
`kubectl describe deployment nginx`  
`kubectl describe pod pod/nginx-8f458dc5b-xs979`  
`kubectl describe pod nginx-8f458dc5b-xs979`  
`kubectl expose deployment nginx --port=80 --type=LoadBalancer`  
`kubectl get all`  
`kubectl get logs nginx-8f458dc5b-xs979`  
`kubectl get logs logs/nginx-8f458dc5b-xs979`  
`kubectl get logs pods/nginx-8f458dc5b-xs979`  
`kubectl get logs pod/nginx-8f458dc5b-xs979`  
`kubectl logs pod/nginx-8f458dc5b-xs979`  
`kubectl logs nginx-8f458dc5b-xs979`  
`kubectl logs --selector app=nginx`  
`kubectl get all`  
`kubectl scale --replicas=10 deployment nginx`  
`kubectl get pods`  
`kubectl descibe deployment nginx`  
`kubectl describe deployment nginx`  
`kubectl get events`  
`kubectl scale --replicas=20 deployment nginx`  
`kubectl get pods`  
`kubectl scale --replicas=500 deployment nginx`  
`kubectl get pods`  
`kubectl scale --replicas=100 deployment nginx`  
`kubectl get pods`  
`kubectl get pods | grep Pending | wc -l`  
`kubectl scale --replicas=50 deployment nginx`  
`kubectl get pods | grep Pending | wc -l`  
`kubectl describe pod nginx-8f458dc5b-zl65k`  
`kubectl describe pods nginx-8f458dc5b-zl65k`  
`kubectl describe pod nginx-8f458dc5b-x2bjn`  
`kubectl describe pod nginx-8f458dc5b-w477c`  
`kubectl scale --replicas=15 deployment nginx`  
`kubectl get pods`  
`kubectl get pods | grep Pending | wc -l`  
`kubectl get pods`  
`kubectl scale --replicas=8 deployment nginx`  
`kubectl get pods`  
`kubectl scale --replicas=2 deployment nginx`  
`git clone https://github.com/rathoddt/GKE-Beginner-To-Pro.git`  
`cd GKE-Beginner-To-Pro/`  
`ls`  
`cd Chapter_T`  
`cd Chapter_Two/Lecture_7_Lab/`  
`ls`  
`cd myapp/`  
`ls`  
`cat requirements.txt`  
`echo "" > requirements.txt`  
`cat requirements.txt`  
`docker build -t myapp .`  
`docker tag myapp gcr.io/playground-s-11-b12d2812/myapp:broken`  
`docker push gcr.io/playground-s-11-b12d2812/myapp:broken`  
`kubectl nginx deployment nginx`  
`kubectl delete deployment nginx`  
`kubectl create deployment --image gcr.io/playground-s-11-b12d2812/myapp:broken badluck2`  
`kubectl get all`  
`watch kubectl get pods`  
`kubectl get pods`  
`kubectl describe pod badluck2-5896b5fdb-chmwr`  
`kubectl get pods`  
`kubectl logs badluck2-5896b5fdb-chmwr`  
`history`  
`man history`  
Printing history without libe no
`cat ~/.bash_history`  
`history -w /dev/stdout`  
`history | cut -c 8-`
