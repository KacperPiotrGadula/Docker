# Azure Blob Storage

docker run -d \
  --restart=always \
  --name registry \
  -v /var/myregistry/certs:/certs \
  -v /var/myregistry/auth:/auth \
  -e REGISTRY_AUTH=htpasswd \
  -e REGISTRY_AUTH_HTPASSWD_PATH=auth/htpasswd \
  -e REGISTRY_AUTH_HTPASSWD_REALM=realm \
  -e REGISTRY_HTTP_ADDR=0.0.0.0:443 \
  -e REGISTRY_HTTP_TLS_CERTIFICATE=/certs/domain.crt \
  -e REGISTRY_HTTP_TLS_KEY=/certs/domain.key \
  -e REGISTRY_STORAGE=azure \
  -e REGISTRY_STORAGE_AZURE_ACCOUNTNAME=<account_name_here> \
  -e REGISTRY_STORAGE_AZURE_ACCOUNTKEY=<key_here> \
  -e REGISTRY_STORAGE_AZURE_CONTAINER=<container_name_here> \
  -p 5043:443 \
  registry:2

# Run Docker Registry UI

docker container run -d -e ENV_DOCKER_REGISTRY_HOST=localhost -e ENV_DOCKER_REGISTRY_PORT=5000 -e ENV_DOCKER_REGISTRY_USE_SSL=1 -p 8080:80 --name registry-ui konradkleine/docker-registry-frontend:v2