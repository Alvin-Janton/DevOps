
# Continuous Integration with CodeBuild


---

## Introducing Today's Project!

In this project, I will demonstrate my current project successfully compiling using CodeBuild. I'm doing this project to learn how to integrate CodeBuild as a continuous integration tool.

### Key tools and concepts

Services I used were AWS CodeBuild, IAM, CodeArtifact, S3, and GitHub. Key concepts I learnt include how to connect CodeBuild to GitHub using CodeConnection, how to configure CodeBuild for continuous integration, how to connect CodeBuild and CodeArtifact using IAM roles, and how to troubleshoot problems in CodeBuild using CloudWatch logs.

### Project reflection

This project took me approximately two hours to complete. The most challenging part was connecting my GitHub account to my AWS environment. It was most rewarding to see a successful build from CodeBuild.

This project is part four of a series of DevOps projects where I'm building a CI/CD pipeline!

---

## Setting up a CodeBuild Project

CodeBuild is a continuous integration service, which means it automatically builds and runs tests for a program whenever new code is pushed. Engineering teams use it because it saves time, is consistent, and is cost-effective.

My CodeBuild project's source configuration means, the environment where my code is located for CodeBuild to find and run, and for my source, I selected GitHub.

![Image](http://learn.nextwork.org/intense_azure_festive_sow/uploads/aws-devops-codebuild-updated_fewgrhte)

---

## Connecting CodeBuild with GitHub

There are multiple credential types for GitHub, like GitHub app, token access tokens, or OAuth app. I used GitHub App because it is the simplest way to connect accounts while still having strong security.

The service that helped connect my GitHub account to my CodeBuild project is CodeConnection, a service offered by AWS to securely connect and manage accounts.

![Image](http://learn.nextwork.org/intense_azure_festive_sow/uploads/aws-devops-codebuild-updated_a7c98e2d)

---

## CodeBuild Configurations

### Environment

My CodeBuild project's Environment configuration means telling CodeBuild how I want it to do its test, it includes settings like provisioning model, environment image, compute, operating system, and much more.

### Artifacts

Build artifacts are a file that stores everything your application needs to run. My build process will create a WAR file, and to store them, I created an S3 bucket.

### Packaging

When setting up CodeBuild, I also chose to package artifacts in a zip file because this makes it so that all the resources needed for this project will be placed into one, lightweight, easily executed file.

### Monitoring

For monitoring, I enabled CloudWatch Logs, which is a tool that will log the process when CodeBuild runs the program, like commands executed, and errors.

---

## buildspec.yml

My first build failed because CodeBuild was trying to run the buildspec.yml file, but it did not exist in my GitHub repository. A buildspec.yml file is needed because that is what CodeBuild uses as instructions on how to build the code.

The first two phases in my buildspec.yml file are install and pre-build, where CodeBuild will install the necessary resources and use the authentication token. The third phase is build, where it will compile. Fourth is post-build phase where it will create the WAR file.

![Image](http://learn.nextwork.org/intense_azure_festive_sow/uploads/aws-devops-codebuild-updated_35588a47)

---

## Success!

My second build also failed, but with a different error that said "Error while executing command: mvn -s settings.xml compile". To fix this, I have to create an IAM policy to allow CodeBuild to access the settings.xml file.

To resolve the second error, I went to AWS IAM and found the role created for my CodeBuild and attached the consumer permissions that I created to CodeArtifact to CodeBuild. When I built my project again, I saw that it was successful.

To verify the build, I checked the S3 bucket I created to hold the resources related to this project. Seeing the artifact tells me that the build was successful.

![Image](http://learn.nextwork.org/intense_azure_festive_sow/uploads/aws-devops-codebuild-updated_d9cc6191)

---
