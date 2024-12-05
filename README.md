# Server Role Apache

Submodule for server ansible playbook. Install Apache, copy conf files, enable sites.


## How to use it in my playbook?

Add submodule into your playbook repo:
```
git submodule add https://github.com/syone/server-role-apache.git roles/apache
```

Example:
```
---
  - hosts: all
    become: true
    become_user: root
    become_method: sudo

    roles:
      - role: apache
        vars:
          apache_sites:
            - domain: foo.com
              directory: /var/www/foo.com
            - domain: bar.com
              directory: /var/www/bar.com
```

Vhosts must be placed into ```files/apache``` directory:
```
your-playbook-directory/
|-- files/
    |-- apache/
        |-- foo.com.conf
        |-- bar.com.conf
```