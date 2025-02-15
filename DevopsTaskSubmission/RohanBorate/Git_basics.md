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

---

## Git undo and reset commands
### Undo changes in the working directory     (Before Staging with `git add`)
```
git checkout -- <file>
```
```
git restore --<file>
```
- Before staging with git add
- use when you have made changes in file but haven't staged it (git add) and want to undo that changes.
- in below snippet we have made changes in out test.txt file, add 'VERSION1'.
- then check with `﻿get status` to get untracked files, here we can see test file .
- but i want to revert these changes in txt file so i used `﻿git checkout -- <filename> ` or we can use `﻿``git restore --<file>`command to undo that changes.
- after using this command changes are reverted.
![image.png](https://eraser.imgix.net/workspaces/wp3r8QsJYwlM1bMFjnCH/yuIy5hbLwHZ10ovGIULZ9qCXT8E3/EBSj-b00_aN-jFosNJ9Yv.png?ixlib=js-3.7.0 "image.png")

- with `﻿git checkout --<file>` 
![image.png](https://eraser.imgix.net/workspaces/wp3r8QsJYwlM1bMFjnCH/yuIy5hbLwHZ10ovGIULZ9qCXT8E3/fYL_KJ1v8VYvry5fSxvZn.png?ixlib=js-3.7.0 "image.png")

- with `git restore --<file>` 
![image.png](https://eraser.imgix.net/workspaces/wp3r8QsJYwlM1bMFjnCH/yuIy5hbLwHZ10ovGIULZ9qCXT8E3/Z13oQ7CgH8YV4Ko3LcIh3.png?ixlib=js-3.7.0 "image.png")

- Note - Cannot undo changes after they have been staged or committed.


### Unstage a file  (After `git add` but Before `git commit`)
```
git reset HEAD <file>
```
- if you added a file in staging area but haven't committed yet.
- Moves file back to the working directory
- it does not delete actual changes in file 
- see below how `﻿git reset HEAD <file>`  actual works


![image.png](https://eraser.imgix.net/workspaces/wp3r8QsJYwlM1bMFjnCH/yuIy5hbLwHZ10ovGIULZ9qCXT8E3/_lNi-REcSuBoMswdleeY-.png?ixlib=js-3.7.0 "image.png")



### Undo the last commit (but keep changes) -- (After `git commit`) 
```
git reset --soft HEAD~1
```
- use when if you are committed a changes by mistake and want to undo that commit while keeping that changes 
- the last commit is undone but changes remain staged.
- does not delete anything
![image.png](https://eraser.imgix.net/workspaces/wp3r8QsJYwlM1bMFjnCH/yuIy5hbLwHZ10ovGIULZ9qCXT8E3/BSTjI-E2ByTek_YftPC9x.png?ixlib=js-3.7.0 "image.png")

![image.png](https://eraser.imgix.net/workspaces/wp3r8QsJYwlM1bMFjnCH/yuIy5hbLwHZ10ovGIULZ9qCXT8E3/5i0IkJgKWvwZY14VlvKDL.png?ixlib=js-3.7.0 "image.png")

- see here changes are reverted and it is showing changes to be committed.
- If you want to keep the changes but move them to the working directory (unstaged)
```
git reset --mixed HEAD~1
```


### **Undo the last commit and discard changes**
If you want to completely erase the last commit and discard change.

✅ Deletes the last commit and all associated changes.

❌ This action is irreversible unless backed up with `git reflog`.

```
git reset --hard HEAD~1
```
in below snippet we have create a test.txt and made two commits in  that file ,now we use `git reset --hard HEAD~1` to revert that commit and discard this changes



![image.png](https://eraser.imgix.net/workspaces/wp3r8QsJYwlM1bMFjnCH/yuIy5hbLwHZ10ovGIULZ9qCXT8E3/9a6B7WhaAdn9_DFbv2bzB.png?ixlib=js-3.7.0 "image.png")

add one other  commit 

![image.png](https://eraser.imgix.net/workspaces/wp3r8QsJYwlM1bMFjnCH/yuIy5hbLwHZ10ovGIULZ9qCXT8E3/2kac8EUhvez1UH-S1uDpn.png?ixlib=js-3.7.0 "image.png")



![image.png](https://eraser.imgix.net/workspaces/wp3r8QsJYwlM1bMFjnCH/yuIy5hbLwHZ10ovGIULZ9qCXT8E3/wwxNnRvmbKUvk5zZyy0co.png?ixlib=js-3.7.0 "image.png")



### Undo Multiple Commits
If you need to undo multiple commits (e.g., the last 3 commits):

```
git reset --hard HEAD~3
```
✅ Erases the last 3 commits and their changes.

❌ Use with caution; data will be lost.



### **Revert a Commit Without Losing Changes**
if you've already pushed a commit and want to undo it safely

```
git revert <commit_hash>
```
✅ Creates a new commit that undoes the changes of a previous commit.

✅ Safe for shared branches since history is not rewritten.



### **Delete All Uncommitted Changes**
If you want to reset everything (both staged and unstaged changes):

```
git reset --hard
```
✅ Restores your working directory to the last committed state.

❌ Cannot be undone unless you use `git reflog`.



### **Reset to a Specific Commit**
If you want to go back to a specific commit and discard later commits:

```
git reset --hard <commit_hash>
```
✅ Moves your branch to an older commit, deleting all later changes.

❌ Irreversible unless you have the commit hash saved.

If you want to reset to a specific commit but keep the changes unstaged:

```
git reset --mixed <commit_hash>
```
If you want to reset but keep the changes staged:

```
git reset --soft <commit_hash>
```


### **View and Restore Lost Commits (if Reset by Mistake)**


If you accidentally used `git reset --hard`, you can recover your commits using:

```
git reflog
```
This shows a history of all actions, including resets. You can restore a lost commit by checking out the commit hash:

```
git checkout <commit_hash>
```


![image.png](https://eraser.imgix.net/workspaces/wp3r8QsJYwlM1bMFjnCH/yuIy5hbLwHZ10ovGIULZ9qCXT8E3/M3XSKdQE-cmhv9TF1I0u7.png?ixlib=js-3.7.0 "image.png")



## **Summary Table**
| Command | Effect | Keeps Changes? |
| ----- | ----- | ----- |
| git checkout -- <file>  | Discards unstaged changes | ❌ No |
| git restore <file> | Discards unstaged changes | ❌ No |
| git reset HEAD <file> | Unstages a file | ✅ Yes |
| git reset --soft HEAD~1 | Undo commit, keep changes staged | ✅ Yes |
| git reset --mixed HEAD~1 | Undo commit, keep changes unstaged | ✅ Yes |
| git reset --hard HEAD~1 | Undo commit and discard changes | ❌ No |
| git revert <commit_hash> | Creates a new commit that undoes a previous commit | ✅ Yes |
| git reset --hard <commit_hash> | Reset branch to a specific commit, discard later changes | ❌ No |
| git reflog | View reset history and recover lost commits | ✅ Yes |


