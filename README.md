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
dnf install -y redhat-rpm-config python2 python2-dnf python3-devel libselinux-python yum-utils
echo 'fastestmirror=true' | tee -a /etc/dnf/dnf.conf
```

### Notes

`pycrypto` needs the `redhat-rpm-config` and `python3-devel` packages or its
build will fail. Ensure you have all the `pycrypto` dependencies if you're
having difficulty installing Ansible 2.0 on Fedora.

#### Proxy

This installation starts a nice copy of dnsmasq. Client machines should
probably have a file like `/etc/resolver/pxy` with contents like

```
nameserver 192.168.1.6
```

That will make this wonderful and useful. Replace `192.168.1.6` with whichever
IP address this dev server is running on.
