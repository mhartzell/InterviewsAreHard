[<< Back to The Basics](index.md)

# Version Control
(Todo)

The first generation of version control used file locking (SCCS, RCS).  The second generation become centralized, allowing concurrent edits and requiring merges before commit (CVS, Vault, TFS, etc).  In the third generation, version control became distributed (Mercurial, Git, etc).

# Distributed Version Control

## Directed Acyclic Graph (DAG)
A graph is composed of nodes and edges.  Some edges are directed, signifying a parent-child relationship.  A node with no parents is a root.  A child can also be called a branch.  When a node has more than one parent, it is a merge.  A node with no children is called a head.  In an acyclic graph, you cannot return to your node of origin by following the directed edges in the graph.

