# Ansible Playbook

This Playbook will install a Docker node for Jenkins on CI.

## Preparation
The **[ci-docker]** paragraph of `hosts` must contain a list of the CI nodes on
which to install Docker. The CI nodes should be created from the standard CI
Ubuntu 16.04 template. The nodes must allow the *ci* user to use `sudo`. The
file `group_vars/ci-docker.yml` defines how the *ci-ssh.inria.fr* ssh proxy will
be used to connect to nodes.

## Invocation
The playbook can be invoked using
```
ansible-playbook --inventory-file=hosts \
    --user=ci --ask-pass --become --ask-become-pass \
    ci-docker.yml
```
