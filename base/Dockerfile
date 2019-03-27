# AlpineLinux with a openssh-client,openssh-server,curl,bash and openjdk8
FROM centos:7

MAINTAINER liliuhai <liliuhai@peersafe.cn>

# Java JAVA_HOME,CLASSPATH and other ENV
ENV JAVA_HOME=/usr/lib/jvm/java \
    JAR_HOME=/usr/lib/jvm/jar
ENV CLASSPATH=.:${JAVA_HOME}/lib/dt.jar:${JAVA_HOME}/lib/tools.jar:${JAR_HOME}/lib \
    PATH=${PATH}:${JAVA_HOME}/bin:${JAR_HOME}/bin \
    USER=root \
    LC_ALL=en_US.UTF-8

# do all in one step
RUN yum install -y java-1.8.0-openjdk-devel openssh-server openssh-clients which \
    && yum clean headers packages metadata dbcache plugins expire-cache rpmdb \
    && echo "export JAVA_HOME=/usr/lib/jvm/java" >> /root/.bashrc \
    && echo "export JAR_HOME=/usr/lib/jvm/jre" >> /root/.bashrc \
    && echo "export CLASSPATH=.:${JAVA_HOME}/lib/dt.jar:${JAVA_HOME}/lib/tools.jar:${JAR_HOME}/lib" >> /root/.bashrc \
    && echo "export PATH=${PATH}:${JAVA_HOME}/bin:${JAR_HOME}/bin" >> /root/.bashrc \
    && echo "export USER=root" >> /root/.bashrc \
    && echo "export LC_ALL=en_US.UTF-8" >> /root/.bashrc \
    && sed -i s/#PermitRootLogin.*/PermitRootLogin\ yes/ /etc/ssh/sshd_config \
    && ssh-keygen -A

EXPOSE 22

ENTRYPOINT ["/usr/sbin/sshd", "-D", "-e"]

# EOF
