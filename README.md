Ansible Role Fish
=========
[![license][2i]][2p]
[![twitter][3i]][3p]

This is a fork of an [Ansible role][7] to install fish and fisher,  originally made by [Alejandro Baez][1]

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

# set the major version of fish to be installed, this is not used by all package managers
fish_major_version: 3

# set fisher package manager packages to install (formerly known as fisherman)
# you can also install packages from https://github.com/oh-my-fish
# see also: https://github.com/jorgebucaran/fisher
fish_fisherman_packages:
  - edc/bass
  - nyarly/fish-bang-bang
  - nyarly/fish-lookup
  - laughedelic/pisces
  - jbonjean/re-search
  - jorgebucaran/fish-bax

# set fish configuraton file
#fish_config: |
  # fish configuration file {{ ansible_managed }}


# or set it to lookup your file
# fish_config: "{{ lookup('file', '../../../templates/config.fish') }}"
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

Useful
------

  * See http://fishshell.com/ for more information and documentation.
  * set full path in prompt per entering ```set -U fish_prompt_pwd_dir_length 0```

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
[7]: https://github.com/abaez/ansible-role-fish
