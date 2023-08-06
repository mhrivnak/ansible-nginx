nginx
=====

Deploys nginx and configures it for use as a reverse proxy on CentOS Stream and compatible distributions.

Requirements
------------

- developed on CentOS Stream 9

Role Variables
--------------

None

Dependencies
------------

None

Example Playbook
----------------

The following playbook will install nginx ready to be used as a reverse proxy
with TLS certificates from letsencrypt. The only piece to add is an nginx config
file for your site that uses the certificate.

```
- hosts: web_hosts
  become: true

  roles:
    - nginx
    - geerlingguy.certbot

  vars:
    certbot_admin_email: certs@example.com
    certbot_create_if_missing: true
    certbot_certs:
      - domains:
          - someapp.example.com
```

License
-------

GPLv3