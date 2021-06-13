# Git and GitHub - CS50 and Beyond

## Version control

- **Keeps track** of all the **changes** made to the code
- **Synchronises code** between different people
  - Gives you and your partner the same file
  - Synchronises the updates
  - Lets everyone work on the same version
- **Test changes** without losing the original copy (e.g. by adding something new to the code- **branching off**)
  - Then, if it works, **merge** the changes back in
  - Return to a previous version of the code

## GitHub

- **Holds Git Repositories** (repository- a folder in which code is stored)
- **`git clone <url>`** locates the repository at \<url> and makes a copy of it on the local machine
- **`git add`** “this is a file I want to include in my next commit.” (**add file to the staging area**)
- **`git commit  -m “message”`** “this is a version of the repository that I’m saving”
- **`git push`** take all the changes I’ve made, and push them onto the server
- **`git pull`** takes changes from the server and put them on the local machine
- **Merge conflicts**:
  - Two people try to push the same file with different (conflicting) changes.
  - I try to pull some files off the server that have been modified, compared to the files on my machine

```python
# This needs manual resolve. 
a = 1
<<<<< HEAD
b = 2
=====    
b = 0
>>>>> 5234513613615151341241
c = 3
d = 4
e = 5
```

- **`git reset`**
  - Go back to a previous version
  - **`git reset --hard <commit>`**
  - **`git reset --hard origin-master`** (to a branch)
- Branching
  - When you want to work on a new feature, branch off from master. Master branch and feature branch.
  - The HEAD is by default on the master branch, but it can be moved on to different branches
  - Merge the feature branch with the bug fix version on the master branch.
  - **`git branch`**
  - **`git checkout branch_name`** go to some branch
  - **`git checkout -b <new_branch_name>`**
  - **`git merge`**
- Pull request (GitHub feature)
