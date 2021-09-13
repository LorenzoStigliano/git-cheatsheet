# Git Course

Git is a distributed revision contorl system -> a presistent map.

## Values and keys

Any sequence of bytes are the value -> then we get a hash for that value which is our key

"apple pie" -> unique hexadecimal key

echo "apple pie" | git hash-object --stdin (this is to see the hash for the string)

## Sorting

git init (initalize a new repo)

git branch -m main (rename the current branch)

ls -a (to see hidden directory)

## First commit

1. "git status" files and folders in project root
2. first you need to stage files: git add menu.txt 
3. git commit -m "first commit!"
4. "git log" list of commits

## Versioning

1. First change a file 
2. "git status" will tell us that file has changed
3. "git add" file to the staging area
4. "git commit" 

now the second commit will have a parent which is the original, and points to the same object that has not changed.
