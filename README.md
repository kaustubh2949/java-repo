# Java Web App – CI/CD with AWS 🚀

This project showcases a Java-based web application deployed using a fully automated CI/CD pipeline with AWS services.

## 🔧 Tools Used
- Java (JSP)
- Maven
- AWS CodePipeline
- AWS CodeBuild
- AWS Elastic Beanstalk
- AWS CloudWatch Logs
- GitHub

## ⚙️ CI/CD Workflow
- Code pushed to GitHub
- CodePipeline auto-triggers
- CodeBuild compiles & packages WAR
- Elastic Beanstalk deploys the app
- CloudWatch monitors logs and health

## 💻 Manual EC2 Deployment (Before CI/CD)
Before setting up the CI/CD pipeline, the app was manually deployed on an EC2 instance using Apache Tomcat:

- Connected to EC2 via SSH
- Installed Java, Tomcat, and Maven
- Configured Tomcat server and deployed WAR manually
- Steps are fully documented in:
  - `DETAILED-GUIDE-ec2-tomcat-deployment.md`
  - `QUICK-START-ec2-tomcat-deployment.txt`

This helped understand the underlying deployment process before automating it.

## 📁 Files in This Repo
- `buildspec.yml` – CodeBuild instructions
- `appspec.yml` – Elastic Beanstalk config
- `install.sh` – App installation script
- `pom.xml` – Maven build file
- `src/main/webapp/` – JSP files (UI)
- `DETAILED-GUIDE-ec2-tomcat-deployment.md` – Manual EC2 deployment steps
- `QUICK-START-ec2-tomcat-deployment.txt` – Short guide for EC2 deployment

## 📌 Highlights
- Automated CI/CD pipeline (no manual steps)
- Real-time logs via CloudWatch
- Production-ready deployment workflow
- JSP pages: `index.jsp`, `register.jsp`, `logout.jsp`

## 📎 Author
**Kaustubh Kishor Tandale**  
GitHub: [kaustubh2949](https://github.com/kaustubh2949)
