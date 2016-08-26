ansible-role-zsh [![Build Status](https://travis-ci.org/mlangry/ansible-role-oh-my-zsh.svg?branch=master)](https://travis-ci.org/mlangry/ansible-role-oh-my-zsh)
=========

An Ansible role to install and configure oh-my-zsh

Requirements
------------

Git must be installed.
For requirements of oh-my-zsh see [Here ](https://github.com/robbyrussell/oh-my-zsh)

Role Variables
--------------

````yaml
oh_my_zsh_users:
  - "{{ ansible_user_id }}"
# -  { user: username, zsh_rc_file_path: zsh_rc_file_path }
oh_my_zsh_path: "~/.oh-my-zsh"
oh_my_zsh_rc_file_path: "~/.zshrc"

````

Dependencies
------------

None

Example Playbook
----------------

By default zsh is configured for connected user.

````yaml
- hosts: servers
  roles:
     - { role: mlangry.oh-my-zsh }
````

If you want to configure zsh for multiple users:

````yaml
- hosts: servers
  roles:
    - role: ansible-role-zsh
      zsh_users:
        - { user: user1, zsh_rc_file_path: zshrc1 }
        - { user: user2 }
        - user3
````

License
-------

MIT
