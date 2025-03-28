# DevOps Lab 1: Introduction to CI/CD

## Name: Deepanshu Kumar Jindal  
**SAP ID:** 500105244  
**Roll Number:** R2142220475  
**Batch:** Full Stack AI B1 Hons  

## Overview
Git is a distributed version control system that helps developers track changes in their code efficiently. GitHub is a cloud-based platform that provides Git repository hosting with additional collaboration tools.

## How Git Works
1. **Local Repository**: Developers maintain a local copy of the repository on their machine.
2. **Staging Area**: Changes are added to the staging area before committing.
3. **Commits**: Snapshots of changes are saved in the local repository.
4. **Remote Repository**: The local repository can be synchronized with a remote repository on GitHub.
5. **Collaboration**: Multiple developers can work on the same project using branches, pull requests, and merges.

## Basic Git Commands

### 1. Git Configuration
```sh
# Set global username and email
git config --global user.name "Deepanshu Kumar Jindal"
git config --global user.email "deepanshujindal190@gmail.com"
```

### 2. Initialize a Repository
```sh
git init
```

### 3. Clone a Repository
```sh
# Clone an existing repository from GitHub
git clone https://github.com/Deepanshu907/devopslab1.git
```

### 4. Check Repository Status
```sh
git status
```

### 5. Add Files to Staging Area
```sh
# Add all changes
git add .
```

### 6. Commit Changes
```sh
# Commit changes with a message
git commit -m "new files added"
```

### 7. Push Changes to Remote Repository
```sh
git push origin main
```

### 8. Pull Changes from Remote Repository
```sh
git pull origin main
```

### 9. Create a New Branch
```sh
git branch feature-branch
```

### 10. Switch to Another Branch
```sh
git checkout feature-branch
```

### 11. Merge Branches
```sh
# Merge a branch into the current branch
git merge feature-branch
```



### 12. Create a Pull Request on GitHub
1. Push your changes to the remote repository.
2. Navigate to your repository on GitHub.
3. Click **Compare & pull request**.
4. Add a description and click **Create pull request**.

**Now the repository is ready for collaboration!**
