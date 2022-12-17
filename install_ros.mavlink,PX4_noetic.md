

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



### ubuntu 20.04 - install_mavlink mavros

- https://docs.px4.io/main/en/ros/mavros_installation.html

```
sudo apt-get install ros-noetic-mavros ros-noetic-mavros-extras
wget https://raw.githubusercontent.com/mavlink/mavros/master/mavros/scripts/install_geographiclib_datasets.sh
sudo bash ./install_geographiclib_datasets.sh 
mkdir -p ~/catkin_ws/src
cd ~/catkin_ws
catkin init                              # 해결방법1  참조할 것
wstool init src

rosinstall_generator --rosdistro noetic mavlink | tee /tmp/mavros.rosinstall  #처음에 안 먹었으나 python3패키지 설치후 작동 (참조1)
rosinstall_generator --upstream mavros | tee -a /tmp/mavros.rosinstall
wstool merge -t src /tmp/mavros.rosinstall
wstool update -t src
rosdep install --from-paths src --ignore-src --rosdistro noetic -y --os ubuntu:focal
wstool merge -t src /tmp/mavros.rosinstall
sudo apt install geographiclib-tools -y
echo "Downloading dependent script 'install_geographiclib_datasets.sh'"
install_geo=$(wget https://raw.githubusercontent.com/mavlink/mavros/master/mavros/scripts/install_geographiclib_datasets.sh -O -)
wget_return_code=$?
sudo bash -c "$install_geo"
catkin build

```

- 참조1 https://velog.io/@jdja2004/SITL-%ED%99%98%EA%B2%BD%EA%B5%AC%EC%B6%95




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


```

- 해결방법1 https://pinkwink.kr/1337
```
sudo apt-get upgrade
sudo apt install python3-osrf-pycommo
sudo apt insall python3-catkin-tools    #  python-noetic-tools은 아님.
catkin init
catkin build                            # 소스가 없어서 테스트로 사용

```

- error 2  python-rosinstall-generator   python2 버전이 오래되어 지원이 끊긴거 같음. 
```
h1@h1:~/catkin_ws$ sudo apt-get install python-catkin-tools python-rosinstall-generator -y
Reading package lists... Done
Building dependency tree
Reading state information... Done
Package python-rosinstall-generator is not available, but is referred to by another package.
This may mean that the package is missing, has been obsoleted, or
is only available from another source
However the following packages replace it:
  python3-rosinstall-generator

Package python-catkin-tools is not available, but is referred to by another package.
This may mean that the package is missing, has been obsoleted, or
is only available from another source

E: Package 'python-catkin-tools' has no installation candidate
E: Package 'python-rosinstall-generator' has no installation candidate

```

- 해결방법2 
```
sudo apt install python3-rosinstall-generator

```

### ubuntu 20.04 - install_PX4 Autopilot 설치
- https://velog.io/@jdja2004/SITL-%ED%99%98%EA%B2%BD%EA%B5%AC%EC%B6%95
- dd

```
cd ~/catkin_ws/src
git clone https://github.com/PX4/PX4-Autopilot.git --recursive
bash ./PX4-Autopilot/Tools/setup/ubuntu.sh   #  이 부분 대체할 것. 아래 부분 업그레이드 진행하고 실행

```
- 설치과정중 경고 , 에러
```
ERROR: pandas 1.5.2 has requirement numpy>=1.20.3; python_version < "3.10", but you'll have numpy 1.17.4 which is incompatible.
```
- 교재 이용(ROS 로보틱스프로그래밍, 
```
sudo apt install python3-pip

pip3 install --user numpy
Requirement already satisfied: numpy in /usr/lib/python3/dist-packages (1.17.4)

pip3 install --upgrade numpy
Collecting numpy
  Downloading numpy-1.23.5-cp38-cp38-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (17.1 MB)
     |████████████████████████████████| 17.1 MB 6.9 MB/s
Installing collected packages: numpy
  WARNING: The scripts f2py, f2py3 and f2py3.8 are installed in '/home/h1/.local/bin' which is not on PATH.
  Consider adding this directory to PATH or, if you prefer to suppress this warning, use --no-warn-script-location.
Successfully installed numpy-1.23.5

pip3 install --user empy
pip3 install --user toml
pip3 install --user packaging
sudo apt install libgstreamer-plugins-base1.0-dev

pip3 install --user jinja2

```

- 대체 애매, Relogin or reboot computer before attempting to build NuttX targets
```
 리부팅 대신 터미널 닫고 새로 열기로 대체 
```


### 설치 정리
- https://swiftcam.tistory.com/407

```
1) mavros 설치 sudo apt install ros-noetic-mavros
2) georaphiclib 데이터 설치 
wget https://raw.githubusercontent.com/mavlink/mavros/master/mavros/scripts/install_geographiclib_datasets.sh
sudo bash ./install_geographiclib_datasets.sh 
3) 필수 유틸리티 설치
sudo apt instal python3-pip
pip3 install --user numpy
pip3 install --user empy
pip3 install --user toml
pip3 install --user jinja2
pip3 install --user packaging

4) catkin_tools 설치
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
sudo apt insall python3-catkin-tools 
sudo apt install python3-osrf-pycommo

5) catkin 초기화
catkin init
wstool init src

6) PX4 펌웨어 다운로드 및 컴파일
git clone https://github.com/PX4/PX4-Autopilot.git --recursive

7) catkim_make로 PX4 펌웨어 및 예제 프로그램 컴파일
cd ~/catkin_ws/
catkin build    (or catkin_make 둘중 하나 선택하면 혼용해서 사용X)

8) SITL 환경설정
source ~/catkin_ws/src/PX4-Autopilot/Tools/setup_gazebo.bash
source ~/catkin_ws/src/PX-Autopilot/build/pix4_sitl_default
export ROSPACKAGE_PATH=$ROS_PACKAGE_PATH:~/catkin_ws/src/PX-Autopilot/
export ROSPACKAGE_PATH=$ROS_PACKAGE_PATH:~/catkin_ws/src/PX-Autopilot/Tools/sitl_gazebo



9) SITL 예제 컴파일/실행
cd ~/catkin_ws/src/PX-Autopilot
make px4_sitl list_vmd_make_targets | grep gazebo

make px4_sitl list_vmd_make_targets | grep gazebo


확인중..
https://swiftcam.tistory.com/604
https://swiftcam.tistory.com/605



```
















