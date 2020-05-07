# Exercise 1

```bash
# git clone
git clone https://github.com/manish87sharma/Git-excercises.git  
# delete hooks for now
rm -rf .git/hooks/
# check the tree
tree .git  
# generate hash
echo "hello" | git hash-object --stdin
> ce013625030ba8dba906f756967f9e9ca394464a
# store the blob
echo "hello" | git hash-object -w --stdin
# check the content of blob
git cat-file -p ce013625
# check type
git cat-file -t ce013625
# first commit
echo 'Hello World!' > hello.txt
git add hello.txt
git commit -m "added file"
```

## Analysis of objects

### Three objects created

- commit (86ed95)
- tree   (581caa)
- blob   (980a0d)

```bash
git cat-file -p 581caa
git cat-file -t 581caa
git cat-file -p 86ed95
git cat-file -p 980a0d
```

## Branch creation

```bash
# head is point to refs/heads/Exercise-commit
cat .git/HEAD
# branch will point to last commit
git checkout -b Exercise-commit
tree .git
git log --oneline
```

## To set Upstream project

```bash
git push --set-upstream origin Exercise-commit
```

## Garbage collector

```bash
# running the garbage collector forcefully
> git gc --prune=now
# list all the dangling objects
> git fsck
# un reachable
```

## remote

```bash
# Retrieve/Clone a repo
> git clone (URL)
# List remotes
> git remote (-v for detail)
# Commit graph
> git log --all --decorate --oneline --graph
# Checkout a branch
> git checkout
# Create and checkout a branch
> git checkout -b (branch name)
# Retrieve/download from a remote
> git fetch (remote name)
# merge branch or tracking-branch
> git merge (branch or tracking branch name)
# List remote branches
> git branch -r
# List both local and remote branches
> git branch -a
# setting upstream
> git remote add upstream <path>
```

### Git global setup

git config --global user.name "Sharma Manish"
git config --global user.email "manish.sharma@nagra.com"

### Create a new repository

```bash
    git clone <path>
    cd junit-test-reports
    touch README.md
    git add README.md
    git commit -m "add README"
    git push -u origin master
```

### Push an existing folder

```bash
cd existing_folder
git init
git remote add origin <path>
git add .
git commit -m "Initial commit"
git push -u origin master
```

### Push an existing Git repository

```bash
cd existing_repo
git remote rename origin old-origin
git remote add origin <path>
git push -u origin --all
git push -u origin --tags
```

### Alias

```bash
# Create a alias
> git config --global alias.logs 'log --oneline --graph --decorate'
```

### Setup up git remote repository

```bash
# Follow below step
> mkdir central-repo.git
> cd central-repo.git
# There is a difference between git init and below command
# This does not create and .git folder ,everything is put under root
# No file will be tracked here
> git init --bare
# Clone the repo on the local machine
> git clone user@ip:<Repo path>
```
