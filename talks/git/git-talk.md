% Got* Talk
% Missoula GDG
% April 16 2015

# Howdy

## My name is Ben

![Using got for over 6 years][1]

* Intern at Workiva
* Student at U of M
* Got proponent

## Today's Goals

> * Cover the life cycle of a logical change in git
> * Wow, I am a terrible speller...
> * Lets fix my mistake

## Oh look, I anticipated this!
I will use this tangible error to illustrate all the steps to effectively commit
changes and distribute them with git.

# Commits

## Fundamental Building Block

* Git does not care about files, only *changes*
* It has the ability to diff what it knows against the working directory
* Each commit is an assembly of *selected* changes as well as meta data
* Including the id of it's parent commit

## Identification

* SHA-256 Hashing produces an almost unique identification
* ex: 12d778978290a212193aa770d55d59ed36dbdabd
* Since commits point to their parents...
* A linear history is established

## 

![Linear History][2]

## Linear Commands

* `git log`
* `git commit`
* *etc*

# Branches

## Multiple Histories

* Pointers go from child to parent
* *So* parents can have many children
* But keeping track of concurrent commits is crazy
* Ergo, **Branches**

## Branches are pointers too

A branch is a meta object that maps a common name to a particular commit.

* There are a few special pointers, but HEAD is important
* HEAD tells git what the most current commit is
* A branch allows you to update head and change your current working commit

## 

![Concurrent History][3]

## My spelling problems

* Lets fix my spelling issues by creating a *feature branch*
* This is a logical grouping of commits that solves a particular problem
* `git branch spelling_errors`
* `git checkout spelling_errors`

## Feature Branches

* Allows me to work independently of the status of the **master** branch
* I can switch from this feature to another or the **master** branch at any time
* If I find my effort is pointless, I can remove this branch without consequence

## Changes to the Code

* I can correct my spelling issues
* Add them to the stage
* And commit them to the repository

# Remotes

## Converging Branches

* So now that I have a fix in place and am satisfied
* But how do I get my fix into the main code base, ie **master**?

## Local Merges

* I could certainly merge my feature branch into master
* But who says I am correct? Obviously my spelling can't be trusted
* What if the **master** differs in time between my repo and another?

# Pull Requests

## Mitigation and Synchronization

A pull request is an abstraction built into Github that allows you to wrap a
feature branch in a request to merge.

* Allows team to review your changes prompts discussion and correctness
* Upon approval, offers a single merge mechanism
* Everyone's repository is downstream of Github's **master**

## Creating a Pull Request

* First I must *push* my feature branch
* `git push --set-upstream origin spelling_errors`
* Github's tooling notices my new branch and prompts for a PR request

--------------------------------

![Remotes][4]

## Review and Merging

* Another team mate reviews your changes and vets your attempt
* When agree once is made, Github allows merging into the target branch
* An authoritative member of the team merges the new feature branch 

## Merge Conflicts

* Github is aware of the merge-able-ness of your branch
* For instance if a team member merges their PR
    * You changes are now against an antiquated master
    * You must merge/rebase master into your feature branch
    * Adds the latest changes so that your feature branch is merge-able

## Downstream Updates

Now that the feature branch is a part of master, I must pull from Github to
reflect the changes in my local repository. I am now ready to start a new
feature branch for the next change!

# Conclusion

## Review

This process touched on the three critical aspects of git. We used a live
example of how to interact with the repository and submit changes.

* Commits
* Branches
* Remotes

## Questions?
 
[1]: imgs/benjic_git_history.png
[2]: imgs/linear_history.png
[3]: imgs/concurrent_history.png
[4]: imgs/remote_history.png
