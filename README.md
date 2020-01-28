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



