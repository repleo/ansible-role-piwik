Ansible role - Piwik web analytics installer
=====

[![Build Status](https://travis-ci.org/repleo/ansible-role-piwik.svg?branch=master)](https://travis-ci.org/repleo/ansible-role-piwik)
[![Ansible Galaxy](http://img.shields.io/badge/galaxy-repleo.piwik-660198.svg?style=flat)](https://galaxy.ansible.com/repleo/piwik)

This role install and configures piwik. Piwik is an open-source web analytics platform.

Requirements
------------

This role requires Ansible 2.0 or higher and platform requirements are listed in the metadata file.

Role Variables
--------------

   # General config.
   piwik_hostname: piwik.example.com

   # SSL Configuration.
   piwik_ssl: no
   piwik_redirect_http_to_https: yes
   piwik_ssl_certificate: "/etc/nginx/ssl/piwik.crt"
   piwik_ssl_certificate_key: "/etc/nginx/ssl/piwik.key"

   # Database config.
   piwik_db_user: piwik
   piwik_db_password: piwik
   piwik_db_host: localhost
   piwik_db_name: piwikdb


Dependencies
------------

- repleo.nginx
- repleo.mysql

Example Playbook
----------------

Install piwik
```yaml
- { role: repleo.piwik,
     piwik_hostname: webtraffic.repleo.nl,
     piwik_ssl: yes,
     piwik_ssl_certificate: /etc/nginx/ssl/ssl.repleo.nl-chain.pem,
     piwik_ssl_certificate_key: /etc/nginx/ssl/ssl.repleo.nl.key
  }

```

License
-------

GPL v3 - (c) 2017, Repleo, Amstelveen

Author Information
------------------

Repleo, Amstelveen, Holland -- www.repleo.nl  
Jeroen Arnoldus (jeroen@repleo.nl)
