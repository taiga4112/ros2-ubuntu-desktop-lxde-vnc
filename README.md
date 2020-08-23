# ros2-ubuntu-desktop-lxde-vnc
A Docker image to provide HTML5 VNC interface to access Ubuntu LXDE + ROS2, based on [dorowu/ubuntu-desktop-lxde-vnc](https://github.com/fcwu/docker-ubuntu-vnc-desktop)

## Quick Start
1. Run the docker container and access with port `6080`.
    - Change the `shm-size` value depending on the situation.

```sh
docker run -p 6080:80 --shm-size=512m taiga4112/ros2-ubuntu-desktop-lxde-vnc:latest
```

2. Browse [http://127.0.0.1:6080](http://127.0.0.1:6080).

![Image from Gyazo](https://i.gyazo.com/ab43ab3f6dc10b5186416499e49d0bbe.jpg)

## Install Information
Please see Dockerfile for detail.

- Set OS by using [dorowu/ubuntu-desktop-lxde-vnc](https://github.com/fcwu/docker-ubuntu-vnc-desktop).
- Installing ROS2 via Debian packages as [this url](https://index.ros.org/doc/ros2/Installation/Foxy/Linux-Install-Debians/#id10).
  - ROS2 version : [Foxy Fitzroy](https://index.ros.org/doc/ros2/Releases/Release-Foxy-Fitzroy/)

At first, [adding sourcing to your VNC shell startup script](https://index.ros.org/doc/ros2/Tutorials/Configuring-ROS2-Environment/#add-sourcing-to-your-shell-startup-script) is strongly recommended like this.

```sh
echo "source /opt/ros/foxy/setup.bash" >> ~/.bashrc
```

## How to build

```sh
git clone git@github.com:taiga4112/ros2-ubuntu-desktop-lxde-vnc.git
cd ros2-ubuntu-desktop-lxde-vnc
docker build -t taiga4112/ros2-ubuntu-desktop-lxde-vnc .
```