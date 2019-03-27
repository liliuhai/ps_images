# AlpineLinux with a hadoop
FROM ps_base:latest

MAINTAINER liliuhai <liliuhai@peersafe.cn>

# Java JAVA_HOME,CLASSPATH and other ENV
ENV HFLINK_HOME=/opt/flink
ENV PATH=${PATH}:${HLINK_HOME}/bin

# do all in one step
RUN curl http://mirrors.tuna.tsinghua.edu.cn/apache/flink/flink-1.7.2/flink-1.7.2-bin-hadoop27-scala_2.11.tgz | tar xvz \
    && mv flink-1.7.2 /opt \
    && ln -s /opt/flink-1.7.2 /opt/flink \
    && echo "export HFLINK_HOME=/opt/flink" >> /root/.bashrc \
    && echo "export PATH=${PATH}:${HFLINK_HOME}/bin" >> /root/.bashrc

# EXPOSE 22

# ENTRYPOINT ["/usr/sbin/sshd", "-D", "-e"]

# EOF
