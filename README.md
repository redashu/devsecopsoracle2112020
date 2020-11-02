# DevsecOPs

##  resource discussion 

<img src="res.png">

## physical to containers 

<img src="p2c.png">

## Os components

<img src="osc.png">

## Docker Desktop 

[for mac os] ('https://hub.docker.com/editions/community/docker-ce-desktop-mac')

##  for windows 10

[windows 10] ('https://hub.docker.com/editions/community/docker-ce-desktop-windows/')


## Install docker in Amazon Linux vm 

```
root@ip-172-31-73-230 ~]# yum install  docker  -y
Failed to set locale, defaulting to C
Loaded plugins: extras_suggestions, langpacks, priorities, update-motd
amzn2-core                                                              | 3.7 kB  00:00:00     
Resolving Dependencies
--> Running transaction check
---> Package docker.x86_64 0:19.03.6ce-4.amzn2 will be installed
--> Processing Dependency: runc >= 1.0.0 for packa

```

## starting docker engine on any linux platform 

```
root@ip-172-31-73-230 ~]# systemctl status  docker 
● docker.service - Docker Application Container Engine
   Loaded: loaded (/usr/lib/systemd/system/docker.service; disabled; vendor preset: disabled)
   Active: active (running) since Mon 2020-11-02 05:38:20 UTC; 33s ago
     Docs: https://docs.docker.com
  Process: 4328 ExecStartPre=/usr/libexec/docker/docker-setup-runtimes.sh (code=exited, status=0/SUCCESS)
  Process: 4315 ExecStartPre=/bin/mkdir -p /run/docker (code=exited, status=0/SUCCESS)
 Main PID: 4331 (dockerd)
    Tasks: 10
   Memory: 36.4M
   CGroup: /system.slice/doc
  
 ```
 
 ## adding a non root user into Docker group
 
 ```
 usermod -aG docker username
 ```
 
## COnnecting to Docker engine 

<img src="deconn.png">

## creating container using docker images

<di.png>

## Docker basic operations 

```
 6  docker  version 
    7  docker  search  mongodb 
    8  docker  images  
    9  docker  pull  java
   10  docker  images  
   11  docker  pull  python 
   12  docker  pull  mysql 
   
 ```
 
 ## PYthon Code 
 
 ```
 import  time,subprocess

while 2 > 1 :
    print("Hello Oracle !!")
    time.sleep(1)
    kernel_check=subprocess.getoutput('uname -r')
    print("check kernel version ....")
    time.sleep(2)
    print("found linux kernel version is ",kernel_check)
    print("_______")
    print("_______")
    print("_______")
```
    
    
## Pyhon code

```
FROM  python
#  i am connecting to DE  and  asking python base docker  image 
MAINTAINER   ashutoshh@linux.com 
# optional field ; DevInfo 
RUN  mkdir /mycode 
#  use of RUN to execute any shell command in python based  contianer 
COPY  hello.py  /mycode/hello.py 
# it will take hello.py from Host  OS  and copy it docker image 
#  copy can only take data from the place where dockerfile is present 
WORKDIR  /mycode
# similar to cd command in linux/windows 
RUN  chmod +x  hello.py
# how to run code automatically when you create contaienr from the Docker image
CMD  ["python","hello.py"]

```


## Building Docker image with Python code & Dockerfile

```
[ec2-user@ip-172-31-73-230 pycode]$ docker  build  -t  ashuoraclepy:v1 .
Sending build context to Docker daemon  3.584kB
Step 1/7 : FROM  python
 ---> 5336a27a9b1f
Step 2/7 : MAINTAINER   ashutoshh@linux.com
 ---> Running in 9800e7b26950
Removing intermediate container 9800e7b26950
 ---> ad033f70c1ac
Step 3/7 : RUN  mkdir /mycode
 ---> Running in 6d7ffe4639b4
Removing intermediate container 6d7ffe4639b4
 ---> 35792ad8d0d4
Step 4/7 : COPY  hello.py  /mycode/hello.

```

## creating contaienr from Docker image

```
[ec2-user@ip-172-31-73-230 ~]$ docker  images
REPOSITORY           TAG                 IMAGE ID            CREATED             SIZE
satishorcle          v1                  43b609895d46        4 minutes ago       886MB
manish               v1                  3de440ad37a6        12 minutes ago      886MB
arthurpy             v1                  82a89c6754db        12 minutes ago      886MB
rashmioracle         v1                  72b649315cae        12 minutes ago      886MB
anandpy              v1                  31a365bb7c9c        15 minutes ago      886MB
ashuoraclepy         v1                  44b3ffc4fa0f        15 minutes ago      886MB
mysql                latest              db2b37ec6181        10 days ago         545MB
python               latest              5336a27a9b1f        12 days ago         886MB
securecodebox/nmap   latest              0d7ffd5f5c30        4 weeks ago         31.6MB
java                 latest              d23bdf5b1b1b        3 years ago         643MB
[ec2-user@ip-172-31-73-230 ~]$ docker  run  --name  ashuc1 -it  -d  ashuoraclepy:v1 
d0f69ec7a4b7200eac154bb55259f706abfa62cf97408d4eb3f32e271964eeb4
[ec2-user@ip-172-31-73-230 ~]$ docker  ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
d0f69ec7a4b7        ashuoraclepy:v1     "python hello.py"   8 seconds ago       Up 7 seconds                            ashuc1
[ec2-user@ip-172-31-73-230 ~]$ 



```

## checking output of programe running in container 

```
 55  docker  logs  ashuc1 
   56  history 
   57  docker  logs -f   ashuc1 
 ```

## running a child process in a alread running container 

```
  20  docker  exec  -it  ashuc1   bash
   21  docker  exec  -it -d ashuc1   ping  8.8.8.8
   
```
## checking resources by Containers 

```
 27  docker  stats  ashuc1 
   28  docker  stats  
   
```
## More operations on containers

```
docker  kill  ashuc1
docker  start  ashuc1
docker  rm   ashuc1
```
