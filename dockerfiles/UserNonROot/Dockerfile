# Use the official Jenkins LTS image
FROM jenkins/jenkins:lts

# Create a new user and group (non-root)
USER root  # Temporarily switch to root to create user

RUN groupadd -g 1000 jenkins-user && \
    useradd -m -d /var/jenkins_home -u 1000 -g jenkins-user -s /bin/bash jenkins-user && \
    mkdir -p /var/jenkins_home && \
    chown -R jenkins-user:jenkins-user /var/jenkins_home && \
    chmod -R 755 /var/jenkins_home

# Switch to the non-root user
USER jenkins-user

# Set the working directory
WORKDIR /var/jenkins_home

# Expose Jenkins default port
EXPOSE 8080

# Start Jenkins
CMD ["java", "-jar", "/usr/share/jenkins/jenkins.war"]
