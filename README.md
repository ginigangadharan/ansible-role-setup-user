Role Name
=========

A simple role to deploy a user for ansible on managed node.

Requirements
------------

Access to remove machine with sudo or root access.

Role Variables
--------------

```
# username to be created on remote machine for ansible
remote_user: devops

# public key string for same user
remote_user_public_key: <public key string>
```

Dependencies
------------

None

Example Playbook
----------------

Call the role with username and public key and use it with privileged user for first time as below.

```
ansible-playbook setup-ansible.yaml -b -K -k -u root
```

**Sample playbook**
```
- hosts: servers
  become: true
  vars_files:
  vars:
    remote_user: devops
    remote_user_public_key: 'ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDPCgWXeSm2t9XJrvCMPMpr0TmhOvnS0e0kax05EeSLXTc98dv4ewP+9Mvc2Vl+2LifAK/FXZlpzexQugnHJ8oUbfjxiD0ZEQQhpV1pLkHp4zDyl4p+fneMtahCYhqkI0YPpN/RCGTxrWxppc65NXaHOGvt9O7bKJCQyR0LvUHbXUw4dqgd5OB2FxL6h0hbe4XxFgJ3Cl7GlSDe3ly14Tdh4ZdvqDxAbtGly1q9HHInWhBxFOpIFrKmN7d6+NhiJK0i5/a8MMmAaGvI0x5pSmM5Ehg+sns11gnt8tvt8MLdHI2SuTiBDLepkgF5CPc2lScH/lkiUbmvqIVKYlddhuKR devops@vm-towernode-10.lab.local'
  roles:
    - { role: setup-ansible-user }

```


License
-------

BSD

Author Information
------------------

This role was created by [Gini](https://www.iamgini.com).
