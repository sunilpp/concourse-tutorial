FROM busybox

ADD hello-world /bin/hello-world
#Install WGET
RUN yum install -y wget
#Install tar
RUN yum install -y tar

# Download and install Tomcat
#RUN cd /space;wget http://svn.dorado.com/dorado/ThirdPartySolutions/tomcat/apache-tomcat-7.0.61.tar.gzhttp://svn.dorado.com/dorado/ThirdPartySolutions/tomcat/apache-tomcat-7.0.61.tar.gz
RUN cd /space;wget http://mirrors.koehn.com/apache/tomcat/tomcat-8/v8.0.33/bin/apache-tomcat-8.0.33.tar.gz
RUN cd /space;gunzip apache-tomcat-8.0.33.tar.gz
RUN cd /space;tar xvf apache-tomcat-8.0.33.tar.gz
RUN chmod -R 755 /space/apache-tomcat-8.0.33.tar.gz
RUN rm -f /space/apache-tomcat-8.0.33.tar.gz

ENTRYPOINT ["/bin/hello-world"]
CMD ["world"]
