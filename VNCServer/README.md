
# How to run

```
cd ${to_this_directory}
sudo build -f ./Dockerfile -t centosvnc:latest `pwd`
sudo docker run -d -P --privileged --name vnc --hostname vnc centosvnc:latest /sbin/init

```
