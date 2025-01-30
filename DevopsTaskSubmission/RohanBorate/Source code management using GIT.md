# Source code management using GIT



- GIT installation on  AWS EC2 server
- created an ec2 instance named as (dev_env)


![Screenshot 2025-01-29 185009.png](https://eraser.imgix.net/workspaces/wp3r8QsJYwlM1bMFjnCH/yuIy5hbLwHZ10ovGIULZ9qCXT8E3/OGxvhxjDitCL2HourBYnN.png?ixlib=js-3.7.0 "Screenshot 2025-01-29 185009.png")



- connect to that ec2 instance and install git on that , as we are using AMAZON linux , we don't have default installation of git like ubuntu
- +[﻿git-scm.com/downloads/linux](https://git-scm.com/downloads/linux) 
- git install command for the AWS linux
```
﻿yum install git  
```


![image.png](https://eraser.imgix.net/workspaces/wp3r8QsJYwlM1bMFjnCH/yuIy5hbLwHZ10ovGIULZ9qCXT8E3/LnKBfqnRQV0EO__YttcW_.png?ixlib=js-3.7.0 "image.png")



- check git is installed or not 
```
git
```
```
git --version
```


![image.png](https://eraser.imgix.net/workspaces/wp3r8QsJYwlM1bMFjnCH/yuIy5hbLwHZ10ovGIULZ9qCXT8E3/cBxhY8v4iVCw6BCtfixF4.png?ixlib=js-3.7.0 "image.png")

- initialize a git repository 
- created a directory inside home directory of the ec2 user named as gitrepo
- command to initialize the git repository (empty git repository will be created)
```
git init
```
![image.png](https://eraser.imgix.net/workspaces/wp3r8QsJYwlM1bMFjnCH/yuIy5hbLwHZ10ovGIULZ9qCXT8E3/gO_wT7mA9QD-nGKSzKtrx.png?ixlib=js-3.7.0 "image.png")

- git repo is initialized , .git folder is created 
- `.git`  folder is a hidden directory inside a Git repository that contains all the information necessary to track changes, manage branches, and store commit history. It is created when you run `git init`  or when you clone an existing repository.
- files and folders inside the .git directory
    - **HEAD** – A reference to the current branch
    - .**config** – Repository-specific configuration settings
    - .**hooks/** – Scripts that run on Git events (e.g., pre-commit, post-merge)
    - .**refs/** – References to commits, including branches (`refs/heads/`  ), tags (`refs/tags/`  ), and remotes (`refs/remotes/`  )
    - .**objects/** – Stores all commits, trees, and blobs (actual content of files)
    - .**logs/** – History of changes to branches and HEAD
    - .**index** – Tracks the staging area (what will be committed)
    - .**info/** – Additional repository metadata.
- **Warning**: Deleting the `.git`  folder will remove version control from the project, making it untracked.
- created one txt file named test.txt, to test git features (commands)
![image.png](https://eraser.imgix.net/workspaces/wp3r8QsJYwlM1bMFjnCH/yuIy5hbLwHZ10ovGIULZ9qCXT8E3/8PJLgnCByy3Ooi-w4nd_l.png?ixlib=js-3.7.0 "image.png")

- new txt file is created in git repository.
- now check the status of the git repo with below command
```
git status
```
- `git status` command is used to display the current state of your working directory and staging area. It helps you see which files have been modified, staged, or untracked before committing changes.
- it is showing our untracked changes (.txt) file which we have created
![image.png](https://eraser.imgix.net/workspaces/wp3r8QsJYwlM1bMFjnCH/yuIy5hbLwHZ10ovGIULZ9qCXT8E3/npNYj_sKGRcC-vfFCOciq.png?ixlib=js-3.7.0 "image.png")

- in above snippet seen that our changes are untracked ,so to track that untracked changes use below git command
```
git add <untrackedfile>
```
```
git add test.txt
```
- When you run `git add <file>` , the file moves from the **working directory to the staging area**.
- This means Git is now tracking the changes but hasn't committed them yet.
- These changes will be listed as **Changes to be committed** in `git status` 


![image.png](https://eraser.imgix.net/workspaces/wp3r8QsJYwlM1bMFjnCH/yuIy5hbLwHZ10ovGIULZ9qCXT8E3/f0aSd0J0OiQfAcRbU0GUT.png?ixlib=js-3.7.0 "image.png")

- Then we have to commit our changes to a git repository.
- use below git command to commit changes
```
git commit -m "commit description"
```
- `git commit`  – Records changes from the staging area into the repository.
- `-m "message"`   – Adds a commit message that describes the changes.
- Once you run `git commit -m "message"` , the changes are permanently stored in the Git database.
- The file is now fully tracked and part of the repository's history.


![image.png](https://eraser.imgix.net/workspaces/wp3r8QsJYwlM1bMFjnCH/yuIy5hbLwHZ10ovGIULZ9qCXT8E3/8yLsvywCutIyLiKKYIth_.png?ixlib=js-3.7.0 "image.png")

- Note  --> 
- we can also use `git commit `command without` -m ` .
- this is used to write detailed commit message like below
![image.png](https://eraser.imgix.net/workspaces/wp3r8QsJYwlM1bMFjnCH/yuIy5hbLwHZ10ovGIULZ9qCXT8E3/arrR32aa1MN7oxsbHz_V_.png?ixlib=js-3.7.0 "image.png")





