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
    remote_user_public_key: '<public key string>'
  roles:
    - { role: setup-ansible-user }

```


License
-------

BSD

Author Information
------------------

This role was created by [Gini](https://www.iamgini.com).
