================= 
NOTICE: kind will behave strange and cranky after 1 day…probably since it is run from cache…so to "RECREATE" the entire cluster config:

  kind delete cluster
  kind create cluster --config ~/environment/000-four-node-cluster.yaml
  kind load docker-image demo:1.0.0
  kubectl -n dev apply -f ~/environment/001-dev-namespace.yaml 
  kubectl -n dev apply -f ~/environment/001-test-namespace.yaml
  kubectl -n dev apply -f ~/environment/005-demo-deployment.yaml    #use your latest
  kubectl get deploy,rs,po -n dev -o wide
================