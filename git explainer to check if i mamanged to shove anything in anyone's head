## Explaining git concepts

>In this exercise, you will write an explanation for various git concepts.

> - Don't assume any prior knowledge of git: imagine you are explaining these concepts to a brand new software developer. Because of this, try not to use jargon.
> - Write full, complete prose. Bullet points can be useful, but not what we're after for this module.
> - Test the explanation. Try your explanation on a non-technical friend before submitting it.

I have a large number of non-techinical friends as well as have tutored git to students. I'm going to explain things the same way I explain these concepts to my non-techinical friends, kids and even freshman students. 

These are also the same ways I was taught by my mentor Gordon Wood during my first internship at Other Ocean Interactive at the end of my first year when he taught me git and by my upperclassman at the time serving his CO-OP work term, Patrick, who taught me command-line git.

> We want explanations for:

> - git

Git is what we call a `version control manager`. A version control manager is a protocol that allows us to track changes to a project as well keeping track of who is working on this project and they contributed to. Think of this similar to an engineer's log book or the Google Docs Collaboration History. We use these to document and keep track of changes to done to any one object or project. Git lets us handle the logging part for us by having us notify it that we did something, and git records it in it's ledger, called the `HEAD`. Every contributor has different a different head, and they can get compared to get an accurate picture of changes having been made. 

> - repository

A repository, like the name it borrows, holds a copy of the project, stored somewhere, either a local server or even the cloud through a service such as GitHub, GitLab or Microsoft DevOps. There can be multiple copies of a repository, making them repositories of their own. This forms a `working tree`, which uses the tree data strucutre, which borrows and is directly inspired by how we classify and interact with parts of a tree. Keeping the tree analogy in your mind is very useful to remembering ideas and concepts of git. Think of the respository as the `stem` or `trunk` of `the working tree`. Whenever you see working tree diagrams, the repositories are the straight lines from where `branches` are made and `merged`. More on those topics as we move forward.

> - remote

When you begin to work on a project, you will get your own `local` repository, a copy of the repository stored somewhere that everyone bases their work off of. This master copy of sorts, the "original" if you will, is called the `remote`. You, your colleagues and the remote have your own ledgers, your own `HEAD` node. Whenever you perform a change in your `local` repository, you can notify the remote of changes by performing a `push`. 

When you perform a push, your `HEAD` records any changes made since it's last known state of the remote. It then sends the list of changes (also known as `commits`, more on that later)  to the `remote` repository you are linked to and updates it. Similarly, you can do the reverse of this, `pulling` data from the `remote` to your `local` repository anytime there are new changes from the remote. 

Of course, git being ledgers, it means it can give a sense of place of where you are `relative` to the remote you're linked to. These introduce the concepts of being `ahead of the remote` and being `behind the remote`. Being ahead means you have changes you haven't pushed to the remote. Being behind means the remote has changes you haven't pulled. Being ahead and behind are not mutually exclusive, meaning you can be ahead in some ways and behind in others.

Before we move on we must address something. So far we have treated our understanding as having one remote, or one "original" to your local copy. The truth is that this relationship is **not** one to one. The truth is that you can also have multiple copies of a repository stored somewhere that is not local to you. What this means is that any repository can have mutiple remotes and multiple local copies in a network or `working tree`. 

In the network you are somehwere on the `stream`. Any changes you push will going upwards the chain of repositories you are attached to is called `going upstream`. Any changes that get propogated downwards to the chain of repositories attached to you is called `going downstream`. 

This allows you to have multiple `upstream sources` or `upstreams`. This is the concept where your copy is attached to two or more `remote` repositories or `remotes`. From here you can have complete discretion of what changes you're going to push to which `upstream`, effectively allowing you to propogate changes to the same project in multiple places. Common usage of this concept is having one `remote` in a service such as GitHub or GitLab where contributions can be made, and another `remote` in deployment or production in parallel, deploying the latest stable changes to the public to a hosting service such as Heroku or AWS. 

> - branching

`Branching` refers to making changes on a copy of your repository, separate from the `main` working tree or repository. Branching allows you to introduce fixes or changes you can test on an isolated copy of your project, making it easier to revert and test out your changes without introducing severe bugs or serious issues to the project before you iron them out. 

This is similar to the concept of the recording room, the virtual machine or dual booting. These are isolated spaces you can experiment in and then once you are sure they work, you can push your changes, or `commits` upstream by performing a `merge`.

When you make a branch you effectively have made a virtual copy of the repository at that point in time, storing changes relative to the next `repository` or `node` up. This means you can make branches out of branches and the changes become incredibly relative. 

This introduces us to the concept of the `fork`. The reality of the matter is that forks and branches are really not that different. However, due to the recursive nature of our tree data structure and to an essence, real trees, we can take a group of branches and treating them effectively as their own thing. 

This separate group is called a fork. A fork becomes a divergence from the main project, allowing it to develop at it's own pace or time, allowing it to develop features we can later propose to the main developers or introduce modifications we believe would help in our own specific case without pushing those changes upstream unless we want to or need to. A fork can have forks and each fork can have its own branches that can develop into their own forks. 

This difference is only conceptual to us, the computer and the protocol really cannot tell the difference. As such, forks and forked development is often considered to be part of a more experienced toolset that can become incredibly powerful and helpful under the right circumstances. 

The concept of the branch and fork are essential to the organization of programming and development projects as well as the open source community as it is how we can offer changes.  

> - merging

Say you have been chugging along in your project and have made changes in your own branch and your colleagues have tested it enough to call it good enough to go into the `remote` repository and have everyone update to your latest change or fix. Pushing your changes only really pushes it to your branch. But now, how can you introduce the changes to everyone else? By performing a `merge`. A merge compares the `HEAD` of your local against the remote and introduces your changes to the remote from your branch. It's basically a push going upstream. From there, the remote is now update to reflect the changes from your branch. 

Usually, changes tend to be smooth sailing like any other push, however, sometimes a fix means you have to change something already up there. We could just overwrite them, but when you start to work in bigger groups, you do not know what could be upstream from your colleagues, and this can introduce breaking changes. You could revert changes to their previous state by either performing a `rebase` (a wipe of the previous head up to a certain point) or a `HEAD reset` which is a rollback; but it's much better to prevent them. 

The prevention mechanism is called a `merge conflict`. 

It bears mentioning that the merge is a fundamental part of the protocol, as a `pull` is actually a combination of a `fetch`, an operation that writes the changes from the remote to your local as commits, and a `merge`, where those commits are applied, setting a new state. As such, you can have a merge conflict both upstream and downstream. 

> - merge conflicts

A merge conflict occurs when two HEADS disagree on which change of an established line is the correct one. This is a preventative move to ensure any changes to already established (and assumed stable) code are done intentionally and correctly depending on the needs of the team while avoiding mistakes that would require complicated and expensive methods of fixing or reverting them. 

A merge conflict shows the file in question with a `diff` or `differential`. The differential is a record of what changes have been made. On a conflict, you get to chose which version is the one you want to propogate or keep. Once you have chosen, the change is committed once again and pushed (or merged if downstream). 

> - the three git states:

We perform changes or `commits` on a file based on the following state system:


> - comitted

This stage is the "status quo" stage. A file that has changed, staged and finalized is stored in this manner until a modification is made.


>  - modified

This is a change you perform a change on a file. Git, nor the remote know this change has been made. In this stage or state, you spend your time essentially performing the fixes or changes. 
 

>  - staged

Staging is the state where you make a note or officially `commit` your change. This notifies your `HEAD` that a change has been made. In a pull request, a chain of commits before a merge or push are assumed to be commits that have been staged together. A file in this state, while subject to change, means has changes that are ready to be pushed upstream. These new commits become the new comitted state, thus establishing the state cycle again. 



