
# Set Up a Web App in the Cloud


---


## Introducing Today's Project!

Today I am going to set up VS code, install maven and Java, so that I can lay the foundation for building my web app.

### Key tools and concepts

Services I used were AWS EC2, VS Code, AWS IAM, ssh, and  Remote - SSH. Key concepts I learned included how to ssh into an instance, how to access the config file, and how to access my web app.

### Project reflection

One thing I didn't expect was to be using the terminal as often as I did.

This project took me approximately 2 and a half hours to complete. The most challenging part was trying to ssh into the instance after installing the Remote - SSh extension.

This project is part one of a series of DevOps projects where I'm building a CI/CD pipeline!

---

## Launching an EC2 instance

I started this project by launching an EC2 instance, an EC2 instance are like virtual computers which I can use to store my web app in the cloud.

### I also enabled SSH

SSH is a protocal used to connect to servers remotely using a private key, it uses encryption to make sure no one can see what you're doing within the server. I enabled SSH so that it will only allow access to traffic with my IP address.

### Key pairs

A key pair is a public and private key that is used for ssh access into a computer.

Once I set up my key pair, AWS automatically downloaded a keypair.pem file into my computer. I will this key to connect to EC2 my instance.

---

## Set up VS Code

VS Code is a text editor IDE that is used to edit the code. It has a multitude of resources and different coding languages that you can install and run.

I installed VS Code to log into my EC2 instance through the terminal.

![Image](http://learn.nextwork.org/intense_azure_festive_sow/uploads/aws-devops-vscode_53d05e68)

---

## My first terminal commands

The first command I ran in this project was cd /Desktop/DevOps. This command took my to the downloads directory where the DevOps folder resides.

I also updated my private key's permissions by using the windows icals commands,

<pre>
icacls "nextwork-keypair.pem" /reset
icacls "nextwork-keypair.pem" /grant:r "USERNAME:R"
icacls "nextwork-keypair.pem" /inheritance:r
</pre>



![Image](http://learn.nextwork.org/intense_azure_festive_sow/uploads/aws-devops-vscode_9328ada1)

---

## SSH connection to EC2 instance

To connect to my EC2 instance, i ran the command below.
<pre>
ssh -i "nextwork-keypair.pem" ec2-user@ec2-54-85-23-61.compute-1.amazonaws.com
</pre>

### This command required an IPv4 address

A server's IPV4 DNS is the public address for your EC2 server that the internet uses to find and connect to it. I'm going to use this to find and connect to my EC2 instance from my personal computer.

![Image](http://learn.nextwork.org/intense_azure_festive_sow/uploads/aws-devops-vscode_e3069dca)

---

## Maven & Java

Apache Maven is a tool that helps developers build and organize Java software projects. It's also a package manager, which means it automatically download any external pieces of code your project depends on to work.

Maven is required for this project because it helps with structuring and formatting web apps quickly.

Java is a popular programming language that is used for many different applications today, especially mobile apps and enterprise systems.

Java is required for this project because Apache Maven needs Java to run.

---

## Create the Application

I generated a Java web app using the command below.
<pre>
  mvn archetype:generate \
   -DgroupId=com.nextwork.app \
   -DartifactId=nextwork-web-project \
   -DarchetypeArtifactId=maven-archetype-webapp \
   -DinteractiveMode=false
</pre>


I installed Remote - SSH because, which is an extension in VS Code. I used it to remotely access my EC2 instance and have it show in the console instead of in the terminal.

Configuration details reruired to set up a remote connection include, the key pair.pem file and the EC2 instance DNS address.

![Image](http://learn.nextwork.org/intense_azure_festive_sow/uploads/aws-devops-vscode_2939cf01)

---

## Create the Application

Using VS Code's file expolorer, I could see all of the files and folders that were related to my web app like the src, pom.xml, and resources to name a few.

Two of the project folders created by Maven are src and webapp which contain the source code for the web app and the code for look and shape of the web app respectively.

![Image](http://learn.nextwork.org/intense_azure_festive_sow/uploads/aws-devops-vscode_45f91fd7)

---

## Using Remote - SSH

Index.jsp is similar to an html file but unlike html, index.jsp allows for the use of Java code inside of it which allows dynamic changes to happen to the web app display.

I edited index.jsp by highlighting the entire code and replacing it with the snippet.

![Image](http://learn.nextwork.org/intense_azure_festive_sow/uploads/aws-devops-vscode_7a1de541)

---

