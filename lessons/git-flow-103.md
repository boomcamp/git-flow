# Git Flow 103 - Git Merging Conflict.

In this lesson you will be able to learn basics understanging about on how to manage and solve git conflicts.

# Overview
What is merge conflict?

Merge conflicts in git happen, when two branches were changed on `the same line` or in `the same content of a file` before a merge. If you just extend a file or append something, git usually just figures it out by itself

For better understanding lets see the basic example of a conflicted file:

file: `stable.txt`

```
<<<<<<< HEAD
I add a stable file, but mico change this

on another branch.
=======
I add a stable file.

Maybe this line will append to HEAD who know.
>>>>>>> feat/conflicting-branch
```

The arrows indicate which branch you’re currently on is `HEAD` and from which branch the conflicting change occurs in the merge is `feat/conflicting-branch` in this case.


# Solving our conflict
To have better understanding we are going to create our git conflict manually to do so, please follow these steps:

**Step 1** : Create your local project directory folder:
```
mkdir test-git-conflict && touch stable.txt
```

**Step 2** : Initialize your git project folder by:
```
git init
```

**Step 3** : Open your file using `nano` editor by:
```
nano stable.txt
```

**Step 4** : Add these contents.
```
Tip: You can use some tools that can automaticaly resolve conflicts like for example git plugins in `vscode`. which provides some sort of options to accept incoming or both changes in git.
```

***Exit and close by pressing `ctrl+x`  and `y` then `enter`***

**Step 5**: Check your added texts like:

```
cat stable.txt
```

**Step 6**: Add and commit your file.

```
git add --all && git commit -m "My intial stable commit"
```

so we are now setup our first stable file inside `master` branch to make our merge conflicts, the next step is creating another branch from  `master`  please continue next steps.

**Step 7**: Create another branch from `master`.

```
git branch bug/conflict
```

now we should have 2 branches created which is **master** and **bug/conflict**.

***You may try to list your branches by `git branch --list`***


**Step 8**: Checkout to `bug/conflict` by.

```
git checkout bug/conflict
```

**Step 9**: Then update your `bug/conflict` branch by.

```
nano stable.txt
```
and update it's content like for example

```
Tips:
```

***Exit and close by pressing `ctrl+x`  and `y` then `enter`***

**Step 10**: Add and commit.

```
git add --all && git commit -m "Updated stable commit"
```

After that we are going to do the same steps from `8 to 10` for `master` branch

**Step 11**: First checkout to `master` branch.

```
git checkout master
```

**Step 12**: Inside your master branch open `stable.txt` by.

```
nano stable.txt
```
and update it's content like for example.

```
My Tips:
```

***Exit and close by pressing `ctrl+x`  and `y` then `enter`***


Again git conlict occur only if `the same line` or in `the same content of a file` are both updated in our example:

Master = Tips:

Bug/conflict = My Tips:



**Step 13**: Add and commit.

```
git add --all && git commit -m "Updated stable commit"
```

inside our `master` branch we are going to try merge `bug/conflict` into `master` branch.

**Step 14**: To produce our conflicts merge these two branches

```
git merge bug/conflict
```

which will result to:

```
Auto-merging stable.txt
CONFLICT (content): Merge conflict in stable.txt
Automatic merge failed; fix conflicts and then commit the result.
```

open up `stable.txt` in your favorite editor you should see this arrow conflicts:

```
<<<<<<< HEAD
My Tips: You can use some tools that can automaticaly resolve conflicts like for example git plugins in `vscode`. which provides some sort of options to accept incoming or both changes in git.
=======
Tips: You can use some tools that can automaticaly resolve conflicts like for example git plugins in `vscode`. which provides some sort of options to accept incoming or both changes in git.
>>>>>>> bug/conflict
```

We need to identify carefully which changes are `needed to accept` in this case `bug/conflict` into `master` so we need to remove `<<<<<<< HEAD` until `======` and update our `stable.txt` like these:

```
Tips: You can use some tools that can automaticaly resolve conflicts like for example git plugins in `vscode`. which provides some sort of options to accept incoming or both changes in git.
```

After you update `stable.txt` save your changes.

**Step 15**: Commit your update file by.

```
git add stable.txt && git commit -m "Solved conflict"
```

To test if conflicts are already solve you can check it by `git merge bug/conflict` which will result to:

```
Already up to date.
```

Done. you can now `checkout` back an fort to different branches without worrying a conflict.
 
**Tip**: You can use some tools or plugins that can automaticaly resolve git conflicts like for example [vscode git](https://code.visualstudio.com/docs/editor/versioncontrol) in `vscode`. which provides some sort of options to accept incoming or both changes in git.
