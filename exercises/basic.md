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
