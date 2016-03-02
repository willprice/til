# git
## Object files
(2016/02/21)
Almost everything in git is stored as an object, these are stored in
`.git/objects` under the name `<hash (first two chars)>/<hash>`. Commits are
stored as objects with reference to the hashes of the files that the commit
contains, and the hash of the parent of the commit. If you want to see what is
inside a hashed file you can run `git cat-file -p <hash>` where `p` designates
pretty printing the contents

## References
(2016/03/02)
`refs` are files whose contents is a SHA-1 value (referencing a specific
commit). `refs` are stored in `.git/refs/heads/<name>` (and tags, another form
of ref,  are stored in `.git/refs/tags`).

`git update-ref refs/heads/<name> <sha1>` will update the ref `<name>` to point
to commit `<sha1>`

What is *HEAD* (wouldn't you like to know!)? A symlink to the current branch
stored in `.git/HEAD`, it is literally a symlink, and acts as a pointer to a
branch. If you want to find out what a symbolic-ref like HEAD is pointing to run
`git symbolic-ref <name>`,  you can also change what it is pointing to: `git
symbolic-ref <name> <ref>` e.g. `git symbolic-ref HEAD refs/heads/master`
