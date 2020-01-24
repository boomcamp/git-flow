# Git Branch Modeling 

What Is GitFlow?

> GitFlow is a branching model for Git, created by Vincent Driessen. It has attracted a lot of attention because it is very well suited to collaboration and scaling the development team.


Illustration:

![alt text](/references/git-model@2x.png)


# Short Demo

<TODO: Video>

## Key Benefits
Parallel Development
One of the great things about GitFlow is that it makes parallel development very easy, by isolating new development from finished work. New development (such as features and non-emergency bug fixes) is done in feature branches, and is only merged back into main body of code when the developer(s) is happy that the code is ready for release.

Although interruptions are a BadThing(tm), if you are asked to switch from one task to another, all you need to do is commit your changes and then create a new feature branch for your new task. When that task is done, just checkout your original feature branch and you can continue where you left off.

### Collaboration
Feature branches also make it easier for two or more developers to collaborate on the same feature, because each feature branch is a sandbox where the only changes are the changes necessary to get the new feature working. That makes it very easy to see and follow what each collaborator is doing.

### Release Staging Area
As new development is completed, it gets merged back into the develop branch, which is a staging area for all completed features that haven’t yet been released. So when the next release is branched off of develop, it will automatically contain all of the new stuff that has been finished.

### Support For Emergency Fixes
GitFlow supports hotfix branches - branches made from a tagged release. You can use these to make an emergency change, safe in the knowledge that the hotfix will only contain your emergency fix. There’s no risk that you’ll accidentally merge in new development at the same time.


### Boom.Camp external resources

- [A successful Git branching model](https://nvie.com/posts/a-successful-git-branching-model/)


- <object data="references/presentations/Git Branch Modeling.pdf" type="application/pdf" width="700px" height="700px">
    <embed src="references/presentations/Git Branch Modeling.pdf">
        <p><a href="references/presentations/Git Branch Modeling.pdf">[Git Branch Modeling.pdf]</a>.</p>
    </embed>
</object>


- <object data="references/presentations/Git Branch Modeling.pdf" type="application/pdf" width="700px" height="700px">
    <embed src="references/presentations/GIT COMMANDS.pdf">
        <p><a href="references/presentations/GIT COMMANDS.pdf">[GIT COMMANDS.pdf]</a>.</p>
    </embed>
</object>


- [Use Semantic Versioning and Give Your Version Numbers Meaning](https://embeddedartistry.com/blog/2017/12/7/start-using-semantic-versioning-to-give-your-version-numbers-meaning).

- [SemServer](https://semver.org/).

- [Cheatsheet](https://devhints.io/semver).

- [A simple guide to semantic versioning](https://www.jvandemo.com/a-simple-guide-to-semantic-versioning/)
