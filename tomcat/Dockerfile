FROM centos:centos6

#java-1.8.0-openjdk.x86_64

RUN set -xe;\
    curl https://www.getpagespeed.com/files/centos6-eol.repo --output /etc/yum.repos.d/CentOS-Base.repo;\
    yum update -y;\
    yum install -y wget;\
    yum install -y java-1.8.0-openjdk.x86_64;

RUN set -xe;\
    wget http://dlcdn.apache.org/tomcat/tomcat-9/v9.0.56/bin/apache-tomcat-9.0.56.tar.gz;\
    tar -xvf apache-tomcat-9.0.56.tar.gz;\
    mkdir /usr/local/tomcat;\
    mv apache-tomcat-9.0.56 /usr/local/tomcat;\
    echo 'export CATALINA_HOME=/usr/local/tomcat/apache-tomcat-9.0.56' >> /etc/profile;\
    echo 'export PATH=${PATH}:{CATALINA_HOME}/bin' >> /etc/profile;\
    source /etc/profile;\
    chmod +X /usr/local/tomcat/apache-tomcat-9.0.56/bin/*;

ENTRYPOINT /usr/local/tomcat/apache-tomcat-9.0.56/bin/catalina.sh run
