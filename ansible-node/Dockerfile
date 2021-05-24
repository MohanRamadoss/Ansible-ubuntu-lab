FROM ubuntu:18.04

RUN apt-get update \
 && apt-get -y install openssh-server python

RUN mkdir /var/run/sshd
RUN sed -i 's/^#PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config

RUN echo 'root:root&&*' | chpasswd

ARG key_content

RUN mkdir /root/.ssh \
 && echo $key_content > /root/.ssh/authorized_keys \
 && chmod 600 /root/.ssh/authorized_keys

CMD ["/usr/sbin/sshd", "-D"]
