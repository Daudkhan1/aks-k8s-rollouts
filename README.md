## Progressive Delivery of Node.js Application on Kubernetes using Argo Rollouts
# Create a service account
kubectl create sa jenkins-admin -n default

#Create a Secret for the Service Account
kubectl create secret generic jenkins-admin-secret \
  --from-literal=token="" \
  --namespace devops-tool

#Patch the Secret with the Service Account
kubectl patch serviceaccount jenkins-admin -n default -p '{"secrets": [{"name": "jenkins-admin-secret"}]}'

Retrieve and Decode the Token
kubectl get secret jenkins-admin-secret -n devops-tool -o jsonpath="{.data.token}" | base64 --decode
token = 


daudidrees/aks-k8s-rollouts:46
if the deployment is failed the the image