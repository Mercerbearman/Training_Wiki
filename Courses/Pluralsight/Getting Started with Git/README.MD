# Getting Started with Git

**Location** - [Getting Started with Git](https://app.pluralsight.com/library/courses/getting-started-git/table-of-contents)

**Brief** - High level of how git works.  Talks about differences between the repository, staging area, and working directories.  Recommend this for a better understanding on how to **use** git.

**Lessons Learned**:

- Three Stages of Files:
  - Committed: Files already stored in the repository.
  - Modified: Files that are modified in the work space (local directory) but are not marked for inclusion in a future commit yet.
  - Staged: Files marked for inclusion into the repository on the next commit.

- Three Main parts of Git:
  - Working Directory: Single copy aka *checkout* of a single git commit.  Modified files reside here.
  - Staging Area (Index): Sits between working directory and repository.  You build up changes and take a **snapshot** with *git add* command.  This hashes all the files **at the time of the snapshot** and includes these files/mods in the next *git commit* command.
  - .git directory: The git repository.  Mirrors remote server data.  Git stores metadata here.

- Git Commands:
  - git config: Allows configuration of git configuration settings.  You can change user name, email, etc. data here for the local (this repo) or global (all git repos) on your machine.
  - git add: Takes a snapshot of the files/mods in the working directory and places them in the staging directory to be ready for next commit.
  - git commit -m "*commit message*": Commits files/mods that are in the staging area to the repository.
  - git branch *{new branch name}*: Create a new branch with name specified.  
  - git checkout: Checkout a branch or commit SHA and refresh the working directory with the files that map to that commit.

  - git checkout -b *{new branch name}*: Create a new branch with the name, and immediately check it out.
  
  - git clone *{url}* *{local folder name}*: Clones a git repository at the link specified.

  - git push: Pushes local changes to the remote tracked repository.  Pull prior to pushing.
  
  - git pull: Pulls down changes from the remote repository and merge them in if required.
  
  - git fetch: Pulls down changes but doesn't merge.  Simply update the git Index, and not the workspace.
  - git rm *{file/directory}*: Removes and stops tracking the file/directory specified.  Git will remove these items out of its index.

- Git Files:
  - .gitignore file: This file is a filter for the files that git will track by default.  You can tell it to omit files or directories and it will not track them.  **Note**: this only works for files that git is not currently tracking.  If it is already in the index (Repository) and you add it to this file, git will keep tracking it.  You need to remove it from the index first with *git rm **file***.
  
  - .gitattribute file: This file tells git how to work with certain file types.  You can specify it to treat files as binary or text based on convention/names.
