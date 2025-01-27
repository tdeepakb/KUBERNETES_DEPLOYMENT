# KUBERNETES_DEPLOYMENT

**COMPANY**: CODTECH IT SOLUTIONS

**NAME**: DEEPAK PRASAD

**INTERN ID**: CT6WGAP

**DOMAIN**: DEVOPS

**BATCH DURATION**: DECEMBER 25th, 2024 to FEBRUARY 10th, 2025

**MENTOR NAME**: NEELA SANTHOSH

# ENTER DESCRIPTION OF TASK PERFORMED NOT LESS THAN 500 WORDS

# OUTPUT OF THE TASKS

![Image](https://github.com/user-attachments/assets/bbf8fe2b-6f23-4fbb-a89f-6500bbd0985e)

Deploy a microservices based application on a kubernetes cluster.
for this i have to create launch ec2 machine like i will select amazon machine image ubuntu
select instance type t2 medium choose key pairs and select configure security groups
or create security groups here. after this you will take storage 20 gb and magnetic storage.
at last launch the instance and connect it to ec2 instance connect so that we will deploy a microservice
based application on a kubernetes cluster.
first update our linux machine sudo apt-get update it will update and install docker
sudo apt install docker.io  after installing docker i will install minikube so that i will deploy
the microservices kubernetes deployment.
i will paste all installing minikube command here i have used minikube.
wget https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo cp minikube-linux-amd64 /usr/local/bin/minikube
sudo chmod +x /usr/local/bin/minikube
Installing kubectl
curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl
chmod +x kubectl
sudo mv kubectl /usr/local/bin/
Starting Minikube
sudo usermod -aG docker $USER && newgrp docker
 minikube start --driver=docker
after installation of minikube you will create deployment name.
vi nginx-deployment.yaml and inside i will write apiVersion kind deployment
metadata, name of the deployment nginx-deployment, spec, replicas- 3, selector, matchlabels,
app- nginx, template, metadata, labels, app-nginx, spec, containers, name, image, ports, and contianer port 80.
This all details i will put inside the nginx-deployment.yaml file and then i will apply it.
kubectl apply -f nginx-deployment command i write then it will create deployment and here 
deployment will create replicaset for you and replicaset having controller manager it will see
first if current state is equal to desired state then it is ok if it is not equal to then controller manager will 
say to kube api server that current state is not equal to desire state then kube api server will ask to schedular
go and check which node having better choice then schedular will decide node 2 is better option to install so schedular
will tell kube api server node 2 is better option so then kube api server will tell to kubelet of node 2 that you can
install one pod or else. then kubelet will tell to RUNC and Runc will download pod for this. 
This whole process will take internally and within a second you can not realise it but it will act very fast. and create 
automatically pods for you.
In deployment there is rolling update strategy 25% max surge available in deployment so here 
there is no any downtime in deployment
if you will describe deployments then you can see there is written there rolling update strategy this will help
alot when your machines use by someone like if someone will delete the pod or replica set then the pod and replica set 
will automatically get back within a second.pod replica set never get deleted
untill unless you do not delete the deployment. as i mentioned above. This is advantage of deployment.
if you want to scale up and scale down the deployment like you want 5 pod you can scale up easily in this deployment.
