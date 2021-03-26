Role Name
=========

[![Actions Status](https://github.com/ome/ansible-role-ice/workflows/Molecule/badge.svg)](https://github.com/ome/ansible-role-ice/actions)
[![Ansible Role](https://img.shields.io/ansible/role/41081.svg)](https://galaxy.ansible.com/ome/ice/)

Install Zeroc Ice.

On Ubuntu and CentOS 8 this only installs the Ice binaries and required libraries under `/opt/ice/bin` (note this is a symlink).
CentOS 8 requires Ansible 2.8+ for Python 3 module support.


Role Variables
--------------

Optional (expert users only):
- `ice_install_devel`: Install Ice development packages, default `True`
- `ice_install_python`: Install Ice Python globally, default `True`, ignored on Ubuntu and CentOS 8 (always `False`)
- `ice_python_wheel`: URL to a python wheel package to be installed, ignored on Ubuntu and CentOS 8.
  You can use this to provide a precompiled ice-py package for 3.6 as an alternative to automatically compiling from the source package.
- `ice_binaries_symlink_dest`: Symlink the Ice binaries required by OMERO into this directory e.g. `/usr/local/bin` (Ubuntu and CentOS 8 only, must exist, if empty don't create symlinks)


Notes
-----
Note that 3.6 requires ice-python to be installed using pip, and will result in the installation of several development tools and libraries unless `ice_python_wheel` is provided.


Example Playbook
----------------

    - hosts: localhost
      roles:
        - role: ome.ice


Author Information
------------------

ome-devel@lists.openmicroscopy.org.uk
