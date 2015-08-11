openvpn-server
==============

This role aims to provide an easy-to-use (yet flexible) OpenVPN server configuration.

It is designed to work together with openvpn-client ; this way it can generate every private key on the right computer and never move them around, which is better for security reasons.

Requirements
------------

At the moment, only portage is supported. Adding support for other package managers should be trivial, though.

Role Variables
--------------

* `openvpn_server_proto`: Protocol to use
Default: udp

* `openvpn_server_port`: Port to which the server should bind
Default: 1194

* `openvpn_server_dev`: Device to create, or use if it already exists. Please note at the moment it supports only TAP-based VPNs
Default: tun

* `openvpn_server_home`: Directory in which to place configuration files
Default: /etc/openvpn

* `openvpn_server_user`: User to run OpenVPN with (will be created if non-existent)
Default: openvpn

* `openvpn_server_group`: Group to run OpenVPN with (will be created if non-existent)
Default: openvpn

* `openvpn_server_ca_cn`: CN of the OpenVPN CA
Default: OpenVPN-CA

* `openvpn_server_key_cn`: CN of the OpenVPN server key
Default: OpenVPN-server

* `openvpn_server_ca_gen`: Configures the way of generating the CA key
Default: rsa:3072

* `openvpn_server_key_gen`: Configures the way of generating the server key
Default: rsa:3072

* `openvpn_server_dh_size`: Configure the number of bits of Diffie-Hellman parameters
Default: 2048

Tags
----

* `openvpn-server-pkgs`: Installs required packages

* `openvpn-server-user`: Add asked user and group if needed

* `openvpn-server-genkeys`: Generates CA and server keys

* `openvpn-server-config`: Configures OpenVPN server

Example Playbook
----------------

TODO

License
-------

GPLv3

Author Information
------------------

If needed, you can contact me at <leo@gaspard.io>.
