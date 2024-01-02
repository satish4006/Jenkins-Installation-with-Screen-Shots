Installation Jenkins on Amazon Linux.

Prerequisites:
Minimum hardware requirements:
•	256 MB of RAM Enough for doing proof of concept (POC).
•	1 GB of drive space (although 10 GB is a recommended minimum if running Jenkins as a Docker container) Recommended hardware configuration for a small team:
•	4 GB+ of RAM.
•	50 GB+ of drive space. Software requirements:
•	Jenkins require Java-17 or later versions.
•	Open Port.No 8080 in EC2-security group. (8080 is Default port of Jenkins)
Launch an Amazon Linux EC2 instance.
•	instance-type: t2.micro
Download Jenkins.
Go to Jenkins Download page:-https://www.jenkins.io/download/

 


Select Red Hat/Fedora/Alma/Rocky/CentOS 
 

We will see following command
 



Connect to instance and execute following commands.
# Become a root
sudo su -

# Jenkins repo is added to yum.repos.d
sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo

 

# Import key from Jenkins
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key
 

# Install Java-17
sudo dnf install java-17-amazon-corretto –y
 



# Install Jenkins
yum install jenkins –y
 



#sudo dnf install java-17-amazon-corretto -y


 
Start Jenkins.
# Become a root, no need to execute if you are alread root.
sudo su -

# You can enable the Jenkins service to start at boot with the command:
systemctl enable Jenkins
 

# You can start the Jenkins service with the command:
systemctl start Jenkins
 

# You can check the status of the Jenkins service using the command:
systemctl status jenkins

 

Open Web-Browser and access jenkins on port 8080.
http://<Public-IPv4-address>:8080/
 

The following page we get
 

cat /var/lib/jenkins/secrets/initialAdminPassword
# you will get the password.
 

Copy the Password and past in Web-Browser then press continue.
 






Go with Install Suggested Plugins. 
 
Suggested Plugins will start downloading.
 


Fill the details and click save and continue.
 
Click on Save and Finish.
 



Jenkins is ready click on start using Jenkins 
 
 

