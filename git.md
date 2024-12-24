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
git init --> used to initiate the branch on current repo
git status --> check all the files status of the repo.
git add .  --> made ready to commit the file who having changed.
git commit -m "message_user" -m "discription_message" --> it commit the changes you made
git push --> sync your commit to github accout.
