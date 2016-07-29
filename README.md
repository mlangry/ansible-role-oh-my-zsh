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
oh_my_zsh_user: "{{ ansible_user_id }}"
oh_my_zsh_path: "/home/{{ oh_my_zsh_user }}/.oh-my-zsh"
# oh_my_zsh_rc_file_source_path:
oh_my_zsh_rc_file_path: "/home/{{ oh_my_zsh_user }}/.zshrc"

````

Dependencies
------------

None

Example Playbook
----------------

````yaml
- hosts: servers
  roles:
     - { role: mlangry.oh-my-zsh }
````

If you want to configure oh-my-zsh for multiple users:

````yaml
- hosts: servers
  roles:
    - role: mlangry.oh-my-zsh
      zsh_user: user1
      zsh_rc_file_source_path: zshrc1

    - role: mlangry.oh-my-zsh
      zsh_user: user2
      zsh_rc_file_source_path: zshrc2
````

License
-------

MIT
