FROM centos:latest
MAINTAINER DemandCube

RUN yum update -y
RUN yum install -y sudo wget curl rpm openssh-clients
RUN yum groupinstall -y 'Development Tools'

#RUN DIR=/home/hadoopdevelopersetup;if [ -d "$DIR" ]; then printf '%s\n' "Removing DIR ($DIR)"; rm -rf "$DIR";fi
RUN mkdir /home/hadoopdevelopersetup
RUN git clone https://github.com/jeroldleslie/hadoop-single-node-cluster.git /home/hadoopdevelopersetup
RUN chmod +x /home/hadoopdevelopersetup/test/unittest.sh

ENTRYPOINT /home/hadoopdevelopersetup/test/unittest.sh

