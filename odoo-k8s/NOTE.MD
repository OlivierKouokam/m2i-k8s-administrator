
sudo adduser nom_utilisateur

<!-- sudo usermod -aG sudo nom_utilisateur -->

su - nom_utilisateur



################### Vagrant ###################################################
kubectl apply -f https://raw.githubusercontent.com/metallb/metallb/v0.13.9/config/manifests/metallb-native.yaml
kubectl get all -n metallb-system
kubectl apply -f ip_address_pool/ipaddresspool.yml
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.7.0/deploy/static/provider/cloud/deploy.yaml

kubectl apply -f .

kubectl get svc -n ingress-nginx -o wide
# get external IP of ingress-nginx-controller service loadbalancer 
# update hosts file with : 192.168.99.150 pozos.m2iformation.fr

kubectl delete -f .