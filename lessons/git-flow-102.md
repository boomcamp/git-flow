# Git Flow 102 - Producing our first release candidate.

> In this lesson you will learn about fetching remote changes, creating your first release candidate branch by using semantic versioning.

# Semantic versioning and Git tagging description
What is a semantic versioning?

Semantic versioning (also referred as SemVer) is a versioning system that has been on the rise over the last few years. It has always been a problem for software developers, release managers and consumers. Having a universal way of versioning the software development projects is the best way to track what is going on with the software as new plugins, addons, libraries and extensions are being built almost everyday.
Semantic Versioning is a 3-component number in the format of **X.Y.Z**, 

where :

**X** = stands for a major version.

**Y** = stands for a minor version.

**Z** = stands for a patch.

The goal of `SemVer` was to bring some sanity to the management of rapidly moving software release targets

to have an idea what releases looks like, i list some example of releases or updates that can download by the end user :

https://github.com/jquery/jquery/releases
https://github.com/facebook/react/tags
https://nodejs.org/en/about/releases/

the goal of `SemServer` is to keep track of every transition or updates in the software development phase.

[Official Documentation SemServer](https://semver.org/)

### What is tagging? 

 The simple explanation of tagging is like a branch and have no further history of commits.

# Fetching from remote changes

From our previous repository `git-flow` we might need to sync remote changes by:

```
git fetch --all 
```

after that we are able to list remote branches by adding `-r` as a parameter, so we can type.

```
git branch -r
```

# Creating and pushing our tags to remote repository

We already done with sync from remote repository and have basic knowledge about `semantic versioning`, now we are going to proceed with basics of tagging please follow these steps below:

**Step 1**: We must checkout to `develop` branch by typing.

```
git checkout develop
```

**Step 2**: Create our first `release` branch from `develop` branch.

```
git branch rc/yourname && git checkout rc/yourname
```

- a release candidate branches can be describe as `rc`

*note: change `yourname` with your real name*


**Step 3**: Merge back your `release` branch to `master` and `develop` by.

```
git checkout master
git merge rc/yourname

git checkout develop
git merge rc/yourname
```

**Step 4**: After successful merging you need to `checkout` in `master` branch.

```
git checkout master
```


The next steps are tagging our release inside `master` branch.


**Step 5**: Create annotated tag by specifying `-a` as parameter in your command:

```
git tag -a rc-1.0.0-yourname -m "My first release version 1.0.0"
```

***change `yourname` with your real name***

**Step 6**: You may try to display your newly created tags by:

```
git show rc-1.0.0-yourname
```

*Please take note that tagging are only for `master` branch.*

**Step 7**: Pushing your newly created tag to the repository.

```
git push origin --tags
```

*Note: typically we need to update first our local copy before pushing any changes to remote repository by doing `git pull --rebase origin master` then try to push it `git push origin --tags`*


### List of some useful commands for tag:

List all the tags:

```
git tag
```

Search tags for a particular pattern:

```
git tag -l <tag-pattern>
```

Show a tag data:

```
git show <tag-name>
```
 
Create a Lightweight Tag:

```
git tag <tag-name>
```

Create a tag for a specific commit:

```
git tag -a <tag-name> <commit-checksome>
```

Push a specific tag to remote:

```
git push origin <tag-name>
```

Push all the tags to remote:

```
git push origin --tags
```

Checkout a specific to local:

```
git checkout -b <branch-name> <tag-name>
```

Congratulations! you already created our first release candidate
