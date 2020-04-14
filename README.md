# RBAC
RBAC authentication to the cluster in k8s

#Steps for creating certificate for user ajinkya

1. openssl genrsa -out ajinkya.key 2048

2. openssl req -new -key ajinkya.key -out ajinkya.csr -subj "/CN=ajinkya/O=finance"

3. penssl x509 -req -in ajinkya.csr -CA ca.crt -CAkey ca.key -CAcreateserial  -out ajinkya.crt -days 365

#Steps for creating a role

1. kubectl create role ajinkya-finance --verb=get,list --resource=pod --namespace finance

2. kubectl create rolebinding ajinkya-finance-rolebinding --role=ajinkya-finance --user=ajinkya --namespace finance 
