[![Build Status](https://travis-ci.com/frite/ansible-role-recon-python3-tools.svg?branch=master)](https://travis-ci.com/frite/ansible-role-recon-python3-tools)

recon_python3_tools
=========

Ansible role to install python 2 tools.

Role Variables
--------------
The following variables need to be set.

```
clone_tools:
          altdns:
            name: bass
            url: https://github.com/Abss0x7tbh/bass.git
          sublist3r:
            name: Sublist3r
            url: https://github.com/aboul3la/Sublist3r.git
``` 
Handles the tools that you want to `git clone` in the server. 
```
pip_args:
          - bass
          - Sublist3r
```
Tools that offer `requirements.txt` files. 

```
setup_files:
  - Sublist3r
```
Tools that offer `setup.py` files
```
        soft_links:
          sublist3r:
            repo: bass
            soft_link: bass
            file: bass.py
```
Tools that are soft linked `ln`.

Dependencies
------------

It depends on `frite.recon_package_manager`.
If you run it on CentOS, you also need `geerlingguy.repo-epel` to deal with the EPEL release repo.


 Playbook
----------------

    - hosts: servers
      roles:
         - { role: ansible-role-recon-python2-tools, whatever_vars_here }

License
-------

BSD
