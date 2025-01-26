# Git Commands Cheat Sheet

## **1. Setting Up a Git Repository**
### **Initialize a New Repository**
```sh
git init
```

### **Clone an Existing Repository**
```sh
git clone <repository_url>
```
Example:
```sh
git clone https://github.com/username/repository.git
```

### **Check Repository Status**
```sh
git status
```

## **2. Configuring Git**
### **Set Username and Email**
```sh
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

### **Check Git Configurations**
```sh
git config --list
```

## **3. Working with Files**
### **Add Files to Staging Area**
```sh
git add <file>
```
Example:
```sh
git add mathsymbols.md
```

### **Add All Modified Files**
```sh
git add .
```

### **Commit Staged Changes**
```sh
git commit -m "Commit message"
```
Example:
```sh
git commit -m "Updated math symbols"
```

## **4. Connecting to a Remote Repository**
### **Add a Remote Repository**
```sh
git remote add origin <repository_url>
```
Example:
```sh
git remote add origin https://github.com/username/repository.git
```

### **Check Remote Repositories**
```sh
git remote -v
```

## **5. Pushing Changes to GitHub**
### **Push a Branch to Remote Repository**
```sh
git push -u origin main
```

### **Push All Local Changes**
```sh
git push
```

## **6. Pulling Updates from GitHub**
### **Fetch and Merge Remote Changes**
```sh
git pull origin main
```

### **Fetch Remote Changes Without Merging**
```sh
git fetch
```

## **7. Branching in Git**
### **Create a New Branch**
```sh
git branch <branch-name>
```

### **Switch to a Branch**
```sh
git checkout <branch-name>
```

### **Create and Switch to a New Branch**
```sh
git checkout -b <branch-name>
```

### **Push a New Branch to GitHub**
```sh
git push -u origin <branch-name>
```

## **8. Merging and Resolving Conflicts**
### **Merge a Branch into Current Branch**
```sh
git merge <branch-name>
```

### **Resolve Merge Conflicts**
- Open conflicting files and edit manually.
- After resolving conflicts, stage the changes:
  ```sh
  git add .
  ```
- Commit the merge:
  ```sh
  git commit -m "Resolved merge conflicts"
  ```

## **9. Undoing Changes**
### **Undo Last Commit (Keep Changes)**
```sh
git reset --soft HEAD~1
```

### **Undo Last Commit (Remove Changes)**
```sh
git reset --hard HEAD~1
```

### **Remove a File from Staging**
```sh
git restore --staged <file>
```

### **Discard Local Changes in a File**
```sh
git checkout -- <file>
```

## **10. Git Ignore Files**
### **Create a .gitignore File**
```sh
touch .gitignore
```

### **Example .gitignore Content**
```
.DS_Store
*.log
node_modules/
*.pyc
```

## **11. Resolving Authentication Issues with GitHub**
### **Issue: Password Authentication Failed (Due to 2FA)**
If you have **Two-Factor Authentication (2FA) enabled**, GitHub no longer allows password authentication for Git over HTTPS. Instead, you must use a **Personal Access Token (PAT)**.

### **Solution: Generate and Use a Personal Access Token (PAT)**
#### **Step 1: Generate a Personal Access Token (PAT)**
1. Go to **GitHub → Settings**: [GitHub Settings](https://github.com/settings/profile)
2. Navigate to **Developer settings > Personal Access Tokens**.
3. Click **Generate new token (fine-grained)**.
4. Set an **Expiration date** (e.g., No expiration or 30 days).
5. Under **Scopes**, select:
   - `repo` (Full access)
   - `workflow` (If using GitHub Actions)
   - `write:packages` (If working with packages)
6. Click **Generate Token**.
7. **Copy the token** (you won’t be able to see it again!).

#### **Step 2: Use the Token Instead of Your Password**
Replace your GitHub password with the **Personal Access Token** when prompted.
Alternatively, update your Git remote URL to include the token:
```sh
git remote set-url origin https://<TOKEN>@github.com/username/repository.git
```
Example:
```sh
git remote set-url origin https://ghp_xxxxxxxxxxxxxxxxx@github.com/username/repository.git
```
Then push your changes:
```sh
git push origin main
```

---
## **12. SSH Authentication for GitHub (Recommended)**
### **Generate an SSH Key**
```sh
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

### **Add SSH Key to GitHub**
1. Copy the SSH key:
   ```sh
   cat ~/.ssh/id_rsa.pub
   ```
2. Go to GitHub → **Settings** → **SSH Keys** → **Add Key**
3. Paste and save the key.

### **Use SSH Instead of HTTPS**
```sh
git remote set-url origin git@github.com:username/repository.git
```

### **Test SSH Connection**
```sh
ssh -T git@github.com
```

---
## This cheat sheet covers the most common Git commands for setting up repositories, committing changes, pushing to GitHub, and resolving authentication issues. 🎯
