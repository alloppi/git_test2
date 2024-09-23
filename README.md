# This repo was used to learn Git (Version Control System)

Version control system keeps track of changes to a group of files. When you have a history of these changes, it lets you find specific versions, compare changes between versions, recover files you may have deleted, or revert files to previous versions.

A distributed version control system means that different users maintain their own repositories of a project, instead of working from one central repository. Users have full file tracking abilities and the project’s complete version history without needing access to a central server or network.

## Three Sections of a Git Project
1. Git directory or : (YOUR-PROJECT-PATH/.git/) is where Git stores everything it needs to accurately track the project. This includes metadata and an object database which includes compressed versions of the project files.
2. Working directory: Pulls the project’s files from the Git directory’s object database and makes local changes to a project.
3. Staging area: Cache file that stores information about what will go into your next commit. A commit is when you tell Git to save these staged changes. Git takes a Snapshot of the files as they are and permanently stores that snapshot in the Git directory.

## GitHub Workflow
1. Branching
2. Commits
3. Pull Request
4. Collaborate
5. Merge or 
6. Rebase


## Git Install for Ubuntu
```
sudo apt update
sudo apt-get install git
git --version
git config --global user.name "Alan Chan"
git config --global user.email "alloppi@gmail.com"
git config --global color.ui true
git config --global core.editor "code --wait"
git config --global diff.tool vscode
git config --global difftool.vscode.cmd "code --wait --diff $LOCAL $REMOTE"
git config -l = List config
```

## GitHub SSH access
Setup GitHub SSH sccess [GitHub SSH](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)

## Working with GitHub projects
### I. Create the repository in remote repo (GitHub), then clone it to Ubuntu
1. Create a directory that save the new repository in GitHub
2. Clone local copy of the repository
```
cd [NAME OF DIRECTORY]
git clone [HTTPS REPO ADDRESS (GitHub)]
git remote -v = Check the remote origin
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
mkdir <repos_will_be_inside>
cd <repos_will_be_inside>
echo "# git_test2" >> README.md
git init 
git add README.md
git status
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:alloppi/git_test2.git  /* origin is the alias */
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
git --version
git --help = contains good Git tutorial insided
git init . = initial git repository
git clone = bring a repository from the remote host (GitHuib) to local machine
git add . = Track all files in current dir and add to staging area
git add -A = Track all files in all dir
git commit = save files in Git, add to commit history
git remote add origin git@github.com:alloppi/git_test2.git = set remote 
git push origin main = Upload Git commit history to remote repo (GitHub) in main branch
git pull = Download changes from remote repo to local machine, opposite to push
git branch = Check any branches in Git (-r for remote, -a for all, - for previous)
git branch feature_1 = Copy commit from current branch to branch feature1 
git checkout feature_1 = Switch to branch feature_1
git status = Check current branch, untracked files and track files
git rm <filename> = Remove file from staging area to unstage
git rm -r --cached . = Recusively remove all files from staging area to unstage
git mv <filename> <newfile> =  Rename file
git log = show all commit history
git log --oneline --graph = show commit history in one line
git show <hash> = show diff for that commit image
git restore <filename> = discard changes after git commit
git diff = show different current file contenet vs last commmited
git commit --amend -m "Amend commit message after commited" = amend commited message
git commit -a -m "update content" = Add and commit together

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
git checkout -b <Branch> = Create branch <Branch>
git branch <Branch> = Create branch <Branch>
git switch <Branch> = Switch to Branch <Branch>
git checkout main = Switch back to branch main
git diff <Branch> = Difference between current branch & <Branch>
git branch -d <Branch> = Delete branch <Branch>
git branch -a = Check all branches
git push origin <Branch>
```

### Updating & Merging
```
git pull = update local repo to latest commit
git merge <Branch> = Merge another branch into active <Branch>
git diff <source_branch> <target_branch> = Preview the different before merging
```

### Tagging
```
git tag 1.0.0 <commit_id> 
```

### Git Roll back Method 1, Checkout commit, (Virtual Commit, require create new branch and merge into main)
```
git checkout <commit_id> = Roll back to the hash that commit
git switch - = Reverse the previous roll back command

git checkout -- <filename> = discard the changes to last HEAD
```

### Git Roll back Method 2, Revert Commit
```
git revert <commit_id> = Roll back to the hash that commit
```

### Git Roll back Method 3, Reset Commit (permanent delete all the commits after commit_id)
```
git reset = Unstage: Undo after git add
get reset -- <file> = Unstage the file
git reset HEAD~1 = Undo the last commit
git reset <commit_id> = 
git reset --hard <commit_id>
```

### Git Roll Back Method 4
```
git restore <file> = discard changes in working directory
git restore --staged <file>..." = to unstage
```

### Code review by team and give comment in GitGub
1. Check every changes
2. Discuss and comment by team
3. Resolve conflicts code
4. Merge & versioning
[Find more details in GitHub](https://github.com/features/code-review)


### Branch vs Rebase
[Git rebase tutorial](https://www.atlassian.com/git/tutorials/rewriting-history/git-rebase)
```
git rebase --interactive <base>
```

### Common Error in GitHub
1. Use SSH instead of HTTPS if pushing to GitHub have error: 
```
git remote set-url origin git@github.com:username/repo.git
```
