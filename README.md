ansible-role-laniakea-tools
===========================

Role for the installation of flavor's tools and workflows on laniakea galaxy instances.

Tested on:

-  CentOS7

Ansible version: 2.9.4

Requirements
------------

python3 pip3 libselinux-python3

Role Variables
--------------

- ``galaxy_flavors_url:``github repository containing flavors (default: ``https://github.com/pmandreoli/Galaxy-flavours``)
 
- ``galaxy_flavors_tag:`` repository branch name (default ``test``)
 
- ``galaxy_tools_base_dir:`` directory used to store galaxy flavors YAML files (default: ``/data``)
 
- ``galaxy_flavors_dir:``  directory to clone the repo in (default: ``'{{ galaxy_tools_base_dir }}/Galaxy-flavours'``)
 
- ``galaxy_flavor:`` galaxy-testing galaxy flavor to install (default: ``galaxy-minimal``)
 
- ``laniakea_galaxy_server_dir:``  galaxy dir that contain run.sh script (default: ``/home/galaxy/galaxy/server``)
 
- ``laniakea_galaxy_venv_dir:`` path to galaxy virtualenv (default: ``/home/galaxy/galaxy/venv``) 

- ``laniakea_galaxy_config_file:``  path to galaxy config file (default:``/home/galaxy/galaxy/config/galaxy.yml``)
 
- ``role_debug:`` bool debug variable (default: ``false``)

- ``create_galaxy_admin:`` (default:`` true``)

- ``GALAXY_ADMIN_USERNAME:`` (default:``admin``)

- ``GALAXY_ADMIN_PASSWORD:`` (default:``galaxy_admin_password``)

- ``galaxy_admin_api_key:`` galaxy istance admin api_key (default:``GALAXY_ADMIN_API_KEY``)


Dependencies
------------

- role: [ansible-role-laniakea-galaxy](https://github.com/Laniakea-elixir-it/ansible-role-laniakea-galaxy)


Example Playbook
----------------

```

--- 
- hosts: galaxyservers
  become: true
  vars:
    galaxy_flavor: "galaxy-testing"
    galaxy_admin_api_key: "admin_key"
    role_debug: true
  roles:
    - ansible-role-laniakea-tools
```

License
-------

MIT

Author Information
------------------
Pietro Mandreoli
email: pietro.mandreoli@unimi.it
