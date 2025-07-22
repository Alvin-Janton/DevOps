
# Deploy a Web App with CodeDeploy



---



## Introducing Today's Project!

In this project, I will demonstrate how to set up and use CodeDeploy to automate the deployment of code to a production environment. I'm doing this project to learn how to use CodeDeploy in a CI/CD pipeline.

### Key tools and concepts

Services I used were CodeDeploy, CloudFormation, and script files. Key concepts I learnt include how to configure and launch a stack using CloudFormation, and how to configure and run CodeDeploy and CodeDeployment groups.

### Project reflection

This project took me approximately two hours to complete. Nothing was particularly challenging in this project. It was most rewarding to see a successful deployment from CodeDeploy.

This project is part five of a series of DevOps projects where I'm building a CI/CD pipeline!

---

## Deployment Environment

To set up for CodeDeploy, I launched an EC2 instance and VPC because this is where I'm going to deploy my web app to the public.

Instead of launching these resources manually, I used CodeDeploy to automate the process. When I need to delete these resources, they will all get deleted together once CodeDeploy is deleted.

Other resources created in this template include VPC, subnets, EC2 instance, security groups, routing tables, and an internet gateway. They're also in the template because they're all connected through CodeDeply.

![Image](http://learn.nextwork.org/intense_azure_festive_sow/uploads/aws-devops-codedeploy-updated_val-5)

---

## Deployment Scripts

Scripts are files that are used to automate the installation of resources. To set up CodeDeploy, I also wrote scripts to download Tomcat and Java. I also made it so the two are connected and can communicate. 

Install_dependencies will install Tomcat and Java, and connect the two. Then it will create a reverse proxy server so that Apache will send the request to Tomcat.

start_server.sh will enable both the Tomcat application server and the Apache web server. Also, it will restart both whenever the server restarts.

stop_server.sh will check to see if the Apache web server is running, and if it is, it will shut it down. It will do the same for the Tomcat application server.

---

## appspec.yml

Then, I wrote an appspec.yml file to instruct CodeDeploy as to what it should do when compiling the code. The key sections in appspec.yml are "BeforeInstall", "ApplicationStart", and "ApplicationStop".

I also updated buildspec.yml because, without the specific paths, CodeDeploy won't know where the script files are and won't deploy correctly.

![Image](http://learn.nextwork.org/intense_azure_festive_sow/uploads/aws-devops-codedeploy-updated_val-12)

---

## Setting Up CodeDeploy

A deployment group is a collection of EC2 instances that are used to create the environment for your code deployment. A CodeDeploy application is a folder that holds these deployment groups.

To set up a deployment group, you also need to create an IAM role to permit CodeDeploy to create resources, delete resources, and perform many other functions.

Tags help keep track of instances, quickly find instances, and group instances together. I used the tag to tell CodeDeploy which EC2 instance/instances to use.

![Image](http://learn.nextwork.org/intense_azure_festive_sow/uploads/aws-devops-codedeploy-updated_val-18)

---

## Deployment configurations

Another key setting is the deployment configuration, which affects the number of instances that are updated during a deployment. I used CodeDeploy.AllAtOnce, so it will deploy the updates to all the instances simultaneously.

To connect an EC2 instance to CodeDeploy, you must use a CodeDeploy Agent. A CodeDeploy Agent is also set up to carry out instructions given to it by CodeDeploy and pass it onto the EC2 instance.

![Image](http://learn.nextwork.org/intense_azure_festive_sow/uploads/aws-devops-codedeploy-updated_val-20)

---

## Success!

A CodeDeploy deployment is a single update to my application. The difference between a deployment group and a deployment is that a deployment group is multiple deployments happening all at once, or one at a time, depending on your configurations.

I had to configure a revision location, which means this is the location for my build artifact. My revision location was the URI for my S3 bucket that holds the artifact.

To check that the deployment was a success, I visited the public IP address of the EC2 instance. I saw the web page that we created back in step two.

![Image](http://learn.nextwork.org/intense_azure_festive_sow/uploads/aws-devops-codedeploy-updated_val-27)

---

