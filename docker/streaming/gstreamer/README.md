# Streaming Container #

Container with tools for video streaming.

License: according to LICENSE.md in the root directory of the PX4 Firmware repository

There multiple Docker images built from this [repository](https://github.com/PX4/containers/tree/master/docker/streaming/gstreamer):

For ARM hardware: `px4io/gstreamer:raspbian-jessie`

This should run on any `armhf` computer with compatible kernel.

For x64 hardware: `px4io/gstreamer:ubuntu-trusty`

## Tested hardware ##

Computers:

- Odroid U3 (Ubuntu)
- Raspberry PI 2 (Ubuntu, Hypriot)

Cameras:

- C920
- Raspberry PI camera

## Usage ##

TODO: usage description, or link to PX4 wiki

Stream to target host:

`sudo docker run --privileged --rm px4io/gstreamer:raspbian-jessie 192.168.1.42 5544`

(Change image according to platform)

To specify stream settings use the following form:

`sudo docker run --privileged --rm px4io/gstreamer:raspbian-jessie 192.168.1.42 5544 1280 720 24 1000000`

## Building ##

The containers were built with the following commands:

```
docker build -t px4io/gstreamer:raspbian-jessie -f DockerfileRaspbian .
docker build -t px4io/gstreamer:ubuntu-trusty -f DockerfileUbuntu .

# Not used ATM. Works too but needs prebuilt GStreamer binaries, where as the other ones have managed repos.
#docker build -t px4io/gstreamer:armhf-ubuntu-trusty -f DockerfileArmhfUbuntu .
```

Notes:

- built on x64 (with QEMU for ARM containers)
- see the scripts directory for installation procedures
