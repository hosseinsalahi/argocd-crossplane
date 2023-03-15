eksctl create cluster --name lab-cluster --version 1.25
eksctl utils write-kubeconfig --cluster lab-cluster -f ~/.kube/lab-aws

helm install arocd \
--namespace arocd \
--create-namespace argo/argo-cd 

helm install crossplane \
--namespace crossplane-system \
--create-namespace crossplane-stable/crossplane



