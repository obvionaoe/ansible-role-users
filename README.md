Ansible Role: users
=========

A simple and minimal Ansible role to manage creation and initial configuration of users on Linux.

Requirements
------------

None.

Role Variables
--------------

Available variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
users_append: true
users_create_home: true
users_shell: /bin/bash
users_skeleton: /etc/skel
users_state: present
users_ssh_authorized_keys_state: present
```

These variables control the default values values for all users passed to the role.  

```yaml
users:
  - name: old_user
    state: absent
    
  - append: true
    create_home: true
    groups: wheel
    hush_login: true
    name: user
    password: 57r0ngPa55
    passwordless_sudo: true
    shell: /bin/bash
    skeleton: /etc/skel
    state: present
    ssh_authorized_keys:
      - ssh-key XXXXXXXXX
      - file: path/to/key/file1
        state: present
      - file: path/to/key/file2
        state: absent
```

A list of users and their desired configuration. It is an empty list by default and only the `name` is mandatory for each user.

Dependencies
------------

None.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
- hosts: servers
  roles:
      - users
```

License
-------

MIT

Author Information
------------------

This role was created in 2024 by [Luís Guimarães](https://obvionaoe.xyz).
