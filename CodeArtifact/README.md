
# Secure Packages with CodeArtifact


---


## Introducing Today's Project!

In this project, I will demonstrate managing packages using AWS CodeArtifiact. I'm doing this project to learn about cloud and cloud security.

### Key tools and concepts

Services I used were AWS IAM, CodeArtifact, and AWS EC2. Key concepts I learned were how to create a CodeArtifact repo, how to create IAM roles and connect them to an EC2 instance, how to create a settings.xml file and how to connect CodeArtifact.

### Project reflection

This project took me approximately one and a half hours. The most challenging part was configuring the CodeArtifact authorization code to work. The most rewarding part was seeing the packages displayed in the CodeArtifact.

This project is part three of a series of DevOps projects where I'm building a CI/CD pipeline!

---

## CodeArtifact Repository

CodeArtifact is a reposititory who's sole purpose is to provide a secure central location for developers to find packages. Engineering teams use artifact repositories because they're secure and reliable.

A domain is is like a folder that holds multiple repositories belonging to the same project or organization. My domain is nextwork-522814735684.d.codeartifact.us-east-1.amazonaws.com.

A CodeArtifact repository can have an upstream repository, which means it connects to a overseer repository where it can go and find libraries that are missing from our CodeArtifact repository. My respository's upstream repository is Maven Central.

![Image](http://learn.nextwork.org/intense_azure_festive_sow/uploads/aws-devops-codeartifact-updated_n4o5p6q7)

---

## CodeArtifact Security

### Issue

To access CodeArtifact, we need an authorization token. I ran into an error when retrieving a token because my EC2 instance does not have permission to interact with my other AWS resources.

### Resolution

To resolve the error with my security token, I created a IAM policy allowing the CodeArtifact repository to have access to my EC2 instance, then I created a role for the EC2 instance so it would listen to CodeArtifact.

It's security best practice to use IAM roles because it enforces the principal of least privelage, allowing resources to have access to other resources while having no access to others.

---

## The JSON policy attached to my role

The JSON policy I set up grants the CodeArtifact permission to get authentication tokens, find repository locations, and read packages from repositories allows temporarily elevated access specifically for CodeArtifact operations, for all resources.

![Image](http://learn.nextwork.org/intense_azure_festive_sow/uploads/aws-devops-codeartifact-updated_23rp7q8r9)

---

## Maven and CodeArtifact

### To test the connection between Maven and CodeArtifact, I compiled my web app using settings.xml

The settings.xml file configures Maven to check the CodeArtifact repository first before looking elsewhere. Creating a seamless connection between the two.

Compiling means that you're turning the code written in the text editor into binary that the computer can read and execute.

![Image](http://learn.nextwork.org/intense_azure_festive_sow/uploads/aws-devops-codeartifact-updated_c17eace8)

---

## Verify Connection

After compiling, I checked my CodeArtifact repository. I noticed that the required dependencies had been automatically installed.

![Image](http://learn.nextwork.org/intense_azure_festive_sow/uploads/aws-devops-codeartifact-updated_1d79e699)

---

