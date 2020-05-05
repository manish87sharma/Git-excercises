# Git Log

```bash
> git log --since="yesterday"
> git log --since="2 weeks ago"
# follow particular file
> git log --name-status --follow -- hello.txt
# follow file
> git log --name-status --follow --since "yesterday" --stat  hello.template
# search for commit message that match regular expression
> git log --grep=reference --author=manish --since=2.weeks
# filter logs, A- added, R- rename, M- modified
> git log --stat --diff-filter=A
# log and graph
> git log --graph --oneline

```

## Git Reflog

 it is a record of all commits that are or were referenced in your repo at any time

```bash
git log --reflog
```
