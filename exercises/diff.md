# DIFF

Diff shows you changes:

- between commits
- between the staging area and the repository
- what’s in the working area

```bash
# diff between staging area and working directory
> git diff
# Diff between staging area and commit
> git diff --staged
# diff between working directory and commit
> git diff HEAD
# diff file between two branches
> git diff branch1..branch2 --ignore-all-space <file>
```

## DIFF BRANCHES

```bash
# Which branches are merged with master, and can be cleaned up
> git branch --merged master
# Which branches aren’t merged with master yet?
> git branch --no-merged master
```
