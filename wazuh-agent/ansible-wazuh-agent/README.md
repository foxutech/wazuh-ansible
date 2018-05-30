Ansible Playbook - Wazuh agent
==============================

This role will install and configure an Wazuh Agent.

OS Requirements
----------------

This role is compatible with:
 * Red Hat
 * CentOS
 * Fedora
 * Debian
 * Ubuntu


Role Variables
--------------

* `wazuh_managers`: Collection of Wazuh Managers' IP address, port, and protocol used by the agent
* `wazuh_agent_authd`: Collection with the settings to register an agent using authd.

Playbook example
----------------

The following is an example how this role can be used:

    - hosts: all:!wazuh-manager
      roles:
        - ansible-wazuh-agent
      vars:
        wazuh_managers:
          - address: 127.0.0.1
            port: 1514
            protocol: udp
        wazuh_agent_authd:
          enable: true
          port: 1515
          ssl_agent_ca: null
          ssl_auto_negotiate: 'no'
