# git
## Object files
(2015/02/21)
Almost everything in git is stored as an object, these are stored in
`.git/objects` under the name `<hash (first two chars)>/<hash>`. Commits are
stored as objects with reference to the hashes of the files that the commit
contains, and the hash of the parent of the commit. If you want to see what is
inside a hashed file you can run `git cat-file -p <hash>` where `p` designates
pretty printing the contents
