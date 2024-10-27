<h1>Project Setup</h1>

<p>This repository contains a structured setup for deploying Jenkins , Ansible and Docker in Docker using Docker. The directory structure includes Dockerfiles for both Jenkins and Ansible, as well as necessary configuration files.</p>

<h2>Folder Structure</h2>
<pre>
folder
  ├── ansible
  │   └── Dockerfile        # Dockerfile for Ansible
  ├── docker
  │   └── Dockerfile        # Dockerfile for Jenkins
  ├── playbooks             # Directory for Ansible playbooks
  ├── jenkins_home          # Jenkins home directory
  └── docker-compose.yml     # Docker Compose configuration
</pre>

<h2>Getting Started</h2>

<h3>Prerequisites</h3>
<ul>
    <li>Docker</li>
    <li>Docker Compose</li>
</ul>

<h3>Instructions</h3>
<ol>
    <li><strong>Clone the Repository:</strong>
        <pre>
        git clone https://github.com/prasaisushant/Jenkins_ansible_docker_compose.git
        cd &lt;repository_folder&gt;
        </pre>
    </li>
    <li><strong>Set Permissions for Jenkins Home:</strong>
        <pre>
        sudo chown -R 1000:1000 jenkins_home
        sudo chmod -R 755 jenkins_home
        </pre>
    </li>
    <li><strong>Start the Services:</strong>
        <pre>
        docker-compose up      # Use -d for detached mode
        </pre>
    </li>
</ol>

<h2>Accessing Services</h2>
<ul>
    <li><strong>Jenkins:</strong> Access Jenkins at <code>https://&lt;host_ip&gt;:8080</code></li>
    <li><strong>Ansible container (via SSH):</strong> Access the Ansible container through SSH:
        <pre>
        ssh root@&lt;host-ip&gt; -p 2000
        </pre>
        <p><strong>Password:</strong> ansible</p>
    </li>
    <li><strong>Docker container (via SSH):</strong> Access the Docker container through SSH:
        <pre>
        ssh root@&lt;host-ip&gt; -p 2001
        </pre>
        <p><strong>Password:</strong> docker</p>
    </li>
</ul>
</ul>

<h2>Notes</h2>
<ul>
    <li>Ensure that you replace <code>&lt;host_ip&gt;</code> with the actual IP address of your host machine.</li>
    <li> For those using docker desktop in replace used localhost in place of host-ip</li>
    <li>Make sure your firewall settings allow traffic on the required ports (8080 for Jenkins, 2000 for Ansible).</li>
</ul>
