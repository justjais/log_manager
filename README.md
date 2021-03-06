log_manager
===========

# This content is currently under development and should not be considered production ready

An [Ansible](https://ansible.com) role to manage logs in many firewall devices.

Current supported list of providers:
* checkpoint

Requirements
------------
Red Hat Enterprise Linux 7.x, or derived Linux distribution such as CentOS 7,
Scientific Linux 7, etc

Functions
---------

* `forward_logs_to_syslog` - This forwards logs of the firewall device to an external syslog server
* `unforward_logs_to_syslog` - This unforwards logs of the firewall device to an external syslog server

Example Playbook
----------------

```
- hosts: checkpoint
  connection: httpapi

  tasks: 
    - include_role:
        name: log_manager
        tasks_from: forward_logs_to_syslog
      vars:
        syslog_server: 192.168.0.1
        checkpoint_server_name: test
        firewall_provider: checkpoint
```


License
-------

GPLv3

Author Information
------------------

[Ansible Security Automation Team](https://github.com/ansible-security)
