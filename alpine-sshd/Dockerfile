FROM alpine:3.12
LABEL maintainer "haoduck <p@eng.cx>"

RUN RUN apk add --no-cache \
	openssh-server && \
    rm -rf /var/cache/apk/* && \
    echo root:root | chpasswd && \
    sed -ri "s/^#?.?PermitRootLogin.*$/PermitRootLogin yes/" /etc/ssh/sshd_config && \
	sed -ri "s/^#?.?UsePAM yes/#UsePAM yes/g" /etc/ssh/sshd_config && \
    sed -ri "s/^#?.?PasswordAuthentication.*$/PasswordAuthentication yes/g" /etc/ssh/sshd_config && \
    mkdir -p /var/run/sshd

EXPOSE 22

CMD ["/usr/sbin/sshd", "-D"]