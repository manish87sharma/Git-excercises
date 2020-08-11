# Plumbing Commands

## How to commit manually

```bash
# Create a file
>  echo "test">test.txt
# Generate a blob for the data
> git hash-object -w test.txt  
# Update the index file
> git update-index --add test.txt
# Create a tree
> git write-tree
# Create a commit object
> git commit-tree <tree hash> -m "adding file test"
```

## Important plumbing commands

```bash
# print the object value
> git cat-file -p <hash-ref>
# Type of object
> git cat-file -t <hash-ref>
# list the file inside staging area
> git ls-tree -s
# Get details about tree
> git ls-tree <hash-ref>
# list out objects
> git count-objects -v
# Run GC
> git prune --expire now
# list out object
> git rev-list --objects --all
# To count objects
> git count-objects
# dry run for git ignore
> git check-ignore -v *
# list all files with more details
> git ls-files --stage --debug  
```
