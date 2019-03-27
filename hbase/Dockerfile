# AlpineLinux with a hadoop
FROM ps_base:latest

MAINTAINER liliuhai <liliuhai@peersafe.cn>

# Java JAVA_HOME,CLASSPATH and other ENV
ENV HBASE_HOME=/opt/hbase
ENV PATH=${PATH}:${HBASE_HOME}/bin

# do all in one step
RUN curl http://mirrors.tuna.tsinghua.edu.cn/apache/hbase/1.4.9/hbase-1.4.9-bin.tar.gz | tar xvz \
    && mv hbase-1.4.9 /opt \
    && ln -s /opt/hbase-1.4.9 /opt/hbase \
    && echo "export HBASE_HOME=/opt/hbase" >> /root/.bashrc \
    && echo "export PATH=${PATH}:${HBASE_HOME}/bin" >> /root/.bashrc \
    && mkdir -p /root/data/hbase/{pids,tmp}

# EXPOSE 22

# ENTRYPOINT ["/usr/sbin/sshd", "-D", "-e"]

# EOF
