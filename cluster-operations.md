## Deploy a new app

First workload to deploy: 
    rancher/hello-world

## Upgrade an app

Change the workload:    
    nginxdemos/hello

## Upgrade Fail && Rollback

Change the workload:
    hello-world

## Node maintenance

kubectl get pods
kubectl describe pod hello
kubectl drain node-0