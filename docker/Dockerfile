# How to execute: 
# $ docker build -t fiware-aiakos .
# $ docker run -p 3000:3000 -d fiware-aiakos

FROM centos:7
ADD fiware.repo /etc/yum.repos.d/fiware.repo
RUN curl --silent --location https://rpm.nodesource.com/setup_4.x | bash -
RUN yum -y install git nodejs rpm-build initscripts crontabs fiware-aiakos
WORKDIR /opt/fiware/fiware-aiakos
RUN npm install
COPY aiakos.yml /etc/sysconfig/fiware-aiakos.yml
EXPOSE 3001
VOLUME /sys/fs/cgroup /run /tmp
ENV container=docke
COPY start.sh start.sh
CMD ./start.sh

