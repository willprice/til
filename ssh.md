# SSH

## Tunneling ports from a remote server to your machine
(2016/03/10)

Let's say you've got mongodb (port 27017) running on a server called `dev`, but
you can't access it externally due to locking it down with a firewall. Running
`ssh -f -N -L 1234:127.0.0.1:27017` will forward the remote's port 27017 to your
machine's port 1234! `-f` forks SSH to run in the background, and `-N` tells it
not to execute a remote command (e.g. a shell by default)

You can even specify this in `~/.ssh/config` with a clause like:

```
Host dev-mongodb-tunnel
    HostName dev
    LocalForward 1234 127.0.0.1:27017
```

## Exiting unresponsive session
(2017/10/15)

Type `<Return> ~ .` in quick succession to exit an unresponsive session

## SSH Config multiple matching entry resolution
(2018/01/10)

If you have multiple matching configurations for a host in `.ssh/config` then
the first value obtained will be used, e.g.

```
Match host uni-desktop !exec "has-mac-addr 192.168.1.1 2c:56:dc:d2:90:37"
    ProxyJump proxy-jump-box
    HostName my-remote-machine

Host uni-desktop
    User my-user
    HostName 192.168.1.246
```

The `Match` clause has to be above the `Host` clause otherwise `uni-desktop`
will always have the HostName `192.168.1.246`
