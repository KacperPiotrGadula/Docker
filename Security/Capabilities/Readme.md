# Add and remove capabilities

docker container run --rm -it alpine chown nobody /

docker container run --rm -it --cap-drop ALL \
    --cap-add CHOWN alpine chown nobody /

docker container run --rm -it --cap-drop CHOWN \
     alpine chown nobody /

docker container run --rm -it --cap-add CHOWN \
     -u nobody alpine chown nobody /

https://man7.org/linux/man-pages/man7/capabilities.7.html

!! Capabilities can only be added and removed for root in the container !!