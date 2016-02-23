# Vim
## Exiting
(2016/02/16)

You can use `ZZ`, `:wq` or `:x` to save and exit a file, `:x` only writes if
there have been changes! `ZQ`, `:q!` exit the file without saving.

## Diffing between buffers
(2016/02/23)
Run `:diffthis` in a buffer to start diffing that file, if you want to diff all
open windows run: `:windo diffthis`, or open buffers: `:bufdo diffthis`

