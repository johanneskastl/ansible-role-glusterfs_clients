![Ansible Lint](https://github.com/johanneskastl/ansible-role-glusterfs_clients/workflows/Ansible%20Lint/badge.svg)

glusterfs_clients
=========

Install packages and prepare a systemd unit for a glusterfs mount

Requirements
------------

You obviously need a glusterfs server on another machine, who's volume you want to mount...

Role Variables
--------------

- `glusterfs_server_name`: hostname of one of the glusterfs servers, e.g. `my-glusterfs-server-01`
- `glusterfs_volume_name`: name of the glusterfs volume (without leading slash), e.g.`gv1`
- `path_to_mount`: path where the glusterfs volume should be mounted, e.g. `/opt/glusterfs`

Optional variables:

- `force_ipv4_as_ipv6_not_available`: (Boolean) In case your machines do not
  have working IPv6, or DNS (or /etc/hosts) only return IPv4 addresses, you can
  force the usage of IPv4 for the client side (mount options) by setting this to
  `true`

Dependencies
------------

None

Example Playbook
----------------

    - hosts: servers
      roles:
         - role: 'johanneskastl.glusterfs_clients'

License
-------

BSD-3-Clause

Author Information
------------------

I am Johannes Kastl, reachable via kastl@b1-systems.de.
