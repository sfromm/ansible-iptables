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
    from.  This defaults to an empty list.
- **ipv6_allowed_networks**: list of IPv6 addresses to allow all traffic
    from.  This defaults to an empty list.
- **ipv4_blackhole**: list of IPv4 addresses to block.
- **ipv6_blackhole**: list of IPv6 addresses to block.
- **iptables_do_src_nat_postrouting**:  boolean for whether to do source
  NAT postrouting in the *nat* table.  One example of using this would
  be deploying something like [OpenVPN](https://openvpn.net).
- **ipv4_src_nat_network**: The source network to use for postrouting in
  the *nat* table.
- **ipv4_postrouting_output_interface**: Output interface to use for
  source NAT postrouting.  Defaults to *ansible_default_ipv4.interface*.
- **ip6tables_has_state_recent**: boolean for whether *ip6tables* supports the
  *state* and *recent* modules.  This defaults to *yes*, except for *EL5*
  where it is *no*.

The IPv4 template specifically allows traffic to the multicast address
range, `224.0.0.0/8`.  In a related fashion, the IPv6 template allows
traffic to the multicast address range, `ff00::/8`, and traffic to and
from the link local address range, `fe80::/10`.  IPv6 will not work if
you do not allow these address ranges.

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
