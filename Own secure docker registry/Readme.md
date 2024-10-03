mkdir -p /var/myregistry/data
mkdir -p /var/myregistry/auth
mkdir -p /var/myregistry/certs
ll /var/myregistry/
total 20
drwxr-xr-x  5 root root 4096 Oct  3 19:47 ./
drwxr-xr-x 15 root root 4096 Oct  3 19:46 ../
drwxr-xr-x  2 root root 4096 Oct  3 19:46 auth/
drwxr-xr-x  2 root root 4096 Oct  3 19:47 certs/
drwxr-xr-x  2 root root 4096 Oct  3 19:46 data/

docker run --entrypoint htpasswd httpd:2 -Bbn user password123 > /var/myregistry/auth/htpasswd

Generation own cert

openssl req -newkey rsa:4096 -nodes -sha256 -keyout /var/myregistry/certs/domain.key -x509 -days 365 -out /var/myregistry/certs/domain.crt
