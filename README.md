# Devsecops 

## Container Security 

<img src="csec.png">

## COnfigure Docker Host variable Globally 

```
root@ip-172-31-78-109 ~]# cat  /etc/profile
# /etc/profile

# System wide envir

# in the last line 

export DOCKER_HOST="tcp://34.204.241.101:2375"

```

## Jenkins more info 

<img src="j.png">

## CI | CD 

<img src="cicd.png">

## shell script for container check and launch 

```
( docker kill arthurC && docker rm arthurC ) || sleep 1
docker run --name arthurC -d -p 4444:5000 arthurflask:v1

```
