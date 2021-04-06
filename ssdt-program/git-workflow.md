---
title: Git Workflow
description: 
published: true
date: 2021-04-06T15:55:15.784Z
tags: 
---

# Git Workflow

**Creating a new branch:**

The first three commands are to make sure your branch will be up to date with the development branch. 
```
1. git fetch 

2. git checkout development 

3. git pull origin developement 

4. git checkout -b BRANCH_NAME
```

**Add, Commit, and Push:**
```
1. git status 

2. git add CHANGED_FILE_DIRECTORY_NAME

3. git commit -m "USEFUL_MESSAGE_DESCRIBING_THE_CHANGES"

4. git push origin BRANCH_NAME
```
*Tip: In step 2, instead of adding each file separately you can do the following. It means add all ( * ) the directories that start with (app)*
```
git add app*
```

**Steps before creating a Pull Request:**
Make sure your branch is up to date with development 
```
1. git checkout development 

2. git pull origin development 

3. git checkout BRANCH_NAME

4. git merge development
```

**Fix Merge Conflicts:**
If there are merge conflicts between your branch and development, make sure to fix those. It is important to ask other developers about which code to keep. We do not want to delete other people's code. 
Fixing merge conflict does not only speed up the review process, but it makes sure your code works with the existing code in the development. 

**Create Pull Request:**
Finally, go to Bitbucket and [create a PR](/ssdt-program/pull-request), tagging the reviewers and leaving useful and clear comments for easy review and merging. 

