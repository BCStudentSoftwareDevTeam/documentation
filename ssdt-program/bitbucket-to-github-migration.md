---
title: Bitbucket to Github Migration
description: 
published: true
date: 2021-05-04T17:19:53.541Z
tags: 
---

# Bitbuket to Github Migration Guide

### Migrating the Repository

1. Create an empty repository in github. Make sure there are no starter files such as README, and make sure the repository is public (we will need it to be public for the issue migration script).

2. Take a mirror clone of the bitbucket repository and push the mirror to github. 
```
1. git clone --mirror BITBUCKET_REPO_URL

2. cd BITBUCKET_REPO

3. git remote set-url --push origin GITHUB_REPO_URL

4. git push --mirror
```

3. If you want to sync any new changes you can run
```
git remote update
```

### Migrating Repository Issues

**Before starting this process, make sure the issue tracker in Bitbucket is set made public. The script does not work for private issue trackers.** 

The code we will be using for migrating repositories is an open-source [Bitbucket Issues Migration](https://github.com/jeffwidman/bitbucket-issue-migration) tool. For more details about the project you can checkout their repository. 

1. First, go to the [repository](https://github.com/jeffwidman/bitbucket-issue-migration) and clone the repo.

2. Follow these instructions before running the code. I have copy pasted the instructions from the repo, so you can see it there  as well. 
**You need to run this part only once, at the beginning, to set up your environment. You don't have to repeat it for every migration.** 
```
$ python3 -m venv ./py3
$ source ./py3/bin/activate
$ pip3 install -r requirements.pip
```

On Windows, use `.\py3\Scripts\activate.bat` instead of `source ./py3/bin/activate`. 

***Note**: If python 3 is the default language in your computer, you don't need to write `python3`. You can run the commands with `python` and `pip`.*

3. Now that you are all set up, it's time to migrate the issues by running the following commands. **You do need to repeat this process for every repository you want to migrate issues from.** 

	* First, change directory `cd bitbucket-issue-migration`
  	* Then, run the following commands
```
python migrate.py --bb-user bitbucket_username bitbucket_repo github_repo github_username
```

You will need to speficy `--map-user user_mapping_file.txt` at the beginning of the command, if you want to map users bitbucket usernames to their github usernames, and to make sure issue assignees are transferred. 

Therefore, the command will look like this: 
```
python migrate.py --map-user users_mapping_file.txt --bb-user bitbucket_username bitbucket_repo github_repo github_username
```
**Important Note: After running the command you will be prompted to write your bitbucket and github passwords. 
You can write your bibucket password like you would in Mobaxterm. However, for github password you need to [generate a token](https://docs.github.com/en/github/authenticating-to-github/creating-a-personal-access-token). You might have to manually type in the token every time you are asked for the password. In my case, copy-pasting did not work**

### Example: Migrating URCPP
1. First migrating the repository
```   
git clone --mirror https://manalaih@bitbucket.org/laborstudents/urcpp-flask.git

cd urcpp-flask 

git remote set-url --push origin https://github.com/BCStudentSoftwareDevTeam/urcpp.git

git push --mirror
```

2. Migrating the issues
```
cd bitbucket-issue-migration

python migrate.py --map-user urcpp_users_mapping_file.txt --bb-user manalaih laborstudents/urcpp-flask BCStudentSoftwareDevTeam/urcpp hmanalai
```


### SSDT Members' Github-to-Bitbucket Username Mapping File
After making sure all the username mapping are correct, copy-paste this list to a `.txt` file that is located in the same folder as the migrations script, which is `bitbucket-issue-migration` folder.

The username mapping is as `bitbucket_username=github_username`, each username separated by a new line. 

[SSDT_Users_Username_Mapping](/ssdt_users_mapping.txt)














