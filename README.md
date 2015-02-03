# Bash firewall

Scripts for generating iptables rules.

## Checkout

    git clone https://github.com/deric/bash-firewall.git /root/.firewall && source /root/.firewall/install

## Usage

Main firewall config should be located in `~/.fw/rules`

opening port
```
open_port tcp 22
```
will generate command:

```
/sbin/iptables -A input_new -p tcp -m multiport --destination-port 22 -j ACCEPT
```

`iptables` command is aliased as `ipt`

```
ipt -A INPUT -s 127.0.0.1 -j ACCEPT
```


Generate preview of iptables commands which will be applied
```
$ fw
```

apply firewall rules:
```
$ fw --apply
```

permanently saves (iptables-persistent)
```
$ fw --save
```

