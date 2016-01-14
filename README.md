# Dev Machine Playbook

## Client

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
dnf install -y python2 python2-dnf libselinux-python yum-utils
echo 'fastestmirror=true' | tee -a /etc/dnf/dnf.conf
```
