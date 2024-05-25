# Git (Version Control System)
## Git Install for Ubuntu
```
sudo apt update
sudo apt-get install git
git --version
git config --global user.name "Alan  Chan"
git config --global user.email "alloppi@gmail.com
```

## Working with GitHub projects
### Create the repository, clone it to Ubuntu
1. Create a new repository in GitHub
2. Clone local copy of the repository
```
cd [NAME OF REPOSITORY]
git clone [HTTPS ADDRESS]
```
3. Four steps in a commit: ‘status’ , ‘add’ , ‘commit’ and ‘push’
```
git status
git add [FILENAME] [FILENAME] [...]
git commit -m "Add comment"
git remote
git push origin master
```
### Work on project locally, create the repository on GitHub and push project to remote
```
cd [NAME OF REPOSITORY]
git init
git status
git add [FILENAME] [FILENAME] [...]
git add .
git commit -m "Add comment"
git remote
git push origin master