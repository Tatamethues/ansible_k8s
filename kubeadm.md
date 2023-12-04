## 1. Ansible Inventory File
`cluster.init.yaml`
```yaml
all:
  vars:
    ansible_user: kube
# control
control:
  hosts:
    192.168.10.30:
      host_name: control
# worker nodes
nodes:
  hosts:
    192.168.10.31:
      host_name: node01
    192.168.10.32:
      host_name: node02
```
## 2. Prepare
> [!NOTE] If the fingerprints are not in the known_hosts, we can skip checking the host key in `ansible.cfg`
> ```
> [defaults]
> host_key_checking = false

### **run prepare.plays.yaml**

`ansible-playbook -i cluster.init.yaml prepare.plays.yaml -K`

-K stands for `--ask-become-pass`. In this demo, this will ask the password of user kube.

1. Copy local ssh key to servers
2. Change hostname. All hostnames are configured in inventory(see step 1 above).

