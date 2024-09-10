version: ‘3.7’ 

in docker-compose.yml refers to the version of the schema that Docker Compose uses to understand and interpret this file. This version defines what features, options and capabilities are available in the docker-compose.yml file, as well as how Docker Compose should work for certain configurations.

3.x: The 3.x versions are mainly dedicated for use in production environments, especially in combination with Docker Swarm Mode (for container orchestration). The 3.x series also introduced changes in the way networking, volumes and service configuration are handled compared to earlier versions such as 2.x.

7: Version 3.7 denotes a specific iteration of the schema that was introduced with a specific version of Docker and Docker Compose (Docker Engine 18.06). Versions in the 3.x series are still backward compatible (e.g. version 3.7 supports everything that was available in 3.6).