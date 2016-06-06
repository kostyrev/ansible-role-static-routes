static-routes
=========

This role can be used to configure static routes

Requirements
------------

None

Role Variables
--------------

static_routes should contain the desired set of static routes

Dependencies
------------

None

Example Playbook
----------------

    - hosts: servers
      vars:
        nics:
          - eth0
          - eth1
        static_routes:
          - "any net 10.16.0.0/16 gw {{ ansible_default_ipv4.gateway }}"
        nic_static_routes:
          - { gw: '10.1.0.1',
              nm: '255.255.252.0',
              ni: 'eth0',
              ad: '10.14.1.0' }
          - { gw: 172.16.0.254'',
              nm: '255.255.252.0',
              ni: 'eth1',
              ad: '172.16.0.1' }
          - { gw: '172.16.0.254',
              nm: '255.255.255.0',
              ni: 'eth1',
              ad: '172.23.0.1' }
          - { gw: '192.168.252.254',
              nm: '255.255.252.0',
              ni: 'eth2',
              ad: '192.168.4.0' }
 

      roles:
         - kostyrevaa.static-routes

License
-------

BSD

Contributing
------------------
 When send PR make sure your changes are backward-compatible.

Author Information
------------------

Aleksandr Kostyrev
