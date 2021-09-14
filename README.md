# Git Cheatsheet

Git is a distributed revision contorl system -> a presistent map.

## 1. Values and keys

Any sequence of bytes are the value which are able to get a hash for that value which is our key. For example, "apple pie" is then mapped to a unique hexadecimal key:
- ``echo "apple pie" | git hash-object --stdin`` this is to see the hash for the string

## 2. Initalize a repo

1. ``git init`` initalize a new repo
2. ``git branch -m main`` rename the current branch from master to main
3. ``ls -a`` to see hidden directory

## 3. First commit

1. ``git status`` files and folders in project root
2. ``git add menu.txt`` then stage files 
3. ``git commit -m "first commit!"`` then commit
4. ``git log`` list of commits

## 4. Versioning

1. change a file 
2. ``git status`` will tell us that file has changed
3. ``git add`` file to the staging area
4. ``git commit -m "file has changed!"`` then commit the staged files

Now the second commit will have a parent which is the original, and points to the same object that has not changed.

## 5. Branches

A branch is a refrence to a commit.
``HEAD`` is a refrence to a branch.

- Create a new branch: ``git branch new_branch_name``
- Go to a new branch: ``git switch new_branch_name`` (switch is new) or ``git checkout new_branch_name``

When switching branches ``HEAD`` points to ``new_branch_name``. 

The branch restores the version of the file when the branch was made. You can think of a branch as bifurcation on the commit they where created.

### Merging branches

- Merge a branch when you are in main: ``git merge new_branch_name``

1. However, in many cases there are conflicts.
2. First edit the file that you want to merge.
3. ``git add file``
4. ``git commit`` in this case git knows that you are in the middle of a merge.

A merge is a commit with two parents.

When going back to to a commit, git gets the state of the project at **that** commit.

#### Special case of a merge

1. Fast-Forwards <br>
- Merging from ``main`` (``master``) to ``new_branch_name`` you can use `` git merge main`` now ``new_branch_name`` is the same at ``main``. Now ``main`` (``master``) and ``new_branch_name`` will point to the same commit.

2.  Detached HEAD  <br>
- ``git checkout commit_hash`` now HEAD points at a commit and **not** a branch. All the commits done with a detached HEAD all the objects are unreachable, no branch can go to these commits. Only acessible by hash. They will deleted by the garbage collector. <br>
- ``git checkout commit_hash`` then `` git branch unreachable`` now we can reach all of the commits with the detached HEAD and now they are all under the ``unreachable`` branch.
