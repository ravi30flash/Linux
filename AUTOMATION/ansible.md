# Ansible

### Features
1. Owned by Redhat
1. Python based
1. Agentless : doesn't requires any daemon service
1. SSH 
1. OpenSource
1. works on pushin the configurations


## module in ansible
 - ansible.builtin.assemble
 - ansible.builtin.add_host
 - ansible.builtin.fetch : fetch files from remote nodes
 - ansible.builtin.file : manage files from file properties
 - ansible.builtin.template
 - ansible.posix.synchronize : an alternative to rsync 
 - ansible.builtin.copy : an alternative to rsync 

[more modules ...](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/index.html)

## how to copy file in ansible
```yaml
---
    - name: Copy file with owner and permissions
    ansible.builtin.copy:
        src: /srv/myfiles/foo.conf
        dest: /etc/foo.conf
        owner: foo
        group: foo
        mode: '0644'

```

















