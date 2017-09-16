# tmux

## Colour scheme is corrupted
(2015/02/18)
tmux probably thinks it's stuck in a 16 colour terminal, run it with a `$TERM`
that it detects at 256 colour capable such as: `TERM=xterm-256color`. 

If apps inside tmux don't pick up the colour settings correctly, it's likely because the
`$TERM` setting _inside_ tmux is incorrect, try setting this with `set -g
default-terminal 'screen-256color'` in `~/.tmux.conf`.

## Reset tmux
(2017/09/16)

I had an issue with my keybindings so I deleted `~/.tmux.conf` and restarted
tmux but the issue still persisted and the old keybindings were still being
used. It turns out you need to run `tmux kill-server` to kill the tmux server
(`killall tmux` doesn't cut it) for bindings to be refreshed (i.e. if you've
removed bindings they'll still persist)

https://stackoverflow.com/questions/38295615/complete-tmux-reset
