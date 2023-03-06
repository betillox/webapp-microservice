# Web Application Deployed with K8s.

- How to run it?

Go to the directory where you have pulled the code from github.
Execute the following command

$kubectl create -f . 

Or if you want to run it using another namespace to separate workspace use:
 
$kubectl create namespace {namespace}

Validate:

$kubectl get namespaces

Now run it but this time using: 

kubectl create -f . -n {namespace}

- How to validate the K8s objects created?

kubectl get pods,deployments,service,pv --namespace={namespace}

- How to access the application?
Check the NodePort created by executing the command, you will notice a NodePort Service created with a specific port 31081 as per configuration setup on test-web-service.yaml file.

$kubectl get services
$kubectl get services -n {namespace}

Access the application by concatenating the IP of the node (or localhost if running a local instance)

[IP_ADDRESS / localhost]:[NODEPORT_PORT]
Architecture Diagram
Microservice Application
