# Jenkins Test - 
# FitLife Gym – Jenkins CI/CD Deployment Project

This project demonstrates complete CI/CD automation using Jenkins to deploy a static HTML website to a remote Linux server using SSH and Nginx. The goal of this project is to automatically deploy a website whenever changes are pushed to GitHub.
## Project Scenario
You are hired as a Junior DevOps Engineer at FitLife Gym.
The development team created a static HTML website, and your task was to:
Set up CI/CD infrastructure
Host the website on a target server
Enable automatic deployment on code push
Troubleshoot and fix pipeline issues
nfrastructure Setup
## Jenkins Server Setup
Installed:
* Java (Required for Jenkins)
* Jenkins
* Required Plugins:
* Git Plugin
* Pipeline Plugin
* SSH Agent Plugin
* Configuration:

* Configured SSH credentials (gym-test-key)
* Connected Jenkins with GitHub repository
* Enabled webhook-based build triggers
## Infrastructure Setup
* Jenkins Server
* Install Java
* Install Jenkins
* Install required plugins (Git, Pipeline, SSH Agent)
## Adding SSH Credentials in Jenkins
* Go to Manage Jenkins → Credentials
* Add new credentials
* Select SSH Username with Private Key
* Enter:ubuntu
* Username: ubuntu
* Private Key: (paste private key)
* ID-test-gym-key
## Configure SSH credentials
* Target Server
* Install Nginx
* Open port 80
Verify website access in browser

![alt text](<Screenshot 2026-02-26 180258.png>)
## Create GitHub Repository
* Create repository: gym-static-website
* Add static HTML website
* Push code to GitHub
![alt text](<Screenshot 2026-02-26 181123.png>)

![alt text](<Screenshot 2026-02-26 181036-1.png>)
## Configure Webhook
* Connect GitHub to Jenkins
* Enable automatic build trigger on push
## Create Jenkins Pipeline
* Create Pipeline Job
* Add Jenkinsfile
* Configure repository URL and branch
![alt text](<Screenshot 2026-02-26 180626.png>)
## Pipeline Execution Flow
When developer pushes code:
* Step 1 – Clone Repository
Jenkins pulls latest code from GitHub.
* Step 2 – Deploy to Target Server
Connect via SSH
Copy files to /var/www/html
* Step 3 – Restart Nginx
Restart Nginx service
Updated website goes live
![alt text](<Screenshot 2026-02-26 180916.png>)
## Jenkins MCQs – With Answers
1. What is Jenkins mainly used for?
B) Continuous Integration and Continuous Delivery

2. Which type of job allows you to define build steps using code in Jenkins?
B) Pipeline Project

3. Which file is used to define a pipeline in Jenkins?
C) Jenkinsfile
4. What is the purpose of a Jenkins Agent (Node)?
B) To execute jobs assigned by the Jenkins controller
5. Which plugin is required to connect Jenkins with GitHub?
B) Git Plugin
6.What is the purpose of a Webhook in Jenkins CI/CD?
B) To trigger build automatically on code push
7. Which command is used inside Jenkins Pipeline to execute shell commands?
C) sh
8. What is the purpose of post block in Jenkins Pipeline?
B) Execute steps after pipeline stages
9. What is the use of sshagent in Jenkins Pipeline?
C) Use stored SSH credentials during execution
10. What happens if a stage fails in Jenkins Pipeline (by default)?
B) The pipeline stops execution 