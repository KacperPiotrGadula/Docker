Contents of file /etc/docker/daemon.json

{
  "tls": true,
  "tlscacert": "/etc/docker/ssl/ca.pem",
  "tlscert": "/etc/docker/ssl/server-cert.pem",
  "tlskey": "/etc/docker/ssl/server-key.pem",
  "hosts":["unix:///var/run/docker.sock","tcp://0.0.0.0:2376"]
}