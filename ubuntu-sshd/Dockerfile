FROM ubuntu:18.04
LABEL maintainer "haoduck <p@eng.cx>"

RUN apt update && \
	apt install -y openssh-server && \
	rm -rf /var/lib/apt/lists/* && \
    apt clean && \
    echo root:root | chpasswd && \
    sed -ri "s/^#?.?PermitRootLogin.*$/PermitRootLogin yes/" /etc/ssh/sshd_config && \
	sed -ri "s/^#?.?UsePAM yes/#UsePAM yes/g" /etc/ssh/sshd_config && \
    sed -ri "s/^#?.?PasswordAuthentication.*$/PasswordAuthentication yes/g" /etc/ssh/sshd_config && \
    mkdir -p /var/run/sshd

EXPOSE 22

CMD ["/usr/sbin/sshd", "-D"]