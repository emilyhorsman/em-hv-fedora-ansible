# Dev Machine Playbook

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
dnf install -y redhat-rpm-config python2 python2-dnf python3-devel libselinux-python yum-utils
echo 'fastestmirror=true' | tee -a /etc/dnf/dnf.conf
```

### Notes

`pycrypto` needs the `redhat-rpm-config` and `python3-devel` packages or its
build will fail. Ensure you have all the `pycrypto` dependencies if you're
having difficulty installing Ansible 2.0 on Fedora.
