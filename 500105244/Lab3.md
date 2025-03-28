# DevOps Lab 3

## Name: Deepanshu Kumar Jindal  
**SAP ID:** 500105244  
**Roll Number:** R2142220475  
**Batch:** Full Stack AI B1 Hons  

## GIT BASICS

Git is a distributed version control system that helps developers manage code efficiently. It allows multiple users to work on a project simultaneously, track changes, and collaborate effectively. Git can be used over SSH and HTTP to interact with remote repositories securely.

#### Using SSH and HTTP for Git

##### SSH Key Setup
Using SSH, we need both public and private keys to clone repositories securely. SSH provides encrypted communication and authentication.

#### 1. Generating SSH Key
Run the following command to generate an SSH key:
```sh
ssh-keygen -t ed25519 -C "deepanshujindal190@gmail.com"
```

Verify if the key is generated at the default location:
```sh
ls ~/.ssh
```

#### 2. Reading the SSH Key
To read the key, use:
```sh
cat ~/.ssh/id_ed25519.pub
```

#### 3. Adding SSH Key to SSH-Agent
```sh
ssh-add ~/.ssh/id_ed25519
```

#### 4. Adding the Key to GitHub
- Go to GitHub Settings → SSH and GPG keys → Add a new key
- Copy the contents of `id_ed25519.pub` and paste it

Using SSH authentication ensures a secure connection and eliminates the need to enter credentials repeatedly.

### Cloning Repository Using SSH
```sh
git clone git@github.com:deepanshujindal/DevOpsLab3.git
```

---

### Cloning Repository Using HTTP
```sh
git clone https://github.com/deepanshujindal/DevOpsLab3.git
```

If authentication is required, Git will prompt for your credentials. Using HTTP requires entering the username and password for authentication, making SSH a more convenient choice for frequent use.

---

## Git Workflow

A Git workflow is a recommended way of using Git to manage changes effectively. It helps teams collaborate efficiently and maintain a structured development process.

### 1. Initialize and Clone Repository
```sh
git init
git clone https://github.com/Deepanshu907/devopslab1.git
```
This step sets up a local Git repository or copies an existing one from a remote server.

### 2. Working on a Repository
1. Navigate to the repository directory.
2. Make the necessary modifications to the files.
3. Add changes to the staging area:
   ```sh
   git add .
   ```
4. Commit changes with a descriptive message:
   ```sh
   git commit -m "new files added"
   ```
   Always write meaningful commit messages to track changes effectively.

### 3. Resolving Merge Conflicts
If multiple developers are working on the same repository, conflicts may arise. To handle them:
```sh
git pull origin main
git merge
```
Then push the changes:
```sh
git push origin main
```
If conflicts occur, Git will prompt to resolve them manually before proceeding.

### 4. Checking Git Status
To check the current state of the repository, use:
```sh
git status
```
This command provides information about untracked files, staged changes, and branches.

### 5. Viewing Commit History
To view the commit history and track changes:
```sh
git log
```
For a more compact history:
```sh
git log --oneline 
```

---

## VIM Commands (for Git commit messages)

Vim is a text editor used to write Git commit messages. Below are some essential Vim commands:
```bash
1. i → Insert mode (start editing text)
2. esc → Exit insert mode
3. q → Quit Vim
4. shift + v → Visual mode (to select text)
   - y → Copy selected text
   - p → Paste copied text
5. ‘H’, ‘J’, ‘K’, ‘L’ → Move left, down, up, right
6. dd → Delete the current line
7. u → Undo the last action
8. /something → Search for 'something' in the file
9. esc + :wq → Save and exit Vim
```


---

## Best Practices for Using Git

- **Commit frequently:** Small, frequent commits help track changes and roll back easily.
- **Use meaningful commit messages:** Describe what was changed and why.
- **Pull before pushing:** Always pull the latest changes before pushing to avoid conflicts.
- **Use branches:** Work on features in separate branches and merge them when complete.
- **Avoid committing sensitive data:** Never commit passwords, API keys, or configuration files with credentials.
- **Review changes before committing:** Use `git diff` to check modifications before adding them.

---
