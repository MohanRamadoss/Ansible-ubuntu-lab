FROM ubuntu:18.04
RUN apt-get update \
 && apt-get install -y software-properties-common \
 && apt-add-repository --yes --update ppa:ansible/ansible \
 && apt-get install -y ansible vim
RUN ssh-keygen -t rsa -f /root/.ssh/id_rsa -N ""
