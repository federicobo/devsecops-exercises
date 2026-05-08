# create namespace
kubectl create namespace dso-apps

# redis-leader deployment and service
kubectl apply -f redis-leader-deployment.yaml
kubectl apply -f redis-leader-service.yaml

# redis-follower deployment and service
kubectl apply -f redis-follower-deployment.yaml
kubectl apply -f redis-follower-service.yaml

# frontend deployment and service
kubectl apply -f frontend-deployment.yaml
kubectl apply -f frontend-service.yaml
kubectl scale deployment frontend --replicas=5
