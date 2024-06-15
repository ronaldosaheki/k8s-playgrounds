helm-install:
	helm repo add superset https://apache.github.io/superset
	helm upgrade --install --values superset.yaml superset superset/superset

create-new-key:
	openssl rand -base64 42