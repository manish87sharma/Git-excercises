# References

```bash
# check where is head
cat .git/HEAD
# check value
cat .git/refs/heads/Exercise-references
# list all the refs
git show-ref --heads
# check all the ref value, all branches are pointing to different commits
git cat-file -p 86ed95
```

## creating tags

```bash
# create simple tag
git tag my-exercise-reference
# list all tags
git show-ref --tags
# check tags pointing at particular commit
git tag --points-at 35c79d
# annotated tag
git tag -a v1.0 -m "my-exercise-reference-annotated"
# To show details about tag
git show v1.0

```

## creating detached Head

```bash
# point to some commit
git checkout 86ed957
# check the head
cat .git/HEAD
```

## Dangling commit

```bash
# add file
echo "this is dangling content">>dangle.txt
# stage and commit the file
git commit -m "this is dangling commit"
# check logs
git log --oneline
# check head
cat .git/HEAD
# checkout the other branch
git checkout Exercise-references
# create a branch from dangling commit
git branch <new-branch-name> f95f5ae
# create an empty branch
> git checkout --orphan <name>
```
