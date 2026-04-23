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

## 🪣 Project 2 — AWS S3 Static Website

### What I Did

**1. Created an S3 Bucket**
- S3 Console → Create bucket → Unique name → Select region
- Disabled "Block all public access"

**2. Enabled Static Website Hosting**
- Bucket → Properties → Static website hosting → Enabled
- Index document: `index.html`
- Copied the public endpoint URL provided by AWS

**3. Uploaded HTML File**
- Uploaded `index.html` via the AWS console

**4. Set Bucket Policy for Public Access**
- Bucket → Permissions → Bucket Policy → Added:
```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "Statement1",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::diksha1b/*"
        }
    ]
}
```

**5. Accessed the Website**
- Opened the S3 endpoint URL in browser → Page loaded successfully 🎉

### 🛠️ Tools Used
- Amazon S3
- S3 Bucket Policy
- AWS Console

### 💡 Key Learnings
- What S3 buckets are and how object storage works
- How to enable static website hosting on S3
- How bucket policies control public access to objects
- Difference between S3 as storage vs S3 as a web server
- How S3 generates a public endpoint URL


## 🗄️ Project 3 — AWS RDS MySQL Database

### What I Did

**1. Created an RDS Instance**
- RDS Console → Create database → Standard Create
- Engine: MySQL | Template: Free Tier
- Set DB identifier, master username & password

**2. Configured Connectivity**
- VPC: Default | Enabled public accessibility
- Security Group inbound rule: MySQL/Aurora → Port 3306 → 0.0.0.0/0

**3. Waited for Instance to Launch**
- Status: creating → available
- Copied the RDS endpoint from the console

**4. Connected via MySQL Workbench**
- New Connection → RDS endpoint as hostname → Port: 3306
- Entered master credentials → Connected successfully ✅

**5. Ran Basic SQL Queries**
```sql
CREATE DATABASE mydb;
USE mydb;
CREATE TABLE users (id INT, name VARCHAR(50));
INSERT INTO users VALUES (1, 'Sanket');
SELECT * FROM users;
```

### 🛠️ Tools Used
- Amazon RDS
- MySQL Engine
- MySQL Workbench
- Security Groups
- AWS Console

### 💡 Key Learnings
- What managed databases are and why RDS simplifies administration
- How to launch a MySQL RDS instance on Free Tier
- How to configure Security Groups to allow DB access on port 3306
- How to connect to RDS remotely using MySQL Workbench
- Difference between RDS (managed) vs self-hosted DB on EC2
  
---

## Resources
- Platform: [GeeksForGeeks](https://www.geeksforgeeks.org/)
- Goal: AWS Cloud Practitioner Certification


 
