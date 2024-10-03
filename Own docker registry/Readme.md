sudo mkdir -p /var/myregistry/data
sudo mkdir -p /var/myregistry/auth
sudo su

The docker container is started, which has to encrypt the password and put it in the indicated path. In this case:
- user name -> user
- password -> password123

docker run --entrypoint htpasswd httpd:2 -Bbn user password123 > /var/myregistry/auth/htpasswd

Run docker registry with the appropriate parameters to set the authentication credentials

docker container run -p 5000:5000 -d \
    -e REGISTRY_AUTH=htpasswd \
    -e REGISTRY_AUTH_HTPASSWD_PATH=auth/htpasswd \
    -e REGISTRY_AUTH_HTPASSWD_REALM=realm \
    -v /var/myregistry/data:/var/lib/registry \
    -v /var/myregistry/auth:/auth \
    --name myregistry \
    --restart always \
    registry:2