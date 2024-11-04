
 


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



