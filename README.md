ansible-role-ufw
=========

Safe-ish UFW firewall reload that will reset if connection is lost.

Requirements
------------

Ansible 2.3, for persistant connections.

Role Variables
--------------

None.

Dependencies
------------

None.

Example Playbook
----------------

After changing some UFW rules, but before reloading, call this role.

    - hosts: servers
      pre_tasks:
      - name: Delete OpenSSH rule
        ufw:
          rule: allow
          name: OpenSSH
          delete: True
      roles:
         - { role: jpmahowald.ansible-role-ufw }

License
-------

GPLv3

Author Information
------------------

John Mahowald

