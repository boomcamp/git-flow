# Git Flow 104 - Git Stash Operation and Git Reset

In these lesson you will able to learn about basic stash operation, this will be benefial to you specially if you are currently working and you `dont want to commit your changes yet`.

Lessons cover:

1. Basic stash and Pop
2. Basic head reseting


For better understanding we are going to create a `modified` file inside `feat/unsave-file`, follow these steps:

**Step 1**. Initialize your local project repository with folder and basic file.

```
mkdir stash-demo && cd stash-demo && touch file.md && git init
```

**Step 2**. Update and commit to `master` branch.

```
git add --all && git commit -m "My initial working tree"
```

**Step 3**. Create another from `master` and checkout to `feat/unsave-file`.

```
git branch feat/unsave-file && git checkout feat/unsave-file
```

**Step 4**. Open `file.md`

```
nano file.md
```

update your changes by adding these lines.

```
When you’ve been working on part of your project, things are in a messy state and you want to switch branches for a bit to work on something else. The problem is, you don’t want to do a commit of half-done work just so you can get back to this point later. The answer to this issue is the git stash command.
```

*exit and save by pressing `ctrl+x` , `y` then hit `enter`.*

**Step 5**. Check if the file is already `modified`.

```
git status -s
```

So we created our first `modified` changes now we are going to stash this file and checkout to `master` branch.

**Step 6**. Stashing modified file and check.

```
git stash && git status -s
```

this should display a WIP(Work In Progress) index like:

```
Saved working directory and index state WIP on feat/unsave-file: ...
```

**Step 7**. Check if file is listed in WIP.

```
git stash list
```

that will result to:

```
stash@{0}: WIP on feat/unsave-file: 2ef3da8 My initial working tree
```

using stash we can checkout back and forth to other branch, the next thing is putting back to modfied state we can make it by:

```
git stash pop stash@{0}
```

that will result to:

```
On branch feat/unsave-file
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   file.md

no changes added to commit (use "git add" and/or "git commit -a")
Dropped stash@{0} (26359146d3226d3e790c82c8707195fc1182d68b)
```

reset your `feat/unsave-file` branch to its previous state by:

```
git reset --hard HEAD
```

it will restore to `My initial working tree` which is your initial commit state

```
HEAD is now at 2ef3da8 My initial working tree
```


### There are various reset that you can experiment like specifying its commit hash like:

```
git reset --hard cedc856
```

Make sure you are on the branch where the commit is. I’m doing this on master.

Then use `git reset –hard <commit-hash>` to set the current branch HEAD to the commit you want.



### There are various stash operation that you can experiment with stashing like:

Git stash save

Git stash list

Git stash apply

Git stash pop

Git stash show

Git stash branch <name>

Git stash clear

Git stash drop