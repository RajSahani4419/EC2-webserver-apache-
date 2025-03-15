#EC2 Apache Web Server Setup

# 📖 Apache Web Server Setup on AWS EC2

## 🛠 Prerequisites
- An **AWS Account**
- A **running EC2 instance** (Ubuntu 22.04)
- **SSH access** to the EC2 instance

## Step 1: Create an EC2 instance

- Go to AWS console
- Launch an EC2 instance
- Download and Save Key .pem file
- Go to EC2 instance which is launched
- Copy the Public IPv4 address.

## Step 2: Connect to EC2 via SSH 
On Bash
If using Ubuntu 
ssh -i "your-key.pem" ubuntu@your-ec2-public-ip

If using Amazon Linux 
ssh -i "your-key.pem" ec2-user@your-ec2-public-ip

##  Step 3: Update System Packages

For Ubuntu
sudo apt update && sudo apt upgrade -y

##   Step 4: Install Apache Web Server
sudo apt install apache2 -y


##   Step 5; Start & Enable and check Status of Apache Service
sudo systemctl start apache2
sudo systemctl enable apache2
sudo systemctl status apache2

##   Step 6: Allow HTTP Traffic in Security Groups

Navigate to AWS Console > EC2 > Security Groups
Edit Inbound Rules and allow HTTP (Port 80).


##   Step 7: Deploy a Custom Webpage
On Bash
- Update index.html file in /var/www/html directory.
- edit index.html
- Replace the default index.html file with nano Command
- Update the index.html with echo "<h1>Welcome to My Apache Web Server on EC2 🚀</h1>" > /var/www/html/index.html
save and exit.
 
##  Step 8: Verify Deployment
- Open EC2 public Ip in browser : http://your-ec2-public-ip

