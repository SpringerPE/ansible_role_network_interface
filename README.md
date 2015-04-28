network_interface
=================

NOTE: This is a rip-off os the role: https://github.com/bennojoy/network_interface/tree/master
DO NOT used, we should use the other one https://bitbucket.org/springersbm/ansible_role_pe_network

This roles enables users to configure various network components on target
machines. The role can be used to configure:

- Ethernet interfaces
- Bonded interfaces
- Network routes


Requirements
------------

This role requires Ansible 1.4 or higher, and platform requirements are listed
in the metadata file.

Role Variables
--------------

The variables that can be passed to this role and a brief description about
them are as follows:

    # The list of ethernet interfaces to be added to the system
    network_ether_interfaces: []

Note: The values for the list are listed in the examples below.


