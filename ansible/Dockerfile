FROM alpine/ansible:latest

# Set root password to "ansible"
RUN echo 'root:ansible' | chpasswd

RUN apk update && \
    apk add --no-cache openjdk11-jre openssh curl && \
    mkdir -p /var/run/sshd

RUN ssh-keygen -A

# Configure SSH
RUN echo "PermitRootLogin yes" >> /etc/ssh/sshd_config && \
    echo "PasswordAuthentication yes" >> /etc/ssh/sshd_config && \
    mkdir -p /root/.ssh

RUN adduser --disabled-password jenkins


# Start SSH server
CMD ["/usr/sbin/sshd", "-D"]
