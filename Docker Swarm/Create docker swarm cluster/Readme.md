# Summary

- adding warkers → typical machine to store containers
- adding managers → each manager can create new services, can manage the cluster, can add more machines to the cluster

docker node promote <node_name> -> promote node to manager
docker node demote <node_name> -> down grade node to worker
docker node ls -> view nodes list