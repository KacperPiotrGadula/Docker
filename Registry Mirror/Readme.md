1. the user downloading the image checks whether it is in the local registry
2. if it is, the container starts using the image from the local registry
3. if it is not, it downloads the local docker registry from the docker hub image, saves it to itself and passes it to the user to run the container.