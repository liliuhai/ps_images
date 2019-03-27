# AlpineLinux with a hadoop
FROM liliuhai/ps_base:latest

MAINTAINER liliuhai <liliuhai@peersafe.cn>

# Java JAVA_HOME,CLASSPATH and other ENV
ENV HADOOP_HOME=/opt/hadoop
ENV PATH=${PATH}:${HADOOP_HOME}/bin:${HADOOP_HOME}/sbin

# do all in one step
RUN curl http://mirrors.tuna.tsinghua.edu.cn/apache/hadoop/common/hadoop-2.7.7/hadoop-2.7.7.tar.gz | tar xvz \
    && mv hadoop-2.7.7 /opt \
    && ln -s /opt/hadoop-2.7.7 /opt/hadoop \
    && echo "export HADOOP_HOME=/opt/hadoop" >> /root/.bashrc \
    && echo "export PATH=${PATH}:${HADOOP_HOME}/bin:${HADOOP_HOME}/sbin" >> /root/.bashrc \
    && mkdir -p /root/hadoop_run/{hdfs/{data,name},journaldata,tmp}

# EXPOSE 22

# ENTRYPOINT ["/usr/sbin/sshd", "-D", "-e"]

# EOF
