# DIFF

Diff shows you changes:

- between commits
- between the staging area and the repository
- what’s in the working area

```bash
# unstaged changes
> git diff
# file changes
> git diff <file>
# staged changes
> git diff --staged
```

## DIFF BRANCHES

```bash
# Which branches are merged with master, and can be cleaned up
> git branch --merged master
# Which branches aren’t merged with master yet?
> git branch --no-merged master
```
