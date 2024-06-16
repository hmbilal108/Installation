DOCKER, KUBECTL, MINIKUBE, CONNTRACK and HELM and ARGOCD (Thanks to Uzair Ahmad Linkedin from Simplified Application Deployment: Mastering Helm Charts with ArgoCD Workflow)

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
