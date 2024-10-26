# Dockerfile for docker-agent and ansible-agent
FROM docker

# Install SSH server
RUN apk update && apk add openssh

# Generate SSH host keys
RUN ssh-keygen -A

# Ensure SSH config allows root login and password authentication
RUN echo "PermitRootLogin yes" >> /etc/ssh/sshd_config && \
    echo "PasswordAuthentication yes" >> /etc/ssh/sshd_config && \
    mkdir -p /root/.ssh

# Start SSH server
CMD ["/usr/sbin/sshd", "-D"]
