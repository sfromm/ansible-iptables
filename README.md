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
- **ipv4_allowed_networks**: list of IPv4 addresses to allow all traffic
  from.  This defaults to `224.0.0.0/8`, the IPv4 multicast netblock.
- **ipv6_allowed_networks**: list of IPv6 addresses to allow all traffic
  from.  This defaults to `fe80::10` (link-local prefix) and `ff00::/8`
  (multicast prefix).
- **ipv4_blackhole**: list of IPv4 addresses to block.
- **ipv6_blackhole**: list of IPv6 addresses to block.

If you override **ipv4_allowed_networks** or **ipv6_allowed_networks**,
you are strongly encouraged to keep the defaults in place.  In
particular, IPv6 will not work well without those defaults allowed.

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
