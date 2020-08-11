# Commands

## Archive

### create an archive file from specified Git Refs like, commits, branches, or trees. git archive accepts additional arguments that will alter the archive output

```bash
> git archive --output=./example_repo_archive.tar --format=tar HEAD
```

## creating and applying patch

GIT patch or GIT diff is used to share the changes made by you to others without pushing it to main branch of the repository. This way other people can check your changes from the GIT patch file you made and suggest the necessary corrections. After making all the corrections you can push the changes to main branch of the repository.

```bash
# creating the patch
git format-patch master --stdout > fix_empty_poster.patch
# check the patch
git apply --check fix_empty_poster.patch
# stat of path
git apply --stat fix_empty_poster.patch

# apply the patch
git am --signoff < fix_empty_poster.patch
```

## git bisect

Use binary search to find the commit that introduced a bug

```bash
git bisect start
# if commit is good
git bisect good <commit>
# if commit is bad
git bisect bad  <commit>
# To end bisect
git bisect reset
```
