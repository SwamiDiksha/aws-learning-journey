# aws-learning-journey

What I am learning ?

- AWS Core Services (EC2, S3, IAM)
- Cloud concepts and architecture
- Hands-on labs and projects

---

## Progress

✅ Cloud Computing & AWS - 100% Complete
- Cloud computing concepts
- AWS fundamentals

🔄 Global Infrastructure of AWS - 50% In Progress
- AWS Regions, Availability Zones
- Edge Locations

🔄 Networking on AWS - 100% In Progress
- VPC (Virtual Private Cloud)
- Subnets and routing
- Security Groups

✅ EC2 - Web Server Project - Complete

---

## 🖥️ Project 1 - AWS EC2 Web Server

### What I Did

**1. Launched an EC2 Instance**
- Amazon Linux 2023
- Instance type: t2.micro (Free Tier eligible)
- Generated a .ppk key pair for SSH access using PuTTY

**2. Configured Security Group**
- Added Inbound Rule for HTTP (Port 80)
- Source: 0.0.0.0/0 (open to all)

**3. Connected to EC2 via PuTTY**
- Used PuTTY (Windows SSH client)
- Authenticated using .ppk private key file
- Connected as user: ec2-user
  <img width="1120" height="503" alt="Screenshot 2026-04-09 164017" src="https://github.com/user-attachments/assets/a5529e5d-36bb-42d0-9815-16fc8be813e7" />


**4. Installed Apache Web Server**
```bash
sudo yum install -y httpd
sudo systemctl start httpd
sudo systemctl enable httpd
```
<img width="1355" height="465" alt="Screenshot 2026-04-09 164918" src="https://github.com/user-attachments/assets/e6c0aa06-c294-4ab0-b9e6-e69012f099ec" />


**5. Created HTML Page**
```bash
echo '<h1>Hello From EC2!</h1>' | sudo tee /var/www/html/index.html
```
<img width="1279" height="353" alt="Screenshot 2026-04-09 165043" src="https://github.com/user-attachments/assets/c9a7e547-2b05-4b22-90b1-3556af0e0376" />


**6. Accessed the Website**
- Opened browser using EC2 Public IP
- Successfully loaded the HTML page! 🎉

### 🛠️ Tools Used
- AWS EC2
- Amazon Linux 2023
- Apache HTTP Server (httpd)
- PuTTY (SSH Client)

### 💡 Key Learnings
- How to launch and configure an EC2 instance
- How to open ports using Security Groups
- How to install Apache and host a webpage on EC2
- How to connect to EC2 using PuTTY on Windows

---

## Resources
- Platform: [GeeksForGeeks](https://www.geeksforgeeks.org/)
- Goal: AWS Cloud Practitioner Certification


 
