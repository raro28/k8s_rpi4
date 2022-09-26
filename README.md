# k8s_rpi4

Ping all without cfg

```
ansible all --key-file ~/.ssh/id_rsa -i inventory -m ping --user pi
```

Ping all with cfg

```
ansible all -m ping --user pi
```

Lists all

```
ansible all --list-hosts
```

Gather all facts

```
ansible all -m gather_facts
```

Gather single host facts
```
ansible all -m gather_facts --limit rpi03.home.lan
```