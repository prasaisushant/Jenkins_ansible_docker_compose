FROM ansible/ansible:ubuntu1404

# Set root password to "ansible"
RUN echo 'root:ansible' | chpasswd

# Configure SSH
RUN sed -i 's/^PermitRootLogin without-password/PermitRootLogin yes/' /etc/ssh/sshd_config && \
    echo "PasswordAuthentication yes" >> /etc/ssh/sshd_config && \
    mkdir -p /root/.ssh && \
    mkdir -p /var/run/sshd && \
    chmod 0755 /var/run/sshd  # Ensure the directory has correct permissions

# Start SSH server
CMD ["/usr/sbin/sshd", "-D"]
