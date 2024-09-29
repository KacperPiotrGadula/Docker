Display of the current logging controller:

docker info --format '{{.LoggingDriver}}'

Change the login driver (/etc/docker/daemon.json):

{
    "log-driver": "TYP_STEROWNIKA"
}