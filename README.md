# Ansible

### Prerequisites

In the `/etc/ansible/hosts` file for the host machine, we expect something like the following:

```shell script
[example]
127.0.0.1:2222 ansible_ssh_private_key_file={path_to_vagrant_folder}/.vagrant/machines/default/virtualbox/private_key
```

In this file:
- `[example]` is the target server group
- `127.0.0.1:2222` is the ip address of one hostname, in this case the ssh port is mapped to `2222`
- `ansible_ssh_private_key_file` allows us to specify the ssh key to use with this machine

### Running

Assuming that the ssh user is `vagrant` and the ssh keys are already loaded in the ssh-agent, or setup in the ansible hosts file: 
```
ansible-playbook playbook.yml -u vagrant
```
