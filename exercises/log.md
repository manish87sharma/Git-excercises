# Git Log

```bash
> git log --since="yesterday"
> git log --since="2 weeks ago"
# follow particular file 
> git log --name-status --follow -- hello.txt
# search for commit message that match regular expression
> git log --grep=reference --author=manish --since=2.weeks
# filter logs, A- added, R- rename, M- modified 
> git log --stat --diff-filter=A
```
