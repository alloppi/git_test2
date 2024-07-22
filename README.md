# Git (Version Control System)

Version control system keeps track of changes to a group of files. When you have a history of these changes, it lets you find specific versions, compare changes between versions, recover files you may have deleted, or revert files to previous versions.

A distributed version control system means that different users maintain their own repositories of a project, instead of working from one central repository. Users have full file tracking abilities and the project’s complete version history without needing access to a central server or network.

## Three Sections of a Git Project
1. Git directory: (YOUR-PROJECT-PATH/.git/) is where Git stores everything it needs to accurately track the project. This includes metadata and an object database which includes compressed versions of the project files.
2. Working directory: Pulls the project’s files from the Git directory’s object database and makes local changes to a project.
3. Staging area: Cache file that stores information about what will go into your next commit. A commit is when you tell Git to save these staged changes. Git takes a snapshot of the files as they are and permanently stores that snapshot in the Git directory.

## GitHub Workflow
1. Branching
2. Commits
3. Pull Request
4. Collaborate
5. Merge


## Git Install for Ubuntu
```
sudo apt update
sudo apt-get install git
git --version
git config --global user.name "Alan Chan"
git config --global user.email "alloppi@gmail.com
git config --global color.ui true
git config --global core.editor "code --wait"
git config --global diff.tool vscode
git config --global difftool.vscode.cmd "code --wait --diff $LOCAL $REMOTE"
```

## GitHub SSH access
Setup GitHub SSH sccess [GitHub SSH](https://docs.github.com/en/authentication/connecting-to-github-with-ssh).

## Working with GitHub projects
### I. Create the repository in remote repo (GitHub), then clone it to Ubuntu
1. Create a directory that save the new repository in GitHub
2. Clone local copy of the repository
```
cd [NAME OF DIRECTORY]
git clone [HTTPS REPO ADDRESS (GitHub)]
```
3. Four steps in a commit: ‘status’ , ‘add’ , ‘commit’ and ‘push’
```
git status
git add [FILENAME] [FILENAME] [...]
git add *
git commit -m "Add commit message" -m "Add description message"
git remote
git push origin main
```
### II. Start on project locally, create the repository on GitHub and push project to remote
```
#### Create a new repository in GitHub
mkdir [NAME OF REPOSITORY]
cd [NAME OF REPOSITORY]
echo "# git_test2" >> README.md
git init
git add README.md
git status
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:alloppi/git_test2.git
git push -u origin main
```

### Help for Git
```
git help COMMAND
git COMMAND --help
man git-COMMAND
```

### Git commands
```
git clone = bring a repository from the remote host (GitHuib) to local machine
git add = Track files and changed in Git
git commit = save files in Git
git push = Upload Git to remote repo (GitHub)
git pull = Download changes from remote repo to local machine, opposite to push
git branch = Check any branchexit

git remote -v
git branch
git commit -am "Modify only"
git ls-files
git rm [FILENAME] [FILENAME] [...]
git mv [NEW_FILE] [OLD_FILE]
git status -s
git diff --staged
git difftool --staged
git log
git log --oneline --reverse
git show d601b90
git show HEAD
git ls-tree HEAD~1
git restore
.gitignore > logs/ main.log *.log
```

### Branching
```
git checkout -b feature_x
git checkout main
git branch -d feather_X
```