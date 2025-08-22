---
Title: CI CD Github
Status: 
marker:
  - "[[github]]"
  - "[[Deployment]]"
tags:
  - Project
Date: 2024.12.25
Time: 21:58
---
# The Approach I took to learn this.
I Have a collection of notes in an application called Obsidian. I had to publish it so that I don't have to be bothered by 10 people asking me to pls send me the notes every exam season. So I automated this process using CI/CD.

## Prerequisites
( Or what I had while learning u don't need to get all this done imho just read the note )
- collection of notes 
- A wonderful opensource project called [Quartz](https://quartz.jzhao.xyz/)
- [[VPS]] From [Hostinger](https://www.hostinger.in/).
- Skills with deploying next.js Projects. 
- Skills with bash/any cli & GIT.
## What's CI/CD??
Continuous Integration and Continuous Deployment is a practice that has been established so developers don't have to log into their servers every time a minor change is pushed on to their code repository.

## Why do I need it?
I make a lot of changes in my notes regularly thus calling for the need of a continuous deployment / integration. Simply saving the files and pushing it to git with a simple key stroke is updating the notes in my page for me.

## Pushing all your notes to a repository manager
For me I use Github since it has Actions. Push all your notes to a Github repository.  Now at this stage you have a backup of your files in a repository. This means u can retrieve it from your servers easily. 

## Okay we have a repository what now?
We are consistent with the database on the repo but we still have to set up a deployment at the servers. For that we use Github Actions.
#### What/Why is Github Actions
Each Push to the repo means a new action has to be run on the server. This enables very feature is designed for that.
With each push, you can configure GitHub to SSH into your server and execute a set of commands.
#### Why is this free?
Github has a open source favouring policy, implying that if your notes are open source you basically have a good amount of actions with you that refreshes periodically. 

## Flow Diagram
![[IMG-20250730000301034.png]]
w

---

### **1. Name of the Workflow**
```yaml
name: Pull on GitHub Repo Update
```
- This is the name of the workflow. It describes what this workflow does: pulling and updating the repository when changes are pushed.

---

### **2. Triggering Event**
```yaml
on:
  push:
    branches:
      - public
```
- **`on`** specifies the event that triggers this workflow.
- It runs when there’s a `push` event to the `public` branch of the GitHub repository.

---

### **3. Job Definition**
```yaml
jobs:
  deploy:
    runs-on: ubuntu-latest
```
- A single job is defined under `jobs`, named `deploy`.
- **`runs-on: ubuntu-latest`** specifies the operating system for the runner (Ubuntu).

---

### **4. Steps in the Job**

#### **Step 1: Checkout Code**
```yaml
    - name: Checkout code
      uses: actions/checkout@v3
```
- This step uses the `actions/checkout` action to fetch the latest version of the repository’s code.  
- It allows subsequent steps to access the repository files.

---

#### **Step 2: Deploy to Server via SSH**
```yaml
    - name: Deploy to Server via SSH
      uses: appleboy/ssh-action@v0.1.9
```
- This step uses the `appleboy/ssh-action` to execute commands on a remote server via SSH.

---

##### **Substeps in the SSH Deployment Script**

1. **Echo SSH Connection**
   ```bash
   echo "SSH Connection Successful"
   ```
   - Confirms that the SSH connection was successful.

2. **Install NVM and Node.js**
   ```bash
   curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash
   export NVM_DIR="$HOME/.nvm"
   [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"
   nvm install 20
   nvm use 20
   ```
   - Installs **Node Version Manager (NVM)** to manage Node.js versions.
   - Installs and sets the Node.js version to 20.
   - Ensures compatibility with Quartz, which requires Node.js for building.

3. **Verify Node.js and npm Versions**
   ```bash
   node -v
   npm -v
   ```
   - Prints the installed versions of Node.js and npm to verify installation.

4. **Pull Updates from GitHub Repository**
   ```bash
   cd /root/notes/Obsidian-Notes-Public
   git pull origin public
   ```
   - Navigates to the repository directory on the server.
   - Pulls the latest changes from the `public` branch of the GitHub repository.

5. **Copy Files to Quartz Content Directory**
   ```bash
   cp -r /root/notes/Obsidian-Notes-Public/* /root/notes/quartz/content/
   ```
   - Copies updated files from the repository into the `quartz/content/` directory.

6. **Build Quartz**
   ```bash
   cd /root/notes/quartz/
   npx quartz build
   ```
   - Navigates to the Quartz directory.
   - Runs the `npx quartz build` command to generate the static site.

7. **Deploy Quartz Build to Web Server**
   ```bash
   cp -r /root/notes/quartz/public/* /var/www/quartz/public/
   ```
   - Copies the generated Quartz site (from `quartz/public/`) to the web server’s hosting directory (`/var/www/quartz/public/`).

---

### **Summary**
- The workflow automates the process of pulling updates from the GitHub repository, setting up the environment, building the Quartz static site, and deploying it to a web server. 
- By combining GitHub Actions with SSH, it ensures that the server always hosts the latest content.>)

###### Information
- date: 2024.12.25
- time: 21:58