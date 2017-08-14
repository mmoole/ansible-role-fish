Role Name
=========
[![license][2i]][2p]
[![twitter][3i]][3p]

This is a fork of the role to install fish (2.2) and fisher originally made by [Alejandro Baez][1]

Description
-----------

Nothing too major. The role installs the shell [fish][4] with [fisher][5].
It is pretty barren for now except with those two options...

Role Variables
--------------

There are these variables with default values:

``` yaml
# user to add fish shell to and its path
user:
  name: "{{ ansible_user_id }}"
  home: "/home/{{ ansible_user_id }}"

# option to set activation for fish shell - or leave installed to use only on demand
fish_shell_activate: true

# option to replace shell or append to bash shell - only if activation is set to true
fish_append_to_bash: false

fish_fisherman_packages:
  - paths
  - edc/bass
  - nyarly/fish-bang-bang
  - ansible-completion
```

Requirements
------------

Needs git installed on remote machine, this is not checked for!


Usage
-----

To use the role, you need to give become access for the user you want to have the shell be installed and configured for. An example can be seen below:

``` yaml
- hosts: servers
    roles:
        - ansible-role-fish
```

Author Information
------------------

[Alejandro Baez][1]

[1]: https://keybase.io/baez
[2i]: https://img.shields.io/badge/license-BSD_2-green.svg
[2p]: ./LICENSE
[3i]: https://img.shields.io/badge/twitter-a_baez-blue.svg
[3p]: https://twitter.com/a_baez
[4]: http://fishshell.com/
[5]: https://github.com/fisherman/fisherman
[6]: https://galaxy.ansible.com/abaez/common
