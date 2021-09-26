## Git Cheat Sheet

### Git Config
```bash
git config --global user.name "Your Name"
git config --global user.email "Your Email"
git config --global user.password "Your password"
git config --list
```

### Create Git Repository
```bash
# From Existing Directory
cd project_dir
git init
git add .

# From Other Repository
git clone git://github.com/user/repo.git
git clone https://github.com/user/repo.git
```

###  Local Changes
```bash
# Changed in working directory
git status

#Tracked file changes
git diff

# Add Changed Files
git add file1 file 2 file3

# Remove File
git rm file
git rm dir/-r

# See Files ready for commit
git diff --cached

# Commit Changes
git commit
git commit -m “message”
git commit -a -m “message”

# Change last commit
git commit --amend

# Revert Changes to file
git checkout -file

# Revert changes (new commit)
git revert HEAD

# Return to last committed state
git reset --hard HEAD

```

### History
```bash
# show all commits
git log

# Short Format
git log --pretty= short

#Patches
git log -p

# Show file commits
git log file

# Show directory commits
git log dir/

# Stats
git log --stat

# Who changed file
git blame file

```

### Merge/Rebase
```bash
# Merge branch into current
git merge branch

# Rebase into branch
git rebase branch
git rebase master branch

# Abort rebase
git rebase --abort

# Merge tool to solve conflicts
git mergetool

# Conflicts against base file
git diff --base file

# Diff other users change
git diff --theirs file

# Diff your changes
git diff --ours file

# After resolving conflicts
git rebase --continue
```

### Remote Update / Publish
```bash
# List remotes
git remote -v

# Show information
git remote show remote

# Add remote
git remote add path/url

# Fetch changes
git fetch remote

# Fetch + Merge
git pull remote branch

# Publish local to remote
git push remote branch

# Delete remote branch
git push remote branch

# Publish tags
git push --tags
```

### Branching / Tagging
```bash
# List branches
git branch

# Switch to branch
git checkout branch

# Create New Branch
git branch new

# Create branch from exisiting
git branch new existing

# Delete branch
git branch -D branch

# Tag current commit
git tag tag-name
```