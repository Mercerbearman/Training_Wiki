# How Git Works

**Location** - [How Git Works](https://app.pluralsight.com/library/courses/how-git-works/table-of-contents)

**Brief** - This course teaches how git works under the hood.  It talks in details about how the commits/files are stored in the git repository.  It explains Branching/Merging.  It gives a lot of detail on the under the hood things that git does when running its commands.

**Lessons Learned**:

- Git Objects:

  - Blobs: Hashed data that git tracks.  It hashes the contents of the files, not the names.  That way two files with the same contents will point to the same Blob in the repo.
  - Trees: Directory stored in git that points to blobs and other trees.  This is how all objects are related to each other through commits.
  - Commits: Object that contains commit information:
    - Commit Message
    - Author
    - Committer
    - Parent(s) - 0 or more.
    - Date
    - Tree SHA-1
  - Tags: Object that points to an explicit SHA-1 commit value from the git database.
- Git Commands:
  - git count-objects: This shows how many files are part of the git repository, and the total size the repo takes up.
  - git cat-file -p *{hash of object}*: This will uncompress and print the git object in question in human readable output.
- Merging Strategy: **Prefer Merge**.  Rebasing is super dangerous if you have already published data to the remote git repository.  You should only rebase to clean up commit history *prior* to pushing upstream.
- Branches: Plan text file pointing to a specific commit SHA.
- Pull: Git Pull == git fetch + git merge in one command.
- Pull prior to Push: Always pull prior to pushing.  Fix merge conflicts in your local work space and then commit whatever changes need to be made.  Then push.
