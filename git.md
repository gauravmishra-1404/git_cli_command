git.md

********git*****************
git is the version control system wby the help of which we can track all our commits of our source code..
it is free open source.

it simplfy the work for software developers work on same code simontaneously using different braches which will merge to master branch.

What is the version control?
It is the way to commit the code base again and again on minor change which will give us all the list of changes that we made in past via records of SHA1 hashes.

Terms:
directory -> Folder
Terminal or command line -> Interface for text commands
CLI -> command Line interface.
cd -> change directory
code editor -> word processor for writing code
Repository -> Project or the folder/place where your project is kept.
git -> is the tool which interact the changes over time
github -> A website where you host ur all ur git repository.  user.name ""


Git Command:-
Clone -> if repo is not in local machine and you want that repo, we can just clone the repo to our machine from github website.

add -> track your files and changes in git
commit -> save your file 
push -> upload git commit to a remote repo like github
pull -> download changes from remote repo to your local machine, th  opposite of push.

Read.md -> md is mark down which is easy way to edit or formate ur text.
for configration:

git config --global user.name "Your Name"
git config --global user.email "Your email"

git config --list  --> gives all configuration that i made.

for any editing on configuration:
nano ~/.gitconfig

git clone https/ssh/github CLI command 
git --status
git --version
git init --> used to initiate the branch on current directory or keep an eye on the directory or file for any change.

git status --> check all the files status of the repo.
git add .  --> made ready to commit the file who having changed.
git commit -m "message_user" -m "discription_message" --> it commit the changes you made
git push --> sync your commit to github accout.

***************SSHKey**********************
Using the SSH protocol, you can connect and authenticate to remote servers and services. With SSH keys, you can connect to GitHub without supplying your username and personal access token at each visit. You can also use an SSH key to sign commits.

SSH key: help us connect local machine to the github account.

*****SSH key i have generate locally on machine.

command: ssh-keygen -t rsa -b 4096 -C "gaurav.mishra.31.4@mountblue.tech"

There are 2 files generated which contain ssh key:
1. testKey ---> private ssh key use to show the machine that i am the user for authentication.
2. testKey.pub ---> public ssh key we put on the github. it require when i need to push into repo.

***only private key generate the public key.
https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent

git push origin master ---> origin signifies the location of the git repo
                            master is the brach that we want to push to