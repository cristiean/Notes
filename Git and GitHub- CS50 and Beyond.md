# Git and GitHub - CS50 and Beyond

## Version control
- **Keep track** of all the **changes** made to the code
- **Synchronise code** between different people
    - Give you and your partner the same file,
    - Synchronise the updates,
    - Everyone works on the same version
- **Test changes** without losing the original copy
    - E.g. adding something new to the code (Branch off)
    - Then, if it works, Merge it back in
    - Revert back to old code. Return to a previous version of the code

## GitHub
- **Holds Git Repositories** (a folder in which code is stored)
- **git clone <url>**
	- Locates the repository at <url>
    - Makes a copy of it on the local machine
- **git add**
    - This is a file I want to include in my next commit. (Add file to the staging area)
- **git commit  -m “message”**
    - “this is a version of the repository that I’m saving”
- **git push**
    - Take all the changes I’ve made, and push them onto the server
- **git pull**
    - Takes changes from the server and put them on the local machine
- Merge conflicts:
    - Two people try to push the same file with different (conflicting) changes.
    - I try to pull some files off the server that have been modified, compared to the files on my machine

~~~python
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
~~~

- **git reset**
    - Go back to a previous version
    - **git reset --hard** \<commit>
    - **git reset --hard origin-master** (to a branch)
- Branching
    - When you want to work on a new feature, branch off from master. Master branch and feature branch.
    - The HEAD is by default on the master branch, but it can be moved on to different branches
    - Merge the feature branch with the bug fix version on the master branch.
    - **git branch**
    - **git checkout branch_name**
        - Go to some branch
        - **git checkout -b** \<new\_branch_name>
    - **git merge**
- Pull request (GitHub feature)
























