# Fixing mistakes

- Checkout
- Clean
- Revert
- Reset

## Checkout

It allow you to restore working tree files and switches branches.
Checkout can move the head pointer and update the staging area and working directory

## WHAT HAPPENS WHEN YOU GIT CHECKOUT A BRANCH

- Change HEAD to point to the new branch
- Copy the commit snapshot to the staging area
- Update the working area with the branch contents

## WHAT HAPPENS WHEN YOU GIT CHECKOUT - - FILE

Replace the working area copy with the version from the current
staging area

## GIT CHECKOUT: OVERWRITE FILES WITH STAGING AREA COPY

- Overwrite the working area file with the staging area version
from the last commit

```bash
> git checkout -- <file_path>
```

## WHAT HAPPENS WHEN YOU GIT CHECKOUT <COMMIT> - - FILE

1. Update the staging area to match the commit
2. Update the working area to match the staging area

## GIT CHECKOUT: FROM A SPECIFIC COMMIT

- Checkout a file from a specific commit
- copies to both working area & staging area
- git checkout <commit> -- <file_path>

```bash
# copies to both working area & staging area
> git checkout <commit> -- <file_path>
# Restore a deleted file
> git checkout <deleting_commit>^ -- <file_path>
```

## GIT CLEAN

- Git clean will clear your working area by deleting untracked
files.
- Use the —dry-run flag to see what would be deleted
- The -f flag to do the deletion
- The -d flag will clean directories

```bash
# shows what files to be deleted
> git clean --dry-run
# shows both files and directory to be deleted
> git clean -d --dry-run
# deleting the both files and directory
> git clean -d -f
# git status
> git status
```

## GIT RESET

- Reset is another command that performs different actions
depending on the arguments.
- with a path
- without a path
  - By default, git performs a git reset —mixed
- For commits:
  - Moves the HEAD pointer, optionally modifies files
- For file paths:
  - Does not move the HEAD pointer, modifies files

```bash
# move only head,commit before this will become dangling commit
> git reset --soft HEAD~
# move head and copy files to stage
> git reset HEAD or git reset --mixed HEAD
# move head and copy files to stage and working directory
# this overwrite files and can't be undone
> git reset --hard HEAD~

```

## GIT RESET <COMMIT> CHEAT CHEAT

1. Move HEAD and current branch
2. Reset the staging area
3. Reset the working area
--soft = (1)
--mixed =(1) & (2) (default)
--hard = (1) & (2) & (3)

## DANGER: GIT RESET CAN CHANGE HISTORY

Warning: never push changed history to a shared or public repository!

```bash
❯ git reset --soft HEAD~
❯ git commit -m “new commit"
```

## GIT RESET for file

```bash
# head pointer will not move
git reset <file>
#  res
> git reset <commit> -- <file>
```

## UNDO A GIT RESET WITH ORIG_HEAD

- In case of an accidental git reset -
- Git keeps the previous value of HEAD in variable called
ORIG_HEAD
- To go back to the way things were:
  
```bash
> git reset ORIG_HEAD
```

## GIT REVERT - THE “SAFE” RESET

- Git revert creates a new commit that introduces the opposite
changes from the specified commit.
- The original commit stays in the repository.
- Tip:
- Use revert if you’re undoing a commit that has already been
shared.
- Revert does not change history.

```bash
# create a new commit with undo
> git revert <commit>
```
