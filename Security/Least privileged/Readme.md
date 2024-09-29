Booting the container in root mode

docker run -itd --name ubuntu-defaultuser \
    -v /:/hacking ubuntu /bin/bash

docker container top ubuntu-defaultuser

Starting a container in non-root mode

docker run -itd --user 998 --name ubuntu-customuser \
    -v /:/hacking ubuntu /bin/bash

docker container top ubuntu-customuser