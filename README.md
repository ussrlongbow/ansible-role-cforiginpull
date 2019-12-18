cforiginpull
============

Ansible role deploys CLoudflare's Origin Pull certificate required for Full SSL mode operation.  
Optionally can copy extra certificates (for example issued by CF for your origin) to the same directory

Example Playbook
----------------

```
- hosts:
    - origin_server
  become: yes
  roles:
    - role: ussrlongbow.cforiginpull
      cfpull_path_dir: "/etc/ssl/cloudflare"
      cfpull_extra_certs:
        - "{{ playbook_dir }}/certs/cloudflare/my.domain.com.crt"
        - "{{ playbook_dir }}/certs/cloudflare/my.domain.com.key"
# This will copy CF Origin Pull cert + your certs to "/etc/ssl/cloudflare"
```

License
-------

[MIT License](./LICENSE)