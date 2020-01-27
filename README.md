# Kubernetes Kurulum Notları

## Dashboard kurulumu 2.0 

1. kurulumun "kubernetes-dashboard" adindaki namespace kurulduguna dikkat ediniz. 



kubectl create -f https://raw.githubusercontent.com/kubernetes/dashboard/master/src/deploy/recommended/kubernetes-dashboard.yaml



2.  "kube proxy " çalıştırdıktan sonra 


localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/



3.  kurulumu tamamlamak için bir dizi hesaplar açmak gerekiyor...


kubectl create serviceaccount dashboard -n default
kubectl create clusterrolebinding dashboard-admin -n default  --clusterrole=cluster-admin  --serviceaccount=default:dashboard


4. token asagidaki komutlar görülebilir. 


kubectl get secret $(kubectl get serviceaccount dashboard -o jsonpath="{.secrets[0].name}") -o jsonpath="{.data.token}" | base64 --decode


