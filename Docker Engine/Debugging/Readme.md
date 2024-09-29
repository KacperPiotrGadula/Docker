Turn on debug (/etc/docker/daemon.json):

{
    "debug": true
}


# Debugging networking

1 Start the container from the **nicolaka/netshoot** image.

**docker run -it --net container:nginx_net2 nicolaka/netshoot tcpdump -i eth0 port 80 -c 1 -Xvv**

- the --net flag indicates the name of the container whose networking you want to monitor
- the -i flag indicates the name of the interface of the container whose traffic we want to observe