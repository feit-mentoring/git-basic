# Tutorial Summary

This quick tutorial will introduce the basic of Git and how we use it together with Github for our project. We will use commandline in WSL.


## Things to Cover
1. Authenticating to Github (SSH)
2. Cloning a repository
3. Creating a branch
4. Pushing a change
5. Pulling a change / checking out a branch
6. Creating a Pull Request/Merge Request
7. Basic rebase

## Authenticating to Github
1. In WSL, create an SSH key.
    1.1 Run 
    ```bash
    ssh-keygen -t ed25519 -C "youremail@gmail.com"
    ```
    1.2 Copy content of your public key. The command from 1.1 should tell you where is the location of the public key
    ```bash
    Your identification has been saved in /home/marloeuyjr/.ssh/id_ed25519
    Your public key has been saved in /home/marloeuyjr/.ssh/id_ed25519.pub
    The key fingerprint is: xxxxxx
    ....
    ```
2. Go to https://github.com/settings/keys, and under SSH keys, click New SSH key.
3. Paste the public key to **Key** field.
4. To test connection, go to WSL terminal and run:
```bash
ssh -T git@github.com
```
## Setting your git config
```bash
#Run:
git config --global user.email "you@example.com"
git config --global user.name "Your Name"
```

## Cloning a repository
1. In your WSL terminal, run:
```bash
git clone git@github.com:feit-mentoring/git-basic.git
```
2. cd to git-basic and run `code .`. This will open vs code from WSL and folder git-basic context.
```bash
cd git-basic
code .
```
3. Verify that the contents are similar to web browser.

# A little about trunk-based development
We are using trunk-based  development. The default branch which is usualy called **main** or **master** is protected and you cannot do changes directly to this branch. Free Github tier don't have this feature so our **main** branch is not protected.
We protect main branch to avoid unwanted changes and make sure that all new changes is reviewed through a Pull Request.
Trunk-based development maintain a main trunk and all features are merged to the main trunk once approved. Here is the usual flow:
1. New feature/bug/request
2. Developer will create a branch (copy of main branch)
3. Developer will develop from this feature branch
4. Once development is done, all codes are committed and pushed, a PR/MR is created which enables code review/peer review process. 
5. Somebody (usually a senior developer) will approve the Pull Request and then merged to the main branch.

## Creating a branch
1. In your WSL terminal, run:
```bash
git branch
```

## Commiting a change and pushing commits
1. In your WSL terminal, run:
```bash
git clone git@github.com:feit-mentoring/git-basic.git
```
