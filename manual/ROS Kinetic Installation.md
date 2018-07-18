# ROS Kinetic Installation

## 1.Installation
ROS Kinetic ONLY supports Wily (Ubuntu 15.10), Xenial (Ubuntu 16.04) and Jessie (Debian 8) for debian packages.
### 1.1 Configure your Ubuntu repositories
Configure your Ubuntu repositories to allow "restricted," "universe," and "multiverse." You can follow the Ubuntu guide for instructions on doing this.https://help.ubuntu.com/community/Repositories/Ubuntu

![test](..\img\3.1.jpg)

![test](..\img\3.2.jpg)

![test](..\img\3.3.jpg)

### 1.2 Setup your sources.list
Setup your computer to accept software from packages.ros.org.
```shell
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
```
### 1.3 Set up your keys
```shell
sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net:80 --recv-key 421C365BD9FF1F717815A3895523BAEEB01FA116
```
If you experience issues connecting to the keyserver, you can try substituting hkp://pgp.mit.edu:80 or hkp://keyserver.ubuntu.com:80 in the previous command.
### 1.4 Installation
First, make sure your Debian package index is up-to-date:
```shell
sudo apt-get update
```
Desktop-Full Install: (Recommended) : ROS, rqt, rviz, robot-generic libraries, 2D/3D simulators, navigation and 2D/3D perception.
```shell
sudo apt-get install ros-kinetic-desktop-full
```
To find available packages, use:
```shell
apt-cache search ros-kinetic
```
### 1.5 Initialize rosdep
Before you can use ROS, you will need to initialize rosdep. rosdep enables you to easily install system dependencies for source you want to compile and is required to run some core components in ROS.
```shell
sudo rosdep init
rosdep update
```
### 1.6 Environment setup
It's convenient if the ROS environment variables are automatically added to your bash session every time a new shell is launched:
```shell
echo "source /opt/ros/kinetic/setup.bash" >> ~/.bashrc
source ~/.bashrc
```
### 1.7 Dependencies for building packages
Up to now you have installed what you need to run the core ROS packages. To create and manage your own ROS workspaces, there are various tools and requirements that are distributed separately. For example, rosinstall is a frequently used command-line tool that enables you to easily download many source trees for ROS packages with one command.

To install this tool and other dependencies for building ROS packages, run:
```shell
sudo apt-get install python-rosinstall python-rosinstall-generator python-wstool build-essential
```
## 2.Troubleshooting
