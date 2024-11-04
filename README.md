**Steps to deploy mongoDB and mongoExpress app**
 
ls
mongo-configmap.yaml  mongo-express.yaml  mongo-secret.yaml  mongo.yaml

kubectl apply -f mongo-secret.yaml

kubectl apply -f mongo.yaml



kubectl apply -f mongo-configmap.yaml

kubectl apply -f mongo-express.yaml


kubectl get all



 kubectl describe pod/mongo-express-85d8576d55-xl95l

 kubectl logs mongo-express-85d8576d55-xl95l

**To access mongo-express service from the browser/outside, we need to assign a Public IP to access it.**
**But as we are running single node cluster in minikube, minikube has workaround for this.**

minikube service mongo-express-service

Above minikube will give following output, 

|-----------|-----------------------|-------------|-----------------------------|
| NAMESPACE |         NAME          | TARGET PORT |             URL             |
|-----------|-----------------------|-------------|-----------------------------|
| default   | mongo-express-service |        8081 | http://192.168.59.100:30000 |
|-----------|-----------------------|-------------|-----------------------------|



Now go to your web browser(on same machine) and enter the url
It will take you to mongo-express web interface.





**Steps to get all deployments, pods and corresponding services**

  kubectl get all,
  
  kubectl get configmap,
  
  kubectl get secret,

**Steps to delete the cluster of mongoDB and mongoExpress via configuration yaml files**

**Delete mongoDB deployment, service(as service is also configured in mongo.yaml file, service will also get deleted when deployment gets deleted) and pods**

  kubectl delete -f mongo.yaml (This will delete mongo database deployment, service and pods)

**Delete mongoexpress deployment, service(as service is also configured in mongo-express.yaml file, service will also get deleted when deployment gets deleted) and pods**
  
  kubectl delete -f mongo-express.yaml (This will delete mongo-express deployment, service and pods)

  kubectl delete configmap mongodb-configmap
  
  kubectl delete configmap mongodb-secret



