---
title: Git for Linux - Install and Quickstart Guide
date: 2022-3-2 12:00:00 -500
categories: [tutorial,software]
tags: [git,github,linux,install,software]
---
Here's my workflow for working with Git and Github; the following is assuming working on Linux but working on Windows is fairly similar. Much of this is done seemlessly in Vscode if you want to avoid the command line: https://code.visualstudio.com/download, https://code.visualstudio.com/docs/sourcecontrol/overview. 

# Install
1. Open a terminal and type:
```
sudo apt install git
```

# Clone a Repository (repo)
1. cd to where you want the repository cloned
2. 
```
git clone https://github.com/yourUsername/yourRepository.git
```
- could also be a repository from someone else
3. enter username
4. For password:
    1. follow the steps for creating a token: <https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token>
    2. paste in your token for the password
    3. (optional) save the token to a .txt file or something for 
    
# Push your changes
1. Mess around with some files in your local repository
2. Push what you have to the origin: <https://www.linode.com/docs/guides/how-to-install-git-and-clone-a-github-repository/>
    1. cd to your github folder
    2. 
    ```bash
    git add .
    git status
    git commit -a -m “message for commit”
    git push origin main
    ```
    **Note**: if you want to only commit certain files, then replae `git add .` with `git add [insert file name here]` 
    3. Or if the last command didn't work: `git push origin master` or `git push origin main`; essentially origin is your repository on Github.com, and master/main is the main branch
3. type in username and password

# Pull new changes
1. cd to your github folder
2. 
```
git pull origin main
```
3. enter username
4. enter token for password

Good overview videos: <https://www.youtube.com/watch?v=RGOj5yH7evk>

# Branching
## Create New Branch
1. `git branch`
- This tells you what branch you’re currently on
2. `git checkout -b name-of-branch`
- this creates a new branch
3. do your code modifications
4. 
```bash
git add .
git commit -m “title” -m “description”
git diff name-of-branch
```
- this shows the difference between the branch you just created
5. git push

## Merge origin/main changes into branch
Let’s say you want to pull changes to the origin/main branch to your branch:

1. commit and push all changes to your current branch)
2. 
```bash
git checkout main
git pull
git checkout {name of your branch}
git merge main
```

# Troubleshooting
**Problem:** 
```
remote: Support for password authentication was removed on August 13, 2021. Please use a personal access token instead.
remote: Please see https://github.blog/2020-12-15-token-authentication-requirements-for-git-operations/ for more information.
fatal: Authentication failed for ‘https://github.com/uw-esolab/sf-learn.git/’
```

**Solution:** need a token: <https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token>

**Problem: you want to clone a fresh repo over your branch**
```
git clone https://github.com/username/repo.git
Username: your_username
Password: your_token
```
***Solution:** If you don’t care about the changes you made and want to pull the repository, type in: git reset –hard origin

<https://stackoverflow.com/questions/1125968/how-do-i-force-git-pull-to-overwrite-local-files>