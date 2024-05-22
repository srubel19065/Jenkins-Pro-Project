# Jenkins-Pro-Project

## Github
1. Setup github account

## Create a multibranch pipeline and integrate it with github
1. Go to AWS
2. Create an instance for the Jenkins server
3. Connect to that VM and install the dependencies for Jenkins and start the Jenkins server
```
#!/bin/bash

# Update package lists
sudo apt update

# Install Java (OpenJDK 11)
sudo apt install -y openjdk-11-jdk

# Add the Jenkins Debian repository key
curl -fsSL https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -

# Add the Jenkins repository to your sources list
echo "deb [signed-by=/usr/share/keyrings/jenkins-archive-keyring.asc] https://pkg.jenkins.io/debian-stable binary/" | sudo tee /etc/apt/sources.list.d/jenkins.list > /dev/null

# Update package lists again (to include Jenkins repository)
sudo apt update

# Install Jenkins
sudo apt install -y jenkins

# Start Jenkins service
sudo systemctl start jenkins

# Enable Jenkins service to start on boot
sudo systemctl enable jenkins
```