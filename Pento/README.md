# game-of-pods-Pento-solution
1) go to /etc/kubernetes/mainfest
2) Update line in file kube-apiserver.yaml <br>
	from :- 
	/etc/kubernetes/pki/ca-authority.crt <br>
	to:- 
	/etc/kubernetes/pki/ca.crt <br>
3) update port to 6443 in /root/.kube/config file
4) update the image in coredns deployment 
kubectl edit deployment coredns -n kube-system
5) kubectl uncordon node01

6) kubectl create -f pento.yaml
