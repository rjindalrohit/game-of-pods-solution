1) Create Dir for persistant volume on node01
   ssh node01 "mkdir -p redis0{1..6}"
2) apply pv_redis_cluster.yaml to create volume and bring up cluster pods.
   kubectl apply -f pv_redis_cluster.yaml
3) exectue cmd mentioned in chalange for creating cluster.

kubectl exec -it redis-cluster-0 -- redis-cli --cluster create --cluster-replicas 1 $(kubectl get pods -l app=redis-cluster -o jsonpath='{range.items[*]}{.status.podIP}:6379 ')

4) apply redis-cluster-service.yaml to create services.
   kubectl apply -f redis-cluster-service.yaml

