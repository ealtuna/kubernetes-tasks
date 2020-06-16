helm install superset ../superset-helm/superset-vv/
kubectl get service

```
kubernetes                 ClusterIP      10.96.0.1       <none>        443/TCP          79m
superset-superset-vv       ClusterIP      10.101.89.211   <none>        80/TCP           78m
```

kubectl expose deployment superset-superset-vv --type=LoadBalancer --name=superset-superset-vv-ext

```
kubernetes                 ClusterIP      10.96.0.1       <none>        443/TCP          79m
superset-superset-vv       ClusterIP      10.101.89.211   <none>        80/TCP           78m
superset-superset-vv-ext   LoadBalancer   10.96.177.255   <pending>     8088:30054/TCP   10s
```

minikube service superset-superset-vv-ext

