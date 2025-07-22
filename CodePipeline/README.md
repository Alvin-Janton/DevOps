
# Build a CI/CD Pipeline with AWS



---



## Introducing Today's Project!

In this project, I will demonstrate how to set up an automatic CI/CD pipeline using CodePipeline. I'm doing this project to learn more about cloud and cloud security.

### Key tools and concepts

Services I used were CodePipeline. Key concepts I learnt include how to configure settings for CodePipeline, how to monitor and check for successful CodePipeline executions.

### Project reflection

This project took me approximately one and a half hours. Nothing about this challenge was particularly difficult. It was most rewarding to see my web app changes deploy successfully through CodePipeline.

---

## Starting a CI/CD Pipeline

AWS CodePipeline is a tool that automatically integrates and deploys your code whenever a change to your GitHub repository is made.

CodePipeline offers different execution modes based on how the pipeline is run. I chose superceded; other options include queued and parallel.

'A service role gets created automatically during setup so that CodePipeline is automatically granted permissions to access and change resources.

![Image](http://learn.nextwork.org/intense_azure_festive_sow/uploads/aws-devops-codepipeline-updated_gdnhtm)

---

## CI/CD Stages

The three stages I've set up in my CI/CD pipeline are source, build, and deploy. While setting up each part, I learnt about how to configure a CodePipeline.

CodePipeline organizes the three stages into executions. In each stage, you can see more details on specific information regarding each execution.

![Image](http://learn.nextwork.org/intense_azure_festive_sow/uploads/aws-devops-codepipeline-updated_fbdetger)

---

## Source Stage

In the Source stage, the default branch tells CodePipeline which branch to monitor when looking for updates to the codebase.

The source stage is also where you enable webhook events, which check for specific conditions like Git push or pull request to determine when to begin the pipeline.

![Image](http://learn.nextwork.org/intense_azure_festive_sow/uploads/aws-devops-codepipeline-updated_sergt)

---

## Build Stage

The Build stage sets up a code artifact, which is a file containing information and resources related to the project. I configured CodePipeline to use the previous code artifacts when starting the pipeline. 

![Image](http://learn.nextwork.org/intense_azure_festive_sow/uploads/aws-devops-codepipeline-updated_j1k2l3m4)

---

## Deploy Stage

The Deploy stage is where CodePipeline will deploy the code to the production environment. I configured it to the CodeDeploy application and group made earlier in the project.

![Image](http://learn.nextwork.org/intense_azure_festive_sow/uploads/aws-devops-codepipeline-updated_m4n5o6p7)

---

## Success!

Since my CI/CD pipeline gets triggered by adding new code to my GitHub repository. I tested my pipeline by creating a new line in my web app source code and pushing it to GitHub.

The moment I pushed the code, the pipeline automatically began to run. The commit message under each stage reflects the operations that CodePipeline uses to run the pipeline.

Once my pipeline executed successfully, I checked the public IP address of the instance deployed through CodeDeploy and saw that the updated line was added to the web app.

![Image](http://learn.nextwork.org/intense_azure_festive_sow/uploads/aws-devops-codepipeline-updated_e1f2g3h4)

---

