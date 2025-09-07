# EC2-Instance
Process of Creating a EC2 instance and Monitoring it

# AWS EC2 Instance Lifecycle Documentation

This document provides a step-by-step walkthrough of working with an **Amazon EC2 instance**:  
- Launching the instance  
- Monitoring and managing   
- Resizing when needed  
- Attaching additional storage (EBS Volume)  
- Terminating 

---

##  1. Launching an EC2 Instance

1. **Login to AWS Management Console**  
   - Go to [EC2 Dashboard]

2. **Launch a New Instance**  
   - Click **Launch Instance**.  
   - Select an **Amazon Machine Image (AMI)** (e.g Amazon Linux) 
   - Choose an **Instance Type** (e.g., `t2.micro` for free tier).  

3. **Configure Instance Details**  
   - Set VPC, subnet, and enable auto-assign public IP if needed.  
   - Keep defaults unless specific networking is required.  

4. **Add Storage (Default EBS Root Volume)**  
   - A default 8GB EBS volume is provided.  
   - You can adjust the size if required.  

5. **Key Pair Setup**  
   - Create or select an existing **key pair (.pem)** file.  
   - This will be used for SSH login.  

6. **Launch Instance**  
   - Review settings → **Launch**.  
   - Wait until the **Instance State** shows **running**.  

---

##  2. Monitoring the Instance

1. **CloudWatch Metrics**  
   - Monitor CPU Utilization, Network In/Out, Disk I/O from the **Monitoring tab**.  

2. **System Status Checks**  
   - Ensure both **System Status** and **Instance Status** checks are passing.  

3. **Manual Monitoring via SSH**  
   ```bash
   ssh -i my-key.pem ubuntu@<public-ip>
   top
   df -h
   free -m
