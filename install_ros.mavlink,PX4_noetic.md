

### ubuntu 20.04 - install_ros.noetic 

- https://java-mugeo.tistory.com/16

```
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
lsb_release -a
cat /etc/apt/sources/list.d/ros-latest.list
sudo apt install curl    
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
sudo apt update
sudo apt install ros-noetic-desktop-full
echo $SHELL
echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
source ~/.bashrc
sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential
sudo rosdep init
rosdep update

```



### ubuntu 20.04 - install_mavlink 

- https://docs.px4.io/main/en/ros/mavros_installation.html

```
sudo apt-get install ros-noetic-mavros ros-noetic-mavros-extras
wget https://raw.githubusercontent.com/mavlink/mavros/master/mavros/scripts/install_geographiclib_datasets.sh
sudo bash ./install_geographiclib_datasets.sh 
mkdir -p ~/catkin_ws/src
cd ~/catkin_ws
catkin init                              # 해결방법1  참조할 것것
```

- error1 : catkin: command not found
```
h1@h1:~/catkin_ws$ catkin init
catkin: command not found
sudo apt-get install ros-noetic-catkin python-noetic-tools 
Reading package lists... Done
Building dependency tree
Reading state information... Done
E: Unable to locate package python-noetic-tools


h1@h1:~/catkin_ws$ sudo apt install catkin
Reading package lists... Done
Building dependency tree
Reading state information... Done
Some packages could not be installed. This may mean that you have
requested an impossible situation or if you are using the unstable
distribution that some required packages have not yet been created
or been moved out of Incoming.
The following information may help to resolve the situation:

The following packages have unmet dependencies:
 catkin : Depends: python3-catkin-pkg (>= 0.4.14-2) but it is not going to be installed
E: Unable to correct problems, you have held broken packages.


``

- 해결방법1 https://pinkwink.kr/1337
```
sudo apt-get upgrade
sudo apt install python3-osrf-pycommo
sudo apt insall python3-catkin-tools    #  python-noetic-tools은 아님.
catkin init
catkin build                            # 소스가 없어서 테스트로 사용

```



