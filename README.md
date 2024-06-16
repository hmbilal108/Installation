DOCKER, KUBECTL, MINIKUBE, CONNTRACK and HELM and ARGOCD (Thanks to Uzair Ahmad Linkedin from Simplified Application Deployment: Mastering Helm Charts with ArgoCD Workflow)

sudo su

sudo apt update && apt -y install docker.io


Kubectl:

curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"

chmod +x kubectl

sudo mv kubectl /usr/local/bin/

kubectl version --short


Minikube:

curl -Lo minikube https://github.com/kubernetes/minikube/releases/download/v1.24.0/minikube-linux-amd64 && chmod +x minikube && sudo mv minikube /usr/local/bin/

apt install conntrack

minikube start --vm-driver=none

minikube status


Helm:

curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3

chmod 700 get_helm.sh

./get_helm.sh

which helm

ArgoCD:

kubectl create namespace argocd

kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

kubectl get all -n argocd

(ClusterIP -> NodePort)

kubectl edit svc argocd-server -n argocd

kubectl get svc -n argocd

Now try to access it theough internet, Copy the public ip of your instance from your console and access it on port 32662.
NOTE : Open port <32662>(in my case) in your security group 

default use name is admin

kubectl get secrets argocd-initial-admin-secret -n argocd -o yaml 

echo VFBrWVlyZ1NXc0xJTUpYYw== | base64 --decode

write application name (mongo/mongo-express)
select project name(default)
select sync option (autometic)
Put repo link and select path, first time path is mongo and in second application path is mongo-express.
Select destination , select default cluster that argocd show you.
At destination use default namedpace.




















