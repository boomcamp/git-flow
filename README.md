# Git Flow 

What Is GitFlow?

> GitFlow is a branching model for Git, created by Vincent Driessen. It has attracted a lot of attention because it is very well suited to collaboration and scaling the development team.


Illustration:

![alt text](/lessons/git-model@2x.png)


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


# Lessons coverage:

We are going to cover those important parts and a summarize lesson about git modeling.

**1. Git Flow 101**

[Orientation about git flow workflow](/lessons/git-flow-101.md)
[Diagram](lessons/git-flow-101-diagram.md)

**2. Git Flow 102**

[Producing our first release candidate.](/lessons/git-flow-102.md)
[Diagram](lessons/git-flow-102-diagram.md)

**3. Git Flow 103**  

[Git Merging Conflict.](/lessons/git-flow-103.md)
No diagram

**4. Git Flow 104** 
[Git Stash Operation and Git Reset.](/lessons/git-flow-104.md)
No diagram

### Resources

[Use Semantic Versioning and Give Your Version Numbers Meaning](https://embeddedartistry.com/blog/2017/12/7/start-using-semantic-versioning-to-give-your-version-numbers-meaning).

[SemServer](https://semver.org/).
