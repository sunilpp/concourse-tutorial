FROM ubuntu

ADD hello-world /bin/hello-world
#Install WGET
#RUN yum install -y wget
#Install tar
#RUN yum install -y tar
RUN apt-get update
RUN apt-get -f install
RUN apt-get install -y wget

RUN mkdir /space
# Download and install Tomcat
#RUN cd /space;wget http://svn.dorado.com/dorado/ThirdPartySolutions/tomcat/apache-tomcat-7.0.61.tar.gzhttp://svn.dorado.com/dorado/ThirdPartySolutions/tomcat/apache-tomcat-7.0.61.tar.gz
RUN cd /space;wget http://mirrors.koehn.com/apache/tomcat/tomcat-8/v8.0.33/bin/apache-tomcat-8.0.33.tar.gz
RUN cd /space;gunzip apache-tomcat-8.0.33.tar.gz
RUN cd /space;tar xvf apache-tomcat-8.0.33.tar
RUN chmod -R 755 /space/apache-tomcat-8.0.33.tar
RUN rm -f /space/apache-tomcat-8.0.33.tar.gz

RUN DEBIAN_FRONTEND=noninteractive apt-get install -y -q vim bzr git gdb openssh-server

RUN echo 'root:root' | chpasswd
RUN mkdir -p /var/run/sshd

RUN sed -ri 's/UsePAM yes/#UsePAM yes/g' /etc/ssh/sshd_config
RUN sed -ri 's/#UsePAM no/UsePAM no/g' /etc/ssh/sshd_config
RUN sed -ri 's/PermitRootLogin without-password/PermitRootLogin yes/g' /etc/ssh/sshd_config

EXPOSE 22

CMD /usr/sbin/sshd -D

ENTRYPOINT ["/bin/hello-world"]
CMD ["world"]
