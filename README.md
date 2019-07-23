# cygwin_ansible
install  cygwin  on widows  and  ansible pip install

### Export ansible directory config  
```
export ANSIBLE_HOME="/home/XXX/ansible"
export ANSIBLE_INVENTORY="/home/XXX/ansible_hosts"
```
cygwin  connect ssh-key error.
```
ansible all -m ping  --private-key ~/.ssh/ansible -u ansible
Server01 | UNREACHABLE! => {
    "changed": false, 
    "msg": "Failed to connect to the host via ssh: mm_send_fd: sendmsg(2): Connection reset by peer\r\nmux_client_request_session: send fds failed", 
    "unreachable": true
}
```
export line shell command and add ansible.cfg
```
export ANSIBLE_SSH_ARGS="-o ControlMaster=no"
```
ansgible.cfg
```
[ssh_connection]
ssh_args = -o ControlMaster=no


```
