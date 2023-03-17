# kubernetes-volumes
For adding volumes in kubetes, PersistentVolume and PersistentVolumeClaim

#Pre-requisites 

1. Install kubernetes with minikube and Install kubectl
2. minikube start 

# Minikubes commands
 kubectl version --client
 minikube delete
 minikube status
 minikube dashboard
 minikube dashboard --url

 3. Build and push images to docker hub.
    
    docker build -t barnmutahi/kube-vol-1-app .
    docker tag kube-vol-1-app barnmutahi/kube-vol-1-app && docker push barnmutahi/kube-vol-1-app
    <!-- docker tag kube-vol-1-app barnmutahi/kube-vol-1-app && docker push barnmutahi/kube-vol-1-app -->
 
 4. Apply the yaml files inside the kubernetes folder i.e
     
      -> kubectl apply -f=deployment.yaml -f=environment.yaml -f=host-pv.yaml f=host-pvc.yaml -f=service.yaml

 5. Start the service that will be exposed outside the cluster.The one that interact with users outside
     ->  minikube service story-service
      This applies for minikube, If you are using Kubernetes provided by cloud will not need to start the service, ie EKS 
 6. Now you can acces your cluster     

     # Test Via postman 
    post-> http://127.0.0.1:1224/story
    get-> http://127.0.0.1:1224/story
    get-> http://127.0.0.1:1224/error

     {
   "text":"my text 10" 
      }


     
         
 