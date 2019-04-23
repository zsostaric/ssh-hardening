Ansible SSH hardening role
=========

This role will reconfigure the currently installed SSH server (sshd).

Warning
------------

This role disables root login and allows only key-based authentication so make sure you have another user set up with key-based authentication.
The default SSH port will also be changed from 22 to 2244. If you want to keep the default port or customize the port, change the variable sshd_port in defaults/main.yml. 

Before applying the new configuration, the role will make a backup of the currently applied sshd_config.

Requirements
--------------

OpenSSH 6.7+ (the role will try to update OpenSSH to the latest version that is available in your repository).

Supported Systems
------------

Tested on CentOS 7.0.1406 and CentOS 7.6.1810.

Variables
--------------

Variables for sshd_config can be changed in defaults/main.yml.
Global variables can be changed in vars/main.yml

Example Playbook
----------------

    - hosts: servers
      roles:
         - ssh-hardening


