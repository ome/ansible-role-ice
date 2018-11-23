Role Name
=========

[![Build Status](https://travis-ci.org/openmicroscopy/ansible-role-ice.svg)](https://travis-ci.org/openmicroscopy/ansible-role-ice)
[![Ansible Role](https://img.shields.io/ansible/role/14761.svg)](https://galaxy.ansible.com/openmicroscopy/ice/)

Install Zeroc Ice.


Role Variables
--------------

Required:
- `ice_version`: The Ice version, 3.6

Optional (expert users only):
- `ice_install_devel`: Install Ice development packages, default `True`
- `ice_python_wheel`: URL to a python wheel package to be installed.
  You can use this to provide a precompiled ice-py package for 3.6 as an alternative to automatically compiling from the source package.


Notes
-----
Note that 3.6 requires ice-python to be installed using pip, and will result in the installation of several development tools and libraries unless `ice_python_wheel` is provided.
The pip version is required in major.minor.patch form so `vars/ice-3.6.yml` will need to be updated whenever there is a new patch release.


Example Playbook
----------------

    - hosts: localhost
      roles:
        - role: openmicroscopy.ice
          ice_version: "3.6"


Author Information
------------------

ome-devel@lists.openmicroscopy.org.uk
