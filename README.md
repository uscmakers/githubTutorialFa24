# Git Tutorial!

## Need help at any time?
If you need ANY help, feel free to make a github issue! On the top tab on the github page, you will see a tab called "issues". Please write your issue there and a member of our team will answer your questions asap! OR you can also post in the #tutorialhelp channel on slack!

## Crash Course of How to Navigate the Command Line 
If you have windows, you want to use the "powershell" application. If you use a Mac, you want to use the "terminal".

- cd ..: go back to the previous directory
- cd folder1: move inside folder1
- ls: list all the files in the current directory
- mkdir <folder_name>: make a folder with the name "folder_name"
- rm <file_name>: delete the file "file_name" permanently
- rm -r <folder_name>: delete the folder "folder_name" and all its contents permanently
- touch <file_name>: create an empty file

## Installation:
### Windows:
1. Get a github account and accept the invitation from "uscmakers" *important*
2. Go to https://git-scm.com/download/win and the download will start automatically.
3. Download sublime with this link: https://www.sublimetext.com/3 (select the windows version)
	1. If you already have a text editor such as VS Code, BBedit, Notepad++, Atom, etc, feel free to skip this step

### Mac:
1. Get a github account and accept the invitation from "uscmakers" *important*
2. Run: <git --version> on your terminal. If you don't already have git installed, this will prompt you to install git.
3. Download sublime with this link: https://www.sublimetext.com/3 (select the mac version)
	1. If you already have a text editor such as VS Code, BBedit, Notepad++, Atom, etc, feel free to skip this step
	
### Setting up Git
## Linking Github to the Terminal (after installing Git on device)
1. In the command prompt/powershell, type these following commands. Make sure your email is your USC email, and make sure that your username is the username affiliated with your github.
```
	git config --global user.name "Your name here"
	git config --global user.email "your_email@example.com"
```
2. By default, git does not color its output. Pretty printing git messages makes it easy read the output and take proper actions. You can enable colors for interactive use with:
```
	git config --global color.ui auto
```
3. Recently GitHub has changed to main as the default branch. We need our local git command to respect that:
```
	git config --global init.defaultBranch main
```
4. Operating systems implement new lines differently. Here you will configure git to automatically normalize the line feed to properly match the platform:

git config --global core.autocrlf input
5. Since Git 2.0, Git has updated its default push settings. To avoid getting a warning when you push (we will explain what push means soon), apply the following setting:
```
	git config --global push.default simple
```
## Configuring SSH Keys
Git uses SSH (Secure Shell protocol) keys to communicate with remote servers (servers in the cloud). You must generate these keys on your device and copy them to you Git profile so that you can establish a secure connection to your remote repos.
1. Enter the following in to your terminal
```
	ssh-keygen -t rsa -b 2048 -C "your_email@example.com"
```
2. When prompted for a location to save the key, use whatever the default is by pressing enter
3. After that, you will be prompted for a passphrase to secure your private key. We reccommend that you don't create a passphrase. Otherwise, you will have to type it in every time you wish to push to your remote repo. Press enter twice to continue wiht no passphrase. Upon success, you should see the following:
```
	Your identification has been saved in /home/cs104/.ssh/id_rsa.
	Your public key has been saved in /home/cs104/.ssh/id_rsa.pub.
	The key fingerprint is:
	SHA256:vC+4OG2u1PIeE0OKX9jiFFHuLnkYCBSsvIW8ybD873H ttrojan@usc.edu
	The key's randomart image is:
	+---[RSA 2048]----+
	|   ++o.          |
	|    S+.o *.*     |
	|   +.X. o        |
	|    0. o +       |
	|   ..o  E .      |
	|  .=S. . + .0    |
	| .*=* ...        |
	|.+.=o*. ..  *o*  |
	| .++*oo. ..      |
	+----[SHA256]-----+
```
4. In your Git account (on the website) navigate to your profile (click your icon in the top right corner) and then your settings. Click "SSH and GPG keys" in the left navigation menu
5. Click "New SSH key". Provide a name of your choice for the key (Eg. MacBookKey).
6. Display the contents of your id_rsa.pub file by running ```cat ~/.ssh/id_rsa.pub``` in your terminal. Select all the contents of your id_rsa.pub file all the way through the end of the last line where your email is displayed and then copy/paste them into the key field. Make sure you copy the entire contents of the id_rsa.pub file. It should start with ssh-rsa and end with your email address.
7. Click add key

## Guide:
0. Complete Installation, Crash Course, and Linking Github to the Terminal in this order. (If you have worked with git on your laptop, you may have to do none/some of the steps)
1. Clone this repo:
	1. Navigate to the folder you want to copy this tutorial into using the crash course guide above (please use the command line!)
	2. Copy the address of the repo. Press the "code" button on the right top of the screen of the online github repo, and copy the address with ONLY https
	3. type "git clone <address_you copied in step 1b>"- you should see the repo in your file explorer now!
	4. Navigate inside of the cloned folder by typing "cd TutorialPractice".
2. Pull Updates:
	1. In the command line, type "git pull" to pull all the updates from the upstream branch. Depending on when you do this, you might see other peoples' files load into your directory. This "refreshes" your local repository to reflect what the remote repository looks like.
3. Create a Branch
	1. Go back into the command line, and type "ls" or "dir". You should be able to see a README.md, and potentially other people's names.
	2. Now, lets orient ourselves and check which branch we are on by typing "git status". You should see that you are on the master branch. By default, you start on the master branch.
	3. Lets create a new branch by typing "git checkout -b <branch_name>" PLEASE title your branch your full name. Ex. Radhika_Agrawal
	4. Type "git status" again. You should see that you are now on your newly created branch.
4. Create a file
	1. Create a text file and name it your full name. Ex. Radhika_Agrawal.txt
	2. Open the file in your file explorer with Sublime (or editor of your choice)
	3. Write your name in the file!
	4. Save and close the file
5. Upload your code to github
	1. Type "git add -A". "-A" means all files
	2. Type "git commit -m "type a message here"". -m means that you will attatch a message to associate your commit with. In this case, just type a generic message briefly describing what you will be uploading.
	3. Type "git push". This should give you an error saying that you have not specified an upstream branch. 
	4. Copy what the error told you to type, which should be "git push --set-upstream origin <branch_name>". By doing this, you are setting where you will later be merging the branch to.
6. Create a pull request on github
	1. Navigate back to the github website and refresh. 
	2. Navigate to the "pull requests" tab
	3. You should see a button that says 'Compare and Pull Request'. Click on the button.
	4. Confirm that the "base" branch is Master, and the branch to be "compared" is your new branch.
	5. Title the pull request with your name Ex. Jenny's Pull Request. You can leave the comment section blank, or you can put some comment in it.
8. NOTE: You can also add people in your team as reviewers to review the pull request in a real life situation!
9. Merge your PR:
	1. You can merge your branch into master. Find your PR on the PR page, and merge it into the master branch.
	2. You will then be able to see your file on the master branch!
	
## Git Shortcuts

- git pull: pull updates from the upstream branch
- git pull origin master: pull updates specifically from the master head 
- git add -A: add ALL the updates that were made in the local repo
- git add jenny.txt: add ONLY the updates that were made in jenny.txt
- git commit -m "write a message": commit the updates
- git push: push the updates from your local repo to your remote repo
- git push --set-upstream origin branch_name: push the updates to the remote repo AND set your upstream branch to master
- git status: check which branch you are on
- git checkout -b branch_name: make a new branch and switch branches
- git checkout branch_name: switch branches
- git branch --list: list the branches that you have on your local machine
- git branch -d branch_name: delete the branch

## Advanced Git Shortcuts

- git reset --soft HEAD~1: Undo one git commit (change the ~1 to ~5 if you want to undo the past 5 commits)
- git stash: Lets pretend that you were working on branch "avl" to work on avl trees. Even though you don't want to commit the code yet, you want to hop over to another branch to work another feature. You can save the work you were doing on the avl trees using stash.
- git stash list: List all the stashes you've stored
- git stash apply: You can re-apply the changes you've stashed back to your branch (most recent stash)
- git stash apply@{2}: Re-apply the second to most recent stash to your branches. (you can change the number to specify which stash you are talking about)
