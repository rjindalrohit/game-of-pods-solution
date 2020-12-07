1) Apply tyro.yaml

   kubectl apply -f tyro.yaml
   
 2) Create User in kubeconfig
 
    kubectl config  set-credentials drogo  --client-certificate=/root/drogo.crt --client-key=/root/drogo.key
    
  3) Create context in kubeconfig
  
    kubectl config set-context developer --user=drogo --cluster=kubernetes --namespace=development
    
  4) Switch to 'developer' context
  
    kubectl config use-context developer
