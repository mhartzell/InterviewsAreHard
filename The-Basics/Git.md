[<< Back to The Basics](index.md)

# Git
Git is a distributed version control system.  It is the most popular DVCS available today and was created by Linus Torvalds in 2005.

# Under the Hood
Git acts similarly to a file system, in that it stores snapshots of the entire project at each commit.  Umodified files do not get stored again but reference the most recent version of that file.  Because Git stores all snapshots, commits and history locally, most operations are very fast.

Everything in Git is check-summed to a 40-character SHA1 hash.  Everything in Git is stored by this hash.

## File Stages

- **Untracked** Files are not tracked by Git
- **Committed** Files are tracked by Git.
- **Modified** Changes to a file have been made.  WIP.
- **Staged** Changes are committed to local database.

## Git Projects

- **.git Directory** The compressed repository and its metadata
- **Working Directory** A single copy of the project (a checkout), pulled from the .git directory
- **Staging Area (Index)** Sits between working directory and git directory. Stages fixes that will be committed, which will then be committed back to the .git directory.

![Merge](img/gitProject.png)

# Commands
- `git --version` Version information
- `git config` Interact with configuration settings
- `git config --global` Interact with global configuration settings
- `git help` Quick command overview
- `git init` Create a new repo.
- `git clone` Clone entire repo to local environment
- `git pull` Retrieve latest commits from remote repository
- `git status` Show the status of changed files
- `git add` Add files to be tracked by git
- `git commit` Commit local changes to the repository
- `git push` Push commits to a remote repository
- `git log` Show a log of commits
- `git diff` Show file differences between commits
- `git checkout` Go back / forward in time to a previous version