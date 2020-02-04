[<< Back to The Basics](index.md)

# Version Control
Version control is a system that records changes to a file or set of files over time so that you can recall specific versions later.

The first generation of version control used file locking (SCCS, RCS).  The second generation become centralized, allowing concurrent edits and requiring merges before commit (CVS, Vault, TFS, etc).  In the third generation, version control became distributed (Mercurial, Git, etc).

# Centralized Version Control
Traditional revision control systems use a centralized model where all the revision control functions take place on a shared server. If two developers try to change the same file at the same time, without some method of managing access the developers may end up overwriting each other's work. Centralized revision control systems solve this problem in one of two different "source management models": file locking and version merging.

# Distributed Version Control
In a distributed version control system, the complete codebase - including full history - is mirrored on every machine that has cloned the repository.

## Directed Acyclic Graph (DAG)
A graph is composed of nodes and edges.  Some edges are directed, signifying a parent-child relationship.  A node with no parents is a root.  A child can also be called a branch.  When a node has more than one parent, it is a merge.  A node with no children is called a head.  In an acyclic graph, you cannot return to your node of origin by following the directed edges in the graph:

![DAG](img/dag.png)

In a distributed version control system, each node represents a commit.  Each node has information about the changes that were made, as well as who its parents are.  A node is identified by a hashed ID value (typically SHA-1) that is generated based on the changes in the commit as well as the parent-child relationships.  A change to a commit node requires a new hash to be calculated.

## Cloning
A distributed version control system does not require a central server where the latest code is found, but in real-world applications, this often is the case.  

In centralized systems, retrieving the latest code entails copying the most recent versions of the sources files to the local development environment.  However, in a distributed system, a clone operation is performed, which brings the entire directed acycilic graph onto the local machine.  This approach is highly optimized for speed and performance, requiring less disc space than you would think.  This is the power of a distributed system, as as any machine that has cloned a repository can recreate that repositority in its entirety.

## Commits
In a distributed system, commits are at first local-only.  The new commit node has not been added to a central server or any other machine where the cloned repository resides.  When local commits are ready to be integrated with any centralized environment, those changes must be pushed to that environment.  

When new, concurrent changes have been made to the central server, a pull or fetch must be invoked.  This operation brings new additions to the local environment.  Often, this creates a conflict between the local environment and the latest version of code that was pushed to the central server.  

Because a node cannot change parents without a change in the hash, a conflict creates multiple heads:

![Conflict](img/multiHead.png)

In this case, the parent-child relationships have been preserved in each set of changes (nodes 4 and 10).  However, multiple heads are a problem.  For example, a build server would not be able to determine which head is the most recent version of the software to build or deploy. 

In this case, a merge must be performed, which is a new commit that draws both sets of changes together, restoring a single head in the repository while continuing to preserve the existing parent-child relationships:

![Merge](img/merge.png)

Just like before, this merge remains a local commit until it is pushed to the central server. 

## Merge Types

### Regular Merge
A regular merge creates a new node on the DAG that has two parents: the master branch and the feature branch.  This merge typically is required when concurrent work in a repository has occured before your feature branch is complete and merged back to master.  

### Fast-Forward Merge
Sometimes, no concurrent work is completed before a feature branch is ready to be merged back to master.  In this case, a "merge" is not actually necessary.  The merge can be completed by simply moving the master label from its current place to the head of the branch.  This merge does not create a new commit / node for the merge.

### Rebase
A rebase changes the history of the repository.  Rather than creating a new commit node for the merge, a rebase recreates the changes of the feature branch in master itself.  This creates new nodes on master with new hashes (the parent has changed), but contains the same changes that were in the branch.  A fast-forward merge is now performed. Often, commits are squashed during the rebase down to a single commit node.

Rebasing provides a linear history, but is misleading because nodes appear to have been created in chronological order. 

## Open Source
The following features of distributed version controls system are especially helpful for open source projects and workflows:

- Forks
- Pull Requests
- Branches

A typical for contributing to an open source project is:

- Fork the project
- Clone the repository locally
- Make a change (probably in a branch)
- Commit and push to the fork
- Issue a pull request from the fork to the original project

## Enterprise

### Benefits
Distributed version control systems have many benefits for large-scale, enterprise-level development teams:

#### Little and Often Commits
You can create many commits that only need to be pushed when your code is "ready", which typically means it meets standards, passes tests, etc.  Each commit is an intermediate save point, and allows easy rollback.  Many little commits can be rebased into a single commit for merge, if desired.  

#### Personal Branches
Branches in centralized servers are public and often long-lived.  In distributed systems, branches tend to be private, short-lived branches that are deleted after merge.  Short-lived branches enable other use cases, like spikes and refactoring branches.  Comitting or stashing changes allows for easy context switching between multiple units of work.  

#### Ad Hoc Teams
Feature branches and forks allow teams to quickly get up and running.  You can also pull branches from other developers machines.  

#### Complete Branching Flexibility
Distributed systems allow easy branching from any node in the graph.  You can use labels to mark key revisions to the repository.  It is easy to merge multiple branches together.  Strategies like Git-Flow help to manage branch complexity.  

#### Disconnected Working
Distributed systems allow for easy remote working.  Outsourced teams can fork a repository and submit pull requests to the original repo.  The pull request model allows easy enforcement of code review for any workflow.  

#### Eliminate Code Freeze
During any code freeze, you can work in local branches that are pushed after the freeze ends.

#### Automated Deployment
Pushes can triggers builds and deployments.  

### Limitations
However, there are also some limitations:

#### Large Repositories
Centralized systems allow partial get latest, which can be helpful for overly large repos.  In distributed systems, a clone operation gets everything.  Branch operations also branch everything.  

#### Large Files
Large files should be hosted elsewhere.  Even if a large file is committed and then removed in a distributed system, that operation would still be included in all the history of that repository.  

#### Exclusive Locks
Some files are not easily merged and support exclusive locking of those files.  Distributed systems often don't support exclusive locks.  