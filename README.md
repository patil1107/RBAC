# RBAC
RBAC authentication to the cluster in k8s

#Steps for creating certificate for user ajinkya

1. penssl genrsa -out ajinkya.key 2048

2. openssl req -new -key ajinkya.key -out ajinkya.csr -subj "/CN=ajinkya/O=finance"

3. penssl x509 -req -in ajinkya.csr -CA ca.crt -CAkey ca.key -CAcreateserial  -out ajinkya.crt -days 365
