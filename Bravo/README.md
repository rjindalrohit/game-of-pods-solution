1) create folder on node01 <br>
 ssh node01 "mkdir -p /drupal-data /drupal-mysql-data"
2) create secret using below cmd. <br>
kubectl create secret generic drupal-mysql-secret --from-literal=MYSQL_ROOT_PASSWORD=root_password --from-literal=MYSQL_DATABASE=drupal-database --from-literal=MYSQL_USER=root
3) Create complete deployment using Bravo.yaml
kubectl apply -f Bravo.yaml

