FROM ubuntu:latest

RUN apt-get update && apt-get install -y openssh-server && \
    mkdir /run/sshd && \
    useradd -ms /bin/bash developer && \
    mkdir /home/developer/.ssh && \
    chown developer:developer /home/developer/.ssh && \
    chmod 700 /home/developer/.ssh && \
    sed -i 's/PermitRootLogin yes/PermitRootLogin no/' /etc/ssh/sshd_config && \
    sed -i 's/#PasswordAuthentication yes/PasswordAuthentication no/' /etc/ssh/sshd_config

COPY ./ssh_keys/id_ed25519.pub /home/developer/.ssh/id_ed25519.pub
COPY ./ssh_keys/id_rsa.pub /home/developer/.ssh/id_rsa.pub

RUN cat /home/developer/.ssh/id_ed25519.pub >> /home/developer/.ssh/authorized_keys && \
    cat /home/developer/.ssh/id_rsa.pub >> /home/developer/.ssh/authorized_keys

RUN chown developer:developer /home/developer/.ssh/authorized_keys && \
    chmod 600 /home/developer/.ssh/authorized_keys

EXPOSE 22

CMD ["/usr/sbin/sshd", "-D"]

