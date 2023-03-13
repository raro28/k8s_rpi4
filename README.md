# k8s_rpi4

Ping all without cfg

```
ansible all --key-file ~/.ssh/id_rsa -i inventory -m ping --user pi
```

Ping all with cfg

```
ansible all -m ping
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

Update cache (will fail)
```
ansible all -m dnf -a update_cache=true
```

Update cache (elevate privileges)
```
ansible all -m dnf -a update_cache=true --become --ask-become-pass
```

Perform full upgrade
```
ansible all -m dnf -a upgrade=full --become --ask-become-pass
```
Reboot
```
ansible all -m reboot --become --ask-become-pass
```

Install requirements
```
ansible-galaxy collection install -r ./collections/requirements.yml
```

Apply full upgrade play-book
```
ansible-playbook --ask-become-pass site.yml
```

Shutdown
```
ansible all -m community.general.shutdown --become --ask-become-pass
```

Get mac address
```
ansible all -m shell -a 'ip add show eth0 | grep ether'
ansible all -m shell -a 'ip add show wlan0 | grep ether'
```