# Install Jenkins on ubuntu (official ) 

```
sudo apt update -y
sudo apt install fontconfig openjdk-17-jre -y

sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
  
echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]" \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
  
sudo apt-get update -y
sudo apt-get install jenkins -y
```
# Verify Jenkins 

```
jenkins --version
```
# Check service status
```
sudo systemctl status jenkins
```

# Access Jenkins
```
http://<EC2-Public-IP>:8080
```
# Get Initial Admin Password
```
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```
Copy the password and paste it into the Jenkins setup page.

Security Group Requirement

Allow inbound traffic on:

Port: 8080
Protocol: TCP
Source: Your IP (recommended)




