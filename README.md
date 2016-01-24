Ansible fail2ban role
=====================

Ansible role to install and configure fail2ban on a host.

Requirements
------------

None

Role Variables
--------------

```yaml
# service
fail2ban_svc_state: started
fail2ban_svc_enabled: yes

# defaults
fail2ban_jail_default:
  bantime: 600
  maxretry: 3

fail2ban_jails:
  - name: fail2ban_sshd:
    enabled: 'true'
    maxretry: '5'
```
`fail2ban_jails` is a list of jails to insert in template. Each list element will
create a new section in config file.

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
