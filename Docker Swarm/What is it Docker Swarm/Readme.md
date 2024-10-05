# Information

- docker swarm is integrated into docker engine
- when you have several or several applications at your disposal, docker swarm helps to manage them all at once
- docker swarm helps to merge applications
    - Supports redirection of traffic to different docker containers of the same application.
    - docker swarm allows the creation of several instances at the same time using a single parameter
- service discovery helps to identify the type of traffic directed to the infrastructure
- a container cluster is created
- continuous monitoring of the cluster


# Check docker swarm node

root@DESKTOP-E9H427N:/home/dell# docker node ls
ID                            HOSTNAME         STATUS    AVAILABILITY   MANAGER STATUS   ENGINE VERSION
ps92axp75jg90wk7mj3lqksxu *   docker-desktop   Ready     Active         Leader           27.2.0
root@DESKTOP-E9H427N:/home/dell# docker node inspect docker-desktop --pretty
ID:                     ps92axp75jg90wk7mj3lqksxu
Hostname:               docker-desktop
Joined at:              2024-10-05 11:49:53.844916555 +0000 utc
Status:
 State:                 Ready
 Availability:          Active
 Address:               192.168.65.3
Manager Status:
 Address:               192.168.65.3:2377
 Raft Status:           Reachable
 Leader:                Yes
Platform:
 Operating System:      linux
 Architecture:          x86_64
Resources:
 CPUs:                  4
 Memory:                13.6GiB
Plugins:
 Log:           awslogs, fluentd, gcplogs, gelf, journald, json-file, local, splunk, syslog
 Network:               bridge, host, ipvlan, macvlan, null, overlay
 Volume:                local
Engine Version:         27.2.0