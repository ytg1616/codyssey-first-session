# codyssey-first-session




기초  터미널 명령어 실습 
ytg16168982@c5r6s1 ~ % pwd
/Users/ytg16168982
ytg16168982@c5r6s1 ~ % mkdir mission-dir
ytg16168982@c5r6s1 ~ % cd mission-dir
ytg16168982@c5r6s1 mission-dir % touch test.txt
ytg16168982@c5r6s1 mission-dir % ls -al      
total 0
drwxr-xr-x   3 ytg16168982  ytg16168982   96 Jul 30 18:28 .
drwxr-x---+ 21 ytg16168982  ytg16168982  672 Jul 30 18:27 ..
-rw-r--r--   1 ytg16168982  ytg16168982    0 Jul 30 18:28 test.txt
ytg16168982@c5r6s1 mission-dir % echo "Hellow World" > test.txt
ytg16168982@c5r6s1 mission-dir % cat test.txt
Hellow World
ytg16168982@c5r6s1 mission-dir % mv test.txt hello.txt
ytg16168982@c5r6s1 mission-dir % cp hello.txt copy.txt
ytg16168982@c5r6s1 mission-dir % 




permission 실습
ytg16168982@c5r6s1 mission-dir % ls -al hello.txt   
-rw-r--r--  1 ytg16168982  ytg16168982  13 Jul 30 18:29 hello.txt
ytg16168982@c5r6s1 mission-dir % cmchod 755 hello.txt
zsh: command not found: cmchod
ytg16168982@c5r6s1 mission-dir % chmod 755 hello.txt
ytg16168982@c5r6s1 mission-dir % ls - al hello.txt
ls: -: No such file or directory
ls: al: No such file or directory
hello.txt
ytg16168982@c5r6s1 mission-dir % chmod 755 hello.txt
ytg16168982@c5r6s1 mission-dir % ls -al hello.txt
-rwxr-xr-x  1 ytg16168982  ytg16168982  13 Jul 30 18:29 hello.txt




docker 실습
ytg16168982@c5r6s1 ~ % docker --version
Docker version 28.5.2, build ecc6942
ytg16168982@c5r6s1 ~ % docker info
Client:
 Version:    28.5.2
 Context:    orbstack
 Debug Mode: false
 Plugins:
  buildx: Docker Buildx (Docker Inc.)
    Version:  v0.29.1
    Path:     /Users/ytg16168982/.docker/cli-plugins/docker-buildx
  compose: Docker Compose (Docker Inc.)
    Version:  v2.40.3
    Path:     /Users/ytg16168982/.docker/cli-plugins/docker-compose

Server:
 Containers: 0
  Running: 0
  Paused: 0
  Stopped: 0
 Images: 0
 Server Version: 28.5.2
 Storage Driver: overlay2
  Backing Filesystem: btrfs
  Supports d_type: true
  Using metacopy: false
  Native Overlay Diff: true
  userxattr: false
 Logging Driver: json-file
 Cgroup Driver: cgroupfs
 Cgroup Version: 2
 Plugins:
  Volume: local
  Network: bridge host ipvlan macvlan null overlay
  Log: awslogs fluentd gcplogs gelf journald json-file local splunk syslog
 CDI spec directories:
  /etc/cdi
  /var/run/cdi
 Swarm: inactive
 Runtimes: io.containerd.runc.v2 runc
 Default Runtime: runc
 Init Binary: docker-init
 containerd version: 1c4457e00facac03ce1d75f7b6777a7a851e5c41
 runc version: d842d7719497cc3b774fd71620278ac9e17710e0
 init version: de40ad0
 Security Options:
  seccomp
   Profile: builtin
  cgroupns
 Kernel Version: 6.17.8-orbstack-00308-g8f9c941121b1
 Operating System: OrbStack
 OSType: linux
 Architecture: x86_64
 CPUs: 6
 Total Memory: 7.81GiB
 Name: orbstack
 ID: 048e2934-194c-4048-9c08-ddd19774df76
 Docker Root Dir: /var/lib/docker
 Debug Mode: false
 Experimental: false
 Insecure Registries:
  ::1/128
  127.0.0.0/8
 Live Restore Enabled: false
 Product License: Community Engine
 Default Address Pools:
   Base: 192.168.97.0/24, Size: 24
   Base: 192.168.107.0/24, Size: 24
   Base: 192.168.117.0/24, Size: 24
   Base: 192.168.147.0/24, Size: 24
   Base: 192.168.148.0/24, Size: 24
   Base: 192.168.155.0/24, Size: 24
   Base: 192.168.156.0/24, Size: 24
   Base: 192.168.158.0/24, Size: 24
   Base: 192.168.163.0/24, Size: 24
   Base: 192.168.164.0/24, Size: 24
   Base: 192.168.165.0/24, Size: 24
   Base: 192.168.166.0/24, Size: 24
   Base: 192.168.167.0/24, Size: 24
   Base: 192.168.171.0/24, Size: 24
   Base: 192.168.172.0/24, Size: 24
   Base: 192.168.181.0/24, Size: 24
   Base: 192.168.183.0/24, Size: 24
   Base: 192.168.186.0/24, Size: 24
   Base: 192.168.207.0/24, Size: 24
   Base: 192.168.214.0/24, Size: 24
   Base: 192.168.215.0/24, Size: 24
   Base: 192.168.216.0/24, Size: 24
   Base: 192.168.223.0/24, Size: 24
   Base: 192.168.227.0/24, Size: 24
   Base: 192.168.228.0/24, Size: 24
   Base: 192.168.229.0/24, Size: 24
   Base: 192.168.237.0/24, Size: 24
   Base: 192.168.239.0/24, Size: 24
   Base: 192.168.242.0/24, Size: 24
   Base: 192.168.247.0/24, Size: 24
   Base: fd07:b51a:cc66:d000::/56, Size: 64

WARNING: DOCKER_INSECURE_NO_IPTABLES_RAW is set
ytg16168982@c5r6s1 ~ % docker run hello-world
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
4f55086f7dd0: Pull complete 
Digest: sha256:c3cbe1cc1aa588a64951ac6286e0df7b27fe2e6324b1001c619bb358770c0178
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/





index html 위치에 서버 만들기
<h1>Hellow, My First Docker Web Server</h1> 

ytg16168982@c5r6s1 my-web % echo "<h1>Hellow, My First Docker Web Server</h1>" > index.html 
Docker 파일 만들기
ytg16168982@c5r6s1 my-web % code.
zsh: command not found: code.
ytg16168982@c5r6s1 my-web % code .


해당 Docker 파일에 프로그램 다운로드
FROM nginx:latest
COPY index.html /usr/share/nginx/html/index.html
4단계: 이미지 만들기
docker build -t my-nginx-image .

5단계(내가 만든 이미지 실행하기)
ytg16168982@c5r6s1 my-web % docker run -d -p 8080:80 --name my-web-container my-nginx-image
0ba5c512916045977d02f010040b3ea0d33c0003d600dcf0ba162427938e32d0

마무리(백그라운드 종료 및 삭제)
ytg16168982@c5r6s1 my-web % docker run -d -p 8080:80 --name my-web-container my-nginx-image
0ba5c512916045977d02f010040b3ea0d33c0003d600dcf0ba162427938e32d0
ytg16168982@c5r6s1 my-web % docker ps
CONTAINER ID   IMAGE            COMMAND                  CREATED          STATUS          PORTS                                     NAMES
0ba5c5129160   my-nginx-image   "/docker-entrypoint.…"   10 minutes ago   Up 10 minutes   0.0.0.0:8080->80/tcp, [::]:8080->80/tcp   my-web-container
ytg16168982@c5r6s1 my-web % docker stop my-web-container
my-web-container
ytg16168982@c5r6s1 my-web % docker rm my-web-container
my-web-container
ytg16168982@c5r6s1 my-web % docker ps -a
CONTAINER ID   IMAGE         COMMAND    CREATED       STATUS                   PORTS     NAMES
eee977a99ed9   ubuntu        "bash"     2 hours ago   Exited (0) 2 hours ago             angry_darwin
0fcaf1025a30   hello-world   "/hello"   2 hours ago   Exited (0) 2 hours ago             quirky_heisenberg
ytg16168982@c5r6s1 my-web % docker images
REPOSITORY       TAG       IMAGE ID       CREATED             SIZE
my-nginx-image   latest    b4d985ec451e   About an hour ago   161MB
ubuntu           latest    de7345b16e94   2 weeks ago         100MB
hello-world      latest    e2ac70e7319a   4 months ago        10.1kB
