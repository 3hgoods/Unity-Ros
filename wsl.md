

### install - old
- https://engpro.tistory.com/49

### install with wsl command

```
C:\gcamp_ros2_ws>wsl -l
Linux용 Windows 하위 시스템 배포:
docker-desktop-data(기본값)
docker-desktop



C:\gcamp_ros2_ws>wsl --install -d ubuntu
다운로드 중: Ubuntu
설치 중: Ubuntu
Ubuntu이(가) 설치되었습니다.
Ubuntu 실행 중...

C:\gcamp_ros2_ws>wsl --install -d ubuntu-20.04
다운로드 중: Ubuntu 20.04 LTS
설치 중: Ubuntu 20.04 LTS
Ubuntu 20.04 LTS이(가) 설치되었습니다.
Ubuntu 20.04 LTS 실행 중...

C:\gcamp_ros2_ws>wsl --install -d ubuntu-22.04.1
잘못된 배포 이름: 'ubuntu-22.04.1'.
올바른 배포 목록을 보려면 'wsl --list --online'을 사용하세요.

C:\gcamp_ros2_ws>wsl --list --online
다음은 설치할 수 있는 유효한 배포 목록입니다.
'wsl --install -d <배포>'를 사용하여 설치하세요.

NAME            FRIENDLY NAME
Ubuntu          Ubuntu
Debian          Debian GNU/Linux
kali-linux      Kali Linux Rolling
openSUSE-42     openSUSE Leap 42
SLES-12         SUSE Linux Enterprise Server v12
Ubuntu-16.04    Ubuntu 16.04 LTS
Ubuntu-18.04    Ubuntu 18.04 LTS
Ubuntu-20.04    Ubuntu 20.04 LTS


```





