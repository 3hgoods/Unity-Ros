

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
catkin init
```

- error1 : catkin: command not found
```
h1@h1:~/catkin_ws$ catkin init
catkin: command not found

``



