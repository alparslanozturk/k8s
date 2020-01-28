# Kubernetes Kurulum Notları

1. https://www.katacoda.com/


## Dashboard kurulumu 2.0  (dashboard.txt)



## Hata giderme :-)


1. kubelet servisinde özel ayarlar   ( gibi https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/kubelet-integration/#kubelet-configuration-patterns)


root@deb2:~# vim /var/lib/kubelet/config.yaml

apiVersion: kubelet.config.k8s.io/v1beta1
kind: KubeletConfiguration
cgroupDriver: systemd


son satırl CgroupDriver eklenir. 



2. master rolu kaldirilmasi hk. 

 kubectl taint nodes --all node-role.kubernetes.io/master-


3.  bir deployu edit etmek hk. 

root@deb1:~# kubectl get deployment -A
NAMESPACE     NAME      READY   UP-TO-DATE   AVAILABLE   AGE
kube-system   coredns   2/2     2            2           21h

kubectl -n kube-system edit deployment coredns

