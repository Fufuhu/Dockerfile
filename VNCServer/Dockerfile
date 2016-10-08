FROM centos:latest


ENV container docker
RUN yum update -y && yum clean all
RUN yum swap -y fakesystemd systemd && yum clean all
RUN yum groupinstall -y "Server with GUI" && yum clean all
RUN yum install -y tigervnc-server && yum clean all
ADD vncserver@:2.service /etc/systemd/system/
ADD vncserver@:3.service /etc/systemd/system/
ADD vncserver@:4.service /etc/systemd/system/
RUN systemctl enable vncserver@:2.service
RUN systemctl enable vncserver@:3.service
RUN systemctl enable vncserver@:4.service
RUN mkdir -p /root/.vnc
RUN echo password | /usr/bin/vncpasswd -f > /root/.vnc/passwd
RUN chmod 600 /root/.vnc/passwd
RUN echo password | passwd root --stdin
RUN systemctl disable firewalld
EXPOSE 5902 5903 5904
