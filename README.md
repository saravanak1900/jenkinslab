# jenkinslab
## Install Jenkins (Stable) in CentOS
```
sudo yum upgrade -y
sudo yum install epel-release vim wget ntp git -y 
systemctl stop firewalld
systemctl disable firewalld
ntpdate pool.ntp.org

sudo wget -O /etc/yum.repos.d/jenkins.repo   https://pkg.jenkins.io/redhat-stable/jenkins.repo
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key

# Add required dependencies for the jenkins package
sudo yum install java-11-openjdk -y
sudo yum install jenkins -y
sudo systemctl daemon-reload
sudo systemctl enable jenkins
sudo systemctl start jenkins
sudo systemctl status jenkins
cat /etc/passwd | grep jenkins
cat /var/lib/jenkins/secrets/initialAdminPassword > /tmp/initialAdminPassword
```
