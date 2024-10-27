# Dockerfile for docker-agent and ansible-agent
FROM docker

# Install SSH server and Java
RUN apk update && apk add --no-cache openssh openjdk11-jre curl

# Generate SSH host keys
RUN ssh-keygen -A

RUN echo 'root:docker' | chpasswd

# Ensure SSH config allows root login and password authentication
RUN echo "PermitRootLogin yes" >> /etc/ssh/sshd_config && \
    echo "PasswordAuthentication yes" >> /etc/ssh/sshd_config && \
    mkdir -p /root/.ssh

RUN adduser --disabled-password jenkins

# Start SSH server
CMD ["/usr/sbin/sshd", "-D"]