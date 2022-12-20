

### 도커 사용 ROS
- https://jderobot.github.io/RoboticsAcademy/exercises/Drones/drone_cat_mouse


### 도커(docker) 이미지의 내용이 궁금할 때
- docker pull jderobot/robotics-academy:latest
- docker inspect  jderobot/robotics-academy:latest
- 설치전 이미지도 확인이 될까? --> 안됨
- docker inspect tensorflow/tensorflow:latest-gpu[]
- Error: No such object: tensorflow/tensorflow:latest-gpu

```
h1@h1:~$ docker inspect  jderobot/robotics-academy:latest
[
    {
        "Id": "sha256:cb46d658f615db8250dfa302c1067f20212d77e1c288d6ecae989243fba136c0",
        "RepoTags": [
            "jderobot/robotics-academy:latest"
        ],
        "RepoDigests": [
            "jderobot/robotics-academy@sha256:fcca4f7af8781cbbf0f6a746e2231404de78596de8ffc0f2794c9c2d97da8e09"
        ],
        "Parent": "",
        "Comment": "",
        "Created": "2022-12-11T20:43:21.31889938Z",
        "Container": "0736c979906a1c8c0c1e64bafeacc7236d20c410ac6b178ba902570926f8ebd4",
        "ContainerConfig": {
            "Hostname": "0736c979906a",
            "Domainname": "",
            "User": "",
            "AttachStdin": false,
            "AttachStdout": false,
            "AttachStderr": false,
            "ExposedPorts": {
                "1108/tcp": {},
                "1831/tcp": {},
                "1904/tcp": {},
                "1905/tcp": {},
                "2303/tcp": {},
                "2304/tcp": {},
                "6080/tcp": {},
                "8000/tcp": {},
                "8765/tcp": {}
            },
            "Tty": false,
            "OpenStdin": false,
            "StdinOnce": false,
            "Env": [
                "PATH=/opt/gradle/gradle-6.3-rc-4/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/opt/VirtualGL/bin:/opt/TurboVNC/bin",
                "NVIDIA_VISIBLE_DEVICES=all",
                "NVIDIA_DRIVER_CAPABILITIES=all",
                "LD_LIBRARY_PATH=/usr/lib/x86_64-linux-gnu:/usr/lib/i386-linux-gnu:/usr/local/nvidia/lib:/usr/local/nvidia/lib64",
                "LANG=en_US.UTF-8",
                "LANGUAGE=en_US:en",
                "LC_ALL=en_US.UTF-8",
                "ROS_DISTRO=noetic"
            ],
            "Cmd": [
                "/bin/sh",
                "-c",
                "#(nop) ",
                "ENTRYPOINT [\"./entrypoint.sh\"]"
            ],
            "Image": "sha256:9a59666cdb35bb28ff6cae2d45acfdf93829f309cb321f50726b1b48701c7bd8",
            "Volumes": null,
            "WorkingDir": "",
            "Entrypoint": [
                "./entrypoint.sh"
            ],
            "OnBuild": null,
            "Labels": {
                "maintainer": "NVIDIA CORPORATION <cudatools@nvidia.com>"
            }
        },
        "DockerVersion": "20.10.6",
        "Author": "",
        "Config": {
            "Hostname": "",
            "Domainname": "",
            "User": "",
            "AttachStdin": false,
            "AttachStdout": false,
            "AttachStderr": false,
            "ExposedPorts": {
                "1108/tcp": {},
                "1831/tcp": {},
                "1904/tcp": {},
                "1905/tcp": {},
                "2303/tcp": {},
                "2304/tcp": {},
                "6080/tcp": {},
                "8000/tcp": {},
                "8765/tcp": {}
            },
            "Tty": false,
            "OpenStdin": false,
            "StdinOnce": false,
            "Env": [
                "PATH=/opt/gradle/gradle-6.3-rc-4/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/opt/VirtualGL/bin:/opt/TurboVNC/bin",
                "NVIDIA_VISIBLE_DEVICES=all",
                "NVIDIA_DRIVER_CAPABILITIES=all",
                "LD_LIBRARY_PATH=/usr/lib/x86_64-linux-gnu:/usr/lib/i386-linux-gnu:/usr/local/nvidia/lib:/usr/local/nvidia/lib64",
                "LANG=en_US.UTF-8",
                "LANGUAGE=en_US:en",
                "LC_ALL=en_US.UTF-8",
                "ROS_DISTRO=noetic"
            ],
            "Cmd": null,
            "Image": "sha256:9a59666cdb35bb28ff6cae2d45acfdf93829f309cb321f50726b1b48701c7bd8",
            "Volumes": null,
            "WorkingDir": "",
            "Entrypoint": [
                "./entrypoint.sh"
            ],
            "OnBuild": null,
            "Labels": {
                "maintainer": "NVIDIA CORPORATION <cudatools@nvidia.com>"
            }
        },
        "Architecture": "amd64",
        "Os": "linux",
        "Size": 11849855029,
        "VirtualSize": 11849855029,
        "GraphDriver": {
            "Data": {
                "LowerDir": "/var/lib/docker/overlay2/856755f41a81c3b1a6329ca567b67b1de0f453982e02d5701fe75a540c4d6b27/diff:/var/lib/docker/overlay2/7e6946377a86ac494660a91fd2cfdc311d38fdb47290cb8b891278ee2107a188/diff:/var/lib/docker/overlay2/ce1ca3bfc3c5b6de59ed87b12b3e720533414422eaa43b7e679a52ae3f788e66/diff:/var/lib/docker/overlay2/f976c8bf78842ba7bfa9797ba0b681a7ab631fa9bd609be1ab250d890072659d/diff:/var/lib/docker/overlay2/17986b9497d350bb0a1e30065c6256c31e26a916cdbe8c5e883105ba337356c7/diff:/var/lib/docker/overlay2/dd98529b9f2dead43801dedc2b386433b01a7c8e3340152c0f65a877baa75382/diff:/var/lib/docker/overlay2/87be447cf543db8e0511b6778bfe3b6769e92d3a1e36c99f19b3501c8144bd09/diff:/var/lib/docker/overlay2/18246a266ef5065229ae49867c2da72d441469698cb474f0a86d150c311221e9/diff:/var/lib/docker/overlay2/01ee7221572448ae61b7a1afa6e9de11a113548b459d3bb1f7782ffe9f78a7ef/diff:/var/lib/docker/overlay2/d258f462e85ee5a63bd2a9194d76df1dd6cac6e20171efbf3f136a2b9a9d324d/diff:/var/lib/docker/overlay2/53a11369ea58aacd51f69e260451138471165562f8c40f4ac003a90a829fc716/diff:/var/lib/docker/overlay2/71a3eba0bda8d48e768fbbec7719ab39e2bd06a3ce9ce2631e15b15db7e86f62/diff:/var/lib/docker/overlay2/fdb090a69ae52d71dc1d1cc67339f40fdee1e5dfa1195f314bc682e274d0b5ca/diff:/var/lib/docker/overlay2/3225f8b8605ad55e862e829a4b64b1367ec4f67c2a77ee8426a46aa0746eec01/diff:/var/lib/docker/overlay2/8fcb816f7c809b5decf1565b926a3b042d19ea208e29a0f7c6295577bc70ff9e/diff:/var/lib/docker/overlay2/947f26d75f8758847975b5d01c45e20f8089c0eb48a31bdd1e815bb61625b34e/diff:/var/lib/docker/overlay2/6863bbec5dd9518609fd733a96a396cd859578bd673b2940464baf2ab8953d1f/diff:/var/lib/docker/overlay2/b7a7189eea369b92bad0376b39273b6378f3bc40866cf09c947f1af592913201/diff:/var/lib/docker/overlay2/377c27297ca0358a81bc43df92467326a02884c701bff1171cf3475b02242b1f/diff:/var/lib/docker/overlay2/3df87b417d8c116a62339167cb51e2dcd8dd3ab7296fe821aa790054f79ef483/diff:/var/lib/docker/overlay2/799167eb0a1a0657e44c39283548dc451a641d33b6dd989185ebd5a9cf0ba717/diff:/var/lib/docker/overlay2/427fdda5ce149d328ebb86a5eee67cac0c792666b1ba63870d0d24390c2fdff6/diff:/var/lib/docker/overlay2/ffc48f0e7991256d246a31a3dc1f3e6b1ef08ea2f2ea97b97e285e9fe2378748/diff:/var/lib/docker/overlay2/1a37aacd64a8496c30d011728ec53398d36b2eff52e609b9312ae2aff52556af/diff:/var/lib/docker/overlay2/2054a307f4562e2560aeb01d048c57f8dc72174b5766a172e6c36bd8e55e0dea/diff:/var/lib/docker/overlay2/e0c51eaade6f053679ae966a879d22510fe1884d69bb5a7e0a011a89e1806387/diff:/var/lib/docker/overlay2/558026d3e9c5055ac3aa7878cd2b6643236756162ee1911e7f1a7fa1c4c191d7/diff:/var/lib/docker/overlay2/35b5634ab92453d63f1043ae5ce72d7e779b4743c513e6b61794831777ae11ec/diff:/var/lib/docker/overlay2/bfbaf3b1378a41276fb429af2ece8075bb44cda732194f0471c1073754724e3a/diff:/var/lib/docker/overlay2/86627a8a992c90b76207d2ed886943661b21f90981a0b92d62d3cb7c314c1d09/diff:/var/lib/docker/overlay2/84b90b8bf79da17d2361f22a425486d298aa65330e21d2da0485aafdc1d11983/diff:/var/lib/docker/overlay2/c85e87bc6538b6561def9bb6a72d052113656852811e48bb73765a248d99f405/diff:/var/lib/docker/overlay2/5879ea060536232d65e3859ba4b8b36d9ea66ab2356b1d5c2e4c45fa809e4eb1/diff:/var/lib/docker/overlay2/e15e4ce4d26edf2dbe06b0c0eb4848657ff4996a9e0b32a522bbbae9534063f2/diff:/var/lib/docker/overlay2/e85782041b6b532ec4561b16d94063c440d3e27f4d1978b3feab345a72c5e4d8/diff:/var/lib/docker/overlay2/f61169187bc9e79d68c9619060474c1719bc8603259105d925b8dc4ba32808c3/diff:/var/lib/docker/overlay2/f29fea055126ef1ee8ab21532c3f97ea7d626ec199cb9c006926d2ed32dc4dea/diff:/var/lib/docker/overlay2/7f9dfcbda29d47692bf932997afceb4935456edefaa652d342b187224196c6e8/diff:/var/lib/docker/overlay2/cbd8baf528d79bc1a591a30f9a6a21410c03faebb725820ea2a7eacdbfeccb0f/diff:/var/lib/docker/overlay2/8d5199ced088fab0a44ca25bb2c1e047d7103b805d19dceb84d25e395ea57a58/diff:/var/lib/docker/overlay2/96a1424bc758949d012ce003bf41291ce4aa5f505d34ef5a29d78f6567495782/diff:/var/lib/docker/overlay2/33c66206625c3b40504f3442e51f69d2c89994f74702837902b8975f042b2f52/diff:/var/lib/docker/overlay2/0267273bbd4674ce9c6d650875d1423743e1180246153e2fca1b6a29a2d8b129/diff:/var/lib/docker/overlay2/eecc949b2199fd005b93b37566290e5a1041cce975aa2259b1684b0ff4f0f843/diff:/var/lib/docker/overlay2/4d650ffad860408881765d3cce07f40fd8ff3a8fcc05bee7a898d4b36146da45/diff:/var/lib/docker/overlay2/1dec5502901a2a4d67ed3e7667f24554b54a1ce98ea93b15d9ad933cbbc16e22/diff:/var/lib/docker/overlay2/a4d6833427bcdb259695e2ffd3db998d6c213ab19281712783d43f228a14b004/diff:/var/lib/docker/overlay2/60bb3d1030fa4e6bc203eee88ac8a548358386e7414854cd8e88b6996190c795/diff:/var/lib/docker/overlay2/ea8e3a1e1de4559edfd3f73d787f6c5b890b21ec122784b1daa9c666d0b01b99/diff",
                "MergedDir": "/var/lib/docker/overlay2/ac31f5a3e2b894e8b0bee227f4bd0e7b238979e355280700deec5911666ff35a/merged",
                "UpperDir": "/var/lib/docker/overlay2/ac31f5a3e2b894e8b0bee227f4bd0e7b238979e355280700deec5911666ff35a/diff",
                "WorkDir": "/var/lib/docker/overlay2/ac31f5a3e2b894e8b0bee227f4bd0e7b238979e355280700deec5911666ff35a/work"
            },
            "Name": "overlay2"
        },
        "RootFS": {
            "Type": "layers",
            "Layers": [
                "sha256:bf8cedc62fb3ef98ad0dff2be56ca451dd3ea69abd0031ad3e0fe5d9f9e4dfff",
                "sha256:c3bc5ba2684888bd1885d6428a5d31f7ab92e62672a0223fc6ab814010d19de0",
                "sha256:20026237d960abb8b4355e4b372bcb40682770d94e8eb6e2625ef02e6f8b1e4e",
                "sha256:df2e8c86e49511e837c4b7be7ef3d9cf957aa3efbb326649c9755478aa9686dd",
                "sha256:047aa3d1de0651fa0aea595c2fdb1305946df36b8ef17db047c9f5b22717edba",
                "sha256:1962167633edd18a21b2762b2cf2ade56b8931f7dd0ad4ba436481144d86e027",
                "sha256:d6cecaaf468f10efe1250e0abd5f038b73a3f2a93909a2ea8e3f66396f2d33bc",
                "sha256:3d0a5c2525e3837625a06262c0bfbac0b51f4fe5b44f0b51dba18e0d2ec6479e",
                "sha256:b04c9cea8957731e2a367382bd207c4416ff2c42d07cc62f017e77e42c3c54b5",
                "sha256:1190fe28f8e1fe6b94115ba4721da688e4b05cfb8f25e9fa1ed993612d55331e",
                "sha256:0f0be6abf8df4ec4f457b175d25d88275f22c685838f6629c395f0ea4eabd647",
                "sha256:fe1d31b621fe3d2fa3b94c389ed37b3bf1e43e9016ed09654452e3c80c61cdbe",
                "sha256:92fe39e13b14003a5a8ebec29a8e5c0e93041274f2d12fb21aacfdf1c79b6016",
                "sha256:0a0f2e43a31b4d20d6630ec739c381d36b59042c55a6488d4ce742f06e6fdc4a",
                "sha256:1e21beaaf2dbb4963df67ddeaaaf23d42d20187a99c4612db06b92268c33f998",
                "sha256:2e71b20bf5a43f06a0710beda5e41cc213f7f6ccb2c6faed3214aa47dddd74ec",
                "sha256:bea0f5eb4ca9b15e5da68af5c6f032e625cdebd53134b184398ab793400804bf",
                "sha256:f810d170eb6be8499807636048ca8f7ea6feb991e317c10c4e0bf7649d5e8ce6",
                "sha256:869f3d394dcbb7554ecbf6ce4d8d42f41e0cb2e370473b2abf0a48f121689abf",
                "sha256:c8766bc6766cccd3d9074a27833ca283584c8402ba35c5caa7c47f063af1290f",
                "sha256:4c7cc57587bcd0b1e323c15cca4dc3f2fd91f6cd2c565dd8894559c08cdf98c8",
                "sha256:91c74921e77781a05cb285080cb44a9e55e98fedc3e7b6fa8aeae044267a22a4",
                "sha256:2b2128000f73e66d4e45b359bf75ef31511ac8d52168f0471fc1877410146bb3",
                "sha256:21994e931d04884c1641c3fc74703bfdb6ce24deb89788ac538665dbd31a70e4",
                "sha256:c844673385443b9a34acb878d9796454a9dff67ccafeef77ecb5c54d9bd8ef91",
                "sha256:e94f50507272835bbb595dfdfc4894d134be5fb82cfa49491edaa629efd6669d",
                "sha256:11588c1d7d7cca39fab1db15d8a2fb2c27d8ccaeeb656fe9ded6e16948f325b0",
                "sha256:0a0282b6e2e34ac6bcca5a9ac0d5565c1f1ec6277d5330973181aa76426a53af",
                "sha256:b7dce2364ebfa6b330729a9d5e72a38fefd6767612374a70f0030bb2552458cb",
                "sha256:1f37a4ab7f73b1a0f3bd5b25b69df62b6dba4b48645d77fcb0a085f656934dd1",
                "sha256:894360da925cb8dc0b6e525ac1b6ea0ce32614b987584d20a75376f2b4a059b9",
                "sha256:00417e7fc99e85d1ef54344ff903b593f5bbe8aca726d7e875935709fee7dbc6",
                "sha256:b810448371e158f4023865ee20e795c25d2c366b7309161ad55d3484deb08ad3",
                "sha256:14f563a8d4190524815b098d7285b4ec5155c7b97a59afb682d21b17a752464b",
                "sha256:5eb81072543ab37dfef6fb79dd3d17dbf8a4532e90a78d2e2938b792b3fcd417",
                "sha256:6c56215197a67f89c3633b1f9dc8c656cc376772a61b22bd0e81a5803cff905a",
                "sha256:002b7bdff6f44b0db03ee0c9d294128141268c7f14e24dd955a3250b9333d2f2",
                "sha256:e7348eea91d8b64ba3d8843e781e63dd62ff5286d16e118fd53ed8437561b071",
                "sha256:21a138f87d552200936d894fa8ac445eead29e958b3bd647d2b65667990e038d",
                "sha256:17f5dd27ec28026df050dcbc66db4c0ab65da9c665c937485c9e072191f73751",
                "sha256:1382b6d3b3bcae73a57555de49fcd75eefc0e593267a4c9437cf522807a0477a",
                "sha256:173df3510653de0f37427cfca77d0efa37feb0edbb74eec5a0dd279c6df3c7c5",
                "sha256:f2d5605f8a0f139a0f4cc0a9313b68a4bd4333468274d12d9cc623123d661775",
                "sha256:d9fe990f5d9fcd02849306e41aa333d1e060a2a5321a1f47eb13146867cbc5ee",
                "sha256:6fa3748475440307b5f631ef133dc71ce61e25daeb1f5dba2d36576e3d1041c8",
                "sha256:e1406088c01c2cf3ac53331ede31e646e0250910fba3d284e5bfc65d267c3ee0",
                "sha256:05c9358ecc1b43ec14c31abcc9eb4687bc9eaa434cdad98debc27ecae9ffc388",
                "sha256:1c94a0fce03f0d1bbfc529d774be917fe58ca49c35c33a3ef0704e9fffa5d22b",
                "sha256:8fa5c87daa71c4806728717e79e589a9e70c9cb612727c6d94e9cba4fb471df8",
                "sha256:9ba591942d61bb936b5f9e18fa99a5af84fb34bfaad3e4ad41d12c1931ef4b5d"
            ]
        },
        "Metadata": {
            "LastTagTime": "0001-01-01T00:00:00Z"
        }
    }
]




```
