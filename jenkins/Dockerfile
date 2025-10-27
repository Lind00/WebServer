# Start from the official Jenkins LTS image
FROM jenkins/jenkins:lts-jdk17

# Switch to root to install Docker
USER root

# Install Docker CLI and docker-compose plugin
#RUN apt-get update && \
#    apt-get install -y docker.io docker-compose-plugin && \
#    rm -rf /var/lib/apt/lists/*

# Install Docker Compose (standalone binary)
RUN curl -L "https://github.com/docker/compose/releases/download/v2.22.1/docker-compose-$(uname -s)-$(uname -m)" \
    -o /usr/local/bin/docker-compose && \
    chmod +x /usr/local/bin/docker-compose

# Give Jenkins user access to Docker
RUN groupadd -f docker && usermod -aG docker jenkins

# Swtich back to Jenkins user
USER jenkins
