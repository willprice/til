# tmux

## Colour scheme is corrupted
(2015/02/18)
tmux probably thinks it's stuck in a 16 colour terminal, run it with a `$TERM`
that it detects at 256 colour capable such as: `TERM=xterm-256color`. 

If apps inside tmux don't pick up the colour settings correctly, it's likely because the
`$TERM` setting _inside_ tmux is incorrect, try setting this with `set -g
default-terminal 'screen-256color'` in `~/.tmux.conf`.
