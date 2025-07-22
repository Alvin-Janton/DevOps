
# Connect a GitHub Repo with AWS


---

## Introducing Today's Project!

Today I am going to create a git hub repository and connect it to my web app to serve as a hub for my code.

### Key tools and concepts

Services I used were Git, and GitHub. Key concepts I learned were how to install Git, how create a local git repository, how to connect a local repository to a public repository on GitHub, and how to view and add changes to a repository.

### Project reflection

This project took me approximately one hour to complete. The project was not challenging in any way. It was most rewarding to see my GitHub repo change at the end of the project.

I did this project today so I can learn more about the cloud and cloud security. This project has met my goals in teaching me more about Git and how to use it.

This project is part two of a series of DevOps projects where I'm building a CI/CD pipeline!

---

## Git and GitHub

Git is a version control software that allows me to track the changes that I make to my code. I installed git using the commands

<pre>
sudo dnf update -y
sudo dnf install git -y
</pre>



GitHub is a storage space that will keep all the different version of my code that are captured by Git. I'm using GitHub to keep track of changes and updates made to my web app.

![Image](http://learn.nextwork.org/intense_azure_festive_sow/uploads/aws-devops-github_efaadbf7)

---

## My local repository

A Git repository is a folder that stores all of the files and code history related to a project.

git init is a command that creates a local git repository on your host system. I ran git init in my EC2 web app terminal.

After running git init, the response from the terminal was Initialized empty Git repository in /home/ec2-user/nextwork-web-project/.git/.
A branch in git is a snapshot of your current code that you can merge with main branch.

![Image](http://learn.nextwork.org/intense_azure_festive_sow/uploads/aws-devops-github_7bf21bae)

---

## To push local changes to GitHub, I ran three commands

### git add

The first command I ran was git add, this command connects the GitHub repo in the local host to the one on the GitHub website.

### git commit

The second command I used was git commit -m "Updated index.jsp with new content". This command will show all the changes made to the codebase before pushing them to GitHub.

### git push

The third command I ran was git push. This command updates the index.jsp file in the GitHub repository.


---

## Authentication

When I commit changes to GitHub, Git asks for my credentials because Git wants to make sure that I have authorization to make changes to the codebase.

### Local Git identity

Git needs my name and email because it wants to identify who is the author behind the changes I make to the codebase.

Running git log showed me that Git does not know who the author is and just used the host computer name as a placeholder.

![Image](http://learn.nextwork.org/intense_azure_festive_sow/uploads/aws-devops-github_9a27ee3b)

---

## GitHub tokens

GitHub authentication failed when I entered my password because, GitHub no longer accepts passwords as valid forms of identification and now they use tokens.

A GitHub token is a random set of characters, I'm using one in this project because it is necessary to connect accounts using https.

I could set up a GitHub token by going to my GitHub account, clicking on settings, going to developer settings, going to token, and generating a classic token.

![Image](http://learn.nextwork.org/intense_azure_festive_sow/uploads/aws-devops-github_fa11169d)

---

## Making changes again

I wanted to see Git working in action, so I made small change to the index.jsp file added it using git add . I couldn't see any changes in my GitHub repo intially because I hadn't commited the change.

I finally saw the changes after in my GitHub repo after I used the git push command to push my code to the GitHub repo.

![Image](http://learn.nextwork.org/intense_azure_festive_sow/uploads/aws-devops-github_6becb2bc)

---
