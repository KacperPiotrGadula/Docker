docker system df

TYPE            TOTAL     ACTIVE    SIZE      RECLAIMABLE
Images          21        3         6.211GB   5.361GB (86%)
Containers      3         3         208.9kB   0B (0%)
Local Volumes   28        3         587.3MB   587.1MB (99%)
Build Cache     39        0         1.265GB   1.265GB

docker network prune

5b29f674404779be561db2d0bd932aa3640ae67b9e1# docker network prune
WARNING! This will remove all custom networks not used by at least one container.
Are you sure you want to continue? [y/N] y
Deleted Networks:
cos-3_default
remotestoragedriverfordockerregistry_default
apparmorandselinux_default