======================
pb.configuration.build
======================

---------------------------------------
Build a full VXLAN / EVPN configuration
---------------------------------------

junos-build
===========

This module will construct a full configuration for a Juniper device within a VXLAN / EVPN data center fabric.

Under construction

Example
-------

Here is a basic example of using the module to mange your resources in Apstra

.. code-block:: yaml

    ---
    ### ---------------------------------------------------------------------------
    ### REMOVE AND RECREATE CONFIGURATIONS
    ### ---------------------------------------------------------------------------
    - hosts: all
      connection: local
      gather_facts: False
      roles:
        - { role: cremsburg.junos-config-build }

