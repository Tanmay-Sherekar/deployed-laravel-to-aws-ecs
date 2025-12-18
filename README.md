# deployed-laravel-to-aws-ecs
----------------------------------------------------------------
Deployed the laravel code from bitbucket to Jenkins CI/CD
-----------------------------------------------------------------
First, We Study about the Jenkins. What is Jenkins?
-	Jenkins is an open-source automation server used primarily for continuous integration and continuous delivery (CI/CD) Pipelines.
-	It allows developers to automate the process of building, testing and deploying software applications.
-	Here how it works:
1)	Developers commit code changes to a version control system like GIT.
2)	Jenkins monitors the version control system for changes
3)	When changes are detected, Jenkins pulls the code, initiates the build process, and runs automated tests.
4)	If the build and tests are successful, Jenkins can deploy the application to various environments, such as development, staging, or production. 
Now, Moving towards the steps:
1)	Login to your AWS account----->Dashboard---->Search EC2
2) Create EC2 Instance with instance type “t2.medium”
3) Click on the running Jenkins instance- scroll down to Security groups  Open the port “8080”, ”22’, “80”, “443”
4) Now, click “Connect” then “Connect”
5) Type:-  sudo su to change user to root user
6)	systemctl status jenkins.service
7)	sudo su -s/bin/bash Jenkins bash-5.2s aws configure
8)	Now Type and search “Elastic container Registry”  | “ECR”
9)	Now go to “ECS” as shown above
10)	Now go to instance you create “EC2 i.e Jenkins Instance”
11)	Copy Public Url followed by colon 8080 like this ex.10.0.149.116:8080
12)	Login to Jenkins admin,admin
13)	Click on “New Item” -> Manage Jenkins -> Install Plugins
14)	In Jenkins-> branch specifier /main, script path JenkinsFile -> Build Now
15)	Copy the public, paste and hit enter , you will see the Laravel screen
