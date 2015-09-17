Ansible fail2ban role
=====================

Ansible role to install and configure fail2ban on a host.

Requirements
------------

For each desired jail, you have to add the proper dict for configuration as well as the loop in the template. I haven't figured out a way yet to loop through nested dicts with jinja templates.

Role Variables
--------------

```yaml
# service
fail2ban_service_state: started
fail2ban_service_enabled: yes

# defaults
fail2ban_jail_default:
  bantime: 600
  maxretry: 4

# fail2ban_sshd
fail2ban_sshd:
  enabled: 'true'
  maxretry: '6'
```

Dependencies
------------

None.

Example Playbook
-------------------------

```yaml
- hosts: servers
  roles:
     - { role: archf.fail2ban }
```

License
-------

MIT

Author Information
------------------

Felix Archambault
