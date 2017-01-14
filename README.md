# Fedora Machine Playbook

## Client

Remember to add an `em-hv-fedora` config to `~/.ssh/config`.

```
ansible-playbook playbook.yml -i 'em-hv-fedora,' -K
```


Or if running locally on the target dev machine (server):

```
ansible-playbook playbook.yml -i 'localhost,' -c local -K
```

## Server

You should probably do these ol’ things on the server first

```
dnf update
```

After running the playbook initially, remember to:

```
root@localhost ~# passwd
root@localhost ~# passwd emily
```
