helm-install:
	helm repo add superset https://apache.github.io/superset
	helm upgrade --install --values superset.yaml superset superset/superset

create-new-key:
	openssl rand -base64 42


install-make:
	yum install make -y

install-openssl:
	yum install openssl -y 

install-helm: install-openssl
	curl https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3 | bash

install: install-helm

install-k9s:
	curl -OL https://github.com/derailed/k9s/releases/download/v0.32.4/k9s_Linux_amd64.tar.gz

k8s-initialize:
	 kubeadm init --apiserver-advertise-address $(hostname -i) --pod-network-cidr 10.5.0.0/16

k8s-network:
	 kubectl apply -f https://raw.githubusercontent.com/cloudnativelabs/kube-router/master/daemonset/kubeadm-kuberouter.yaml
