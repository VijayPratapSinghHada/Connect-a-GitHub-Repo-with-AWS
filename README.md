<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Connect a GitHub Repo with AWS

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-devops-github)

**Author:** Vijay Pratap Singh Hada  
**Email:** vijaypratapsinghhada9@gmail.com

---

## Connect a GitHub Repo with AWS

![Image](http://learn.nextwork.org/blissful_yellow_calm_donkey/uploads/aws-devops-github_dd9d254e)

---

## Introducing Today's Project!

Today, I'll set up Git and GitHub and connect your web app project to a GitHub repo. Also make changes to your web app code and watch your GitHub repo update too. Also set up a README file for your repo.

### Key tools and concepts

Services I used were Amazon EC2 for cloud-based development, VSCode for coding, and GitHub for version control. Key concepts I learned include Git for tracking changes, repositories (both local and remote) for storing code, and the importance of a README file for project documentation. I also learned about secure authentication with GitHub tokens.

### Project reflection

This project took me approximately 3 hours and 30 minutes to complete.



I did this project today to learn how to connect a GitHub repository with AWS, setting up essential version control for a web application. It was a practical step in understanding CI/CD pipelines and cloud-based development.

I did this project today to learn how to connect a GitHub repository with AWS, setting up essential version control for a web application. It was a practical step in understanding CI/CD pipelines and cloud-based development.



---

## Git and GitHub

Git is a system that keeps track of changes in code, acting like a version history for my projects. I installed Git by running two commands in my EC2 instance's terminal: `sudo dnf update -y` to update existing software, and then `sudo dnf install git -y` to install Git itself. This process ensures I have the latest tools and can easily manage my code changes for development.

GitHub is an online platform where developers can store and share their code and projects. I'm using GitHub in this project to easily view and manage changes to my code in a user-friendly way, and to store my project files online, which makes collaboration and access from anywhere much simpler.

![Image](http://learn.nextwork.org/blissful_yellow_calm_donkey/uploads/aws-devops-github_efaadbf7)

---

## My local repository

A Git repository is essentially a special folder that holds all the files for a project, along with a complete record of every change ever made to them. It's like a time machine for your code, allowing you to track and manage different versions of your project.

`git init` is a command that creates a new, empty Git repository or reinitializes an existing one. I ran `git init` in the `nextwork-web-project` folder on my EC2 instance, which tells Git to start tracking changes within that directory for version control.

After running `git init`, the response from the terminal was a suggestion about naming the main branch, often `master`. A branch in Git is like creating a separate version or parallel timeline of your project. It allows you to work on new features or fix bugs without affecting the main, stable version of your code, making it safe to experiment and develop new ideas.

![Image](http://learn.nextwork.org/blissful_yellow_calm_donkey/uploads/aws-devops-github_7bf21bae)

---

## To push local changes to GitHub, I ran three commands

### git add

The first command I ran was `git add .`. This command tells Git to include all the changes I've made in my project for the next commit. A staging area is like a temporary holding place where Git collects all your modified files before you permanently save them as a new version in your project's history. It allows you to review and select exactly which changes you want to include in your next commit.

### git commit

The second command I ran was `git commit -m "Updated index.jsp with new content"`. This command takes all the changes I've prepared in the staging area and saves them as a permanent snapshot in my project's history. Using `-m` means I'm adding a short, descriptive message to this saved version, explaining what changes were made. This makes it easy to understand the purpose of each saved update later on.

### git push

The third command I ran was `git push -u origin master`. This command sends my saved changes (commits) from my local computer to the GitHub repository, making them available online. Using `-u` means I'm setting up a default connection, so from now on, when I want to push changes, I can just type `git push` without needing to specify the destination every time.

---

## Authentication

When I commit changes to GitHub, Git asks for my credentials because it needs to verify my identity and ensure I have permission to update the repository. This is a security measure to prevent unauthorized changes and protect the project's code.

### Local Git identity

Git needs my name and email because it uses this information to identify who made each change (commit) in the project's history. This helps in tracking authorship for every update, making it clear who is responsible for specific modifications to the code. If not manually set, Git might use a generic system username, which isn't ideal for tracking contributions accurately.

Running `git log` showed me the history of all the commits made to the repository. This includes details like the commit message, the author's name, and the date and time of each commit, giving a clear timeline of the project's development.

![Image](http://learn.nextwork.org/blissful_yellow_calm_donkey/uploads/aws-devops-github_9a27ee3b)

---

## GitHub tokens

GitHub authentication failed when I entered my password because GitHub no longer allows using your account password for security reasons. Instead, it requires a more secure method like a personal access token to log in and interact with your repositories.

A GitHub token is a unique, randomly generated string of characters that acts like a secure password for accessing your GitHub account and repositories. I'm using one in this project because GitHub no longer supports password authentication due to security risks. The token provides a more secure way to log in and interact with my repositories, ensuring that my actions are authorized without exposing my actual password.

I could set up a GitHub token by navigating to my GitHub profile settings, then to "Developer settings," and finally "Personal access tokens." From there, I chose to generate a new classic token, gave it a descriptive note and set its expiration to 7 days. Crucially, I selected the "repo" scope to grant it the necessary permissions for interacting with my repositories, and then generated the token. After generation, I copied the token, as it wouldn't be visible again.

![Image](http://learn.nextwork.org/blissful_yellow_calm_donkey/uploads/aws-devops-github_fa11169d)

---

## Making changes again

I wanted to see Git working in action, so I updated the `index.jsp` file in my `nextwork-web-project`. I couldn't see the changes in my GitHub repo initially because saving changes in VSCode only updates my local repository. For the changes to appear on GitHub, I needed to explicitly use Git commands to stage, commit, and then push them from my local repo to the cloud-based GitHub repository.

I finally saw the changes in my GitHub repo after running the `git add .`, `git commit -m "Add new line to index.jsp"`, and `git push` commands in my VSCode terminal. This sequence staged my modifications, saved them to my local Git history, and then uploaded them to the GitHub repository. I also had to provide my GitHub username and the personal access token for authentication when prompted during the `git push` operation, and then refresh the GitHub webpage to view the updated `index.jsp` file.

![Image](http://learn.nextwork.org/blissful_yellow_calm_donkey/uploads/aws-devops-github_6becb2bc)

---

## Setting up a READMe file

As a finishing touch to my GitHub repository, I added a README file, which is a document that introduces and explains the project, detailing what it does, how to set it up, and how to use it. I added a README file by using the `touch README.md` command in my terminal, which created a new, blank file named `README.md`.

My README is written in Markdown because it's a simple text language that lets me easily format documents for webpages, making them look clean and readable without complex software. Special characters can help you format text in Markdown, such as `#` for different heading sizes, `**text**` to make text bold, `*text*` for italics, and `[link text](URL)` to create hyperlinks. These symbols allow me to structure and style the content effectively.

My README file has 6 sections that outline the project's details, starting with an "Introduction" explaining its purpose and my personal goals. The "Technologies" section lists the tools used, like Amazon EC2, VS Code, and GitHub, along with potential future AWS CI/CD services. "Setup" provides instructions for getting the project running locally, while "Contact" offers information for reaching me. Finally, the "Conclusion" expresses gratitude and mentions the NextWork guide. There's also a "Table of Contents" for easy navigation.

![Image](http://learn.nextwork.org/blissful_yellow_calm_donkey/uploads/aws-devops-github_c94976902)

---

---
