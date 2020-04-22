# Staging

```bash
# delete any branch
git branch -D Exercise-staging
# list all files ins staging
git ls-files -s
# update hello.txt
echo "This is a test of the emergency git-casting system." >> hello.txt
# add file to stage interactively, ? for detail description
git add -p
# check new file content
git cat-file -p  b31a35
# Un staged changes after reset:
git reset hello.txt
# stash changes
git stash save "hello world update"
# check stash
git stash list
# show stash info
git stash show stash@{0}
# apply particular stash
git stash apply stash@{0}
# check git diff
git diff hello.txt
# apply last stash
git stash pop
# delete stash
git stash drop stash@{0}

```
