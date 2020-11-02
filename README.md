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
 
 ```import  time,subprocess

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
    
    
