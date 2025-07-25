# 🚀 Manual Deployment of Java Web Application on EC2 using Apache Tomcat

This document outlines the step-by-step manual deployment of a Java-based web application on an EC2 instance using Apache Tomcat and Maven.

---

## 🔧 Tech Stack Used

- **Amazon EC2** (Amazon Linux 2)
- **Apache Tomcat 9** (manually installed & configured)
- **Apache Maven** for building the WAR file
- **Java 17**
- **Linux Shell & PuTTY** (for SSH access)
- **WAR Deployment** via Tomcat `webapps/ROOT.war`

---

## 🪜 Deployment Steps

1. **SSH into EC2 Instance**
   - Connected via PuTTY using `.ppk` key
   - OS: Amazon Linux 2

2. **Install Java & Maven**
   ```bash
   sudo yum update -y
   sudo yum install java-17-openjdk -y
   sudo yum install maven -y
   ```

3. **Clone Project from GitHub**
   ```bash
   git clone https://github.com/kaustubh2949/java-manual-deploy.git
   cd java-manual-deploy
   ```

4. **Build WAR File using Maven**
   ```bash
   mvn clean package
   ```
   - Output: `target/your-app.war`  
   - Rename it to `ROOT.war`:
   ```bash
   mv target/your-app.war ROOT.war
   ```

5. **Install Apache Tomcat 9**
   ```bash
   wget https://downloads.apache.org/tomcat/tomcat-9/v9.0.89/bin/apache-tomcat-9.0.89.tar.gz
   tar -xvzf apache-tomcat-9.0.89.tar.gz
   mv apache-tomcat-9.0.89 tomcat9
   ```

6. **Deploy WAR to Tomcat**
   ```bash
   cp ROOT.war ~/tomcat9/webapps/
   ```

7. **Start Tomcat Server**
   ```bash
   cd ~/tomcat9/bin
   chmod +x *.sh
   ./startup.sh
   ```

8. **Open Port 8080 in EC2 Security Group**
   - Navigate to your EC2 instance → Security Group → Inbound Rules → Edit
   - Add rule: `Custom TCP | Port 8080 | 0.0.0.0/0`

9. **Access the App**
   ```
   http://<your-ec2-public-ip>:8080/
   ```

---

## 💡 Challenges Faced

- WAR not auto-extracting: fixed by cleaning existing `webapps/ROOT/` folder
- Tomcat permission issues: resolved with `chmod +x *.sh`
- Port access issues: resolved via EC2 security group configuration

---

## 📌 Learnings

- How WAR files are deployed in Tomcat
- Maven project build lifecycle and packaging
- Manual configuration and startup of Apache Tomcat
- Managing Linux permissions and services on EC2

---

✅ **Status**: Application is running successfully and accessible via browser.

📂 You can view this deployment documentation in this file for future reference.
