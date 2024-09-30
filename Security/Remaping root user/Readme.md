Edit /etc/docker/daemon.json

{
    "userns-remap": "default"
}

Than we should restart docker

1) systemctl restart docker

After that - every another operation what we proceed in docker, that are saving in another folder and process in container have root privilege