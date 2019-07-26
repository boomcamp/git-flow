# Git Flow 101 - Orientation about git flow workflow

> In these lesson you will be able to learn basics of branch modeling: 

It will cover.

1. Creating our first `feature` branch and push to repository.
2. Using the configured global git template for a meaningful commit messages.
3. Introducing to a different kinds of git log messages.
3. Git Merging. 

But first let's take a look what does git flow cycle looks like:

1. A `develop` branch is created from `master`
2. A `release` branch is created from `develop`
3. Feature branches are created from `develop`
4. When a `feature` is complete it is merged back into the `develop` branch
5. When the `release` branch is done it is merged into `develop` and `master`
6. If an issue in `master` is detected a `hotfix` branch is created from `master`
7. Once the `hotfix` is complete it is merged to both `develop` and `master`

### Configuration 

So first we need to configure first our git template, please follow these steps and procedure.

**Step 1**: Create your `.git_commit_template.txt` and add these inside your newly created template.

```
Subject

Body

Task
Sub Task
```

**Step 2**: We need to update our git global configuration file, edit `/path/to/` with a real path.

```
git config --global commit.template /path/to/.git_commit_template.txt
```

or we can edit directly our `.gitconfig` by typing `sudo nano ~/.gitconfig` and add these few lines below:

```
[commit]
 template = /path/to/.git_commit_template.txt
```

exit and save by pressing `ctrl+x` then `y` last press `enter`.



### Our first git branch

We are going to create our first feature branch from our existing repository for our git model.

**Step 1**: Clone existing project repository and specify which branch you would like to clone `-b develop`

```
git clone -b develop https://github.com/boomcamp/git-flow
```

**Step 2**: Create your new `feature` branch from `develop`. edit `yourname` with your real name.

```
git branch feat/yourname-bio && git checkout feat/yourname-bio
```

**Step 3**: Make sure that you are already inside your newly created feature branch which is `feat/yourname-bio` you can check it by listing.

```
git branch --list
```

*Note: an asterisk symbolize your current branch.*

**Step 4**: Inside `submission-bio` folder create a text file called `biodata-yourname.txt`.

```
touch biodata-yourname.txt && nano biodata-yourname.txt
```

***Note: change `-yourname` with your real name.***

**Step 5**: Fill your personal information inside `biodata-yourname.txt` 

```
Name:
Course:
My Overall Progressing in terms of software development:
```

exit and save by pressing `ctrl+x` then `y` last press `enter`

**Step 6**: Commit your changes, we can now use our configured commit template by typing.

```
git commit
```

update your commit template with information about your current changes, exit and save by pressing `ctrl+x` then `y` last press `enter`.

**Step 7**: Push your new feature branch.

```
git push origin feat/yourname-bio
```

*Note: typically we need to update first our local copy before pushing our new local branch to remote repository by doing `git pull --rebase origin feat/yourname-bio` then try to push it `git push origin feat/yourname-bio`*

**Step 8**: Merge back to `develop` branch.

```
git checkout develop
git merge feat/yourname-bio
```

**Step 9**: Push your updated `develop` branch to origin.

```
git push origin develop
```
*Note: typically we need to update first our local copy before pushing our new local branch to remote repository by doing `git pull --rebase origin develop` then try to push it `git push origin develop`*

**Step 10**: Check your log messages

Below are various logging messages in git you may try one by one.

Display a simple oneline commit message.
 
```
git log --oneline
git log --pretty=oneline
```

Graph and decorate all commit messages by oneline.

```
git log --graph --decorate --oneline --all
```

Graph and format by oneline commit messages.

```
git log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr)%Creset' --abbrev-commit --date=relative
```

i guess its bit too long to memorize the last command, Let's just make an alias for that. Copy and paste the line below on your terminal:

```
git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
```

and then every time you need to see your log, just type in.

```
git lg
```

Or, if you want to see the lines that changed

```
git lg -p
```

Please take note that all changes you made for your git global configuration are always stored inside `.gitconfig`

The next lesson will be about `fetching` remote changes, creating your first `release candidate` branch by using `semantic versioning`