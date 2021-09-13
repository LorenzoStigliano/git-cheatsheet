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
