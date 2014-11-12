Iptables
=========

Ansible role to manage iptables rules.

Requirements
------------

No external dependencies.

Role Variables
--------------

The *iptables* role has the following variables that can be overridden
by inventory:

- **bridge_physdev**: boolean for whether to enable bridging on physical
    interfaces.
- **ip_allowed_tcp_ports**: list of TCP ports to allow connectivity to.
    This should be used for services on the host.
- **ip_allowed_udp_ports**: list of UDP ports to allow connectivity to.
    This should be used for services on the host.
- **ipv4_allowed_networks**: list of IPv4 addresses to allow all traffic from.
- **ipv6_allowed_networks**: list of IPv6 addresses to allow all traffic from.
- **ipv4_blackhole**: list of IPv4 addresses to block.
- **ipv6_blackhole**: list of IPv6 addresses to block.


Dependencies
------------

No role dependencies.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: sfromm.iptables }

License
-------

GPLv2

Author Information
------------------

See https://github.com/sfromm
