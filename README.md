wkhtmltopdf
=========

[![Build Status](https://travis-ci.com/fidanf/ansible-role-wkhtmltopdf.svg?branch=master)](https://travis-ci.com/fidanf/ansible-role-wkhtmltopdf)

Installs [wkhtmltopdf](https://github.com/wkhtmltopdf/wkhtmltopdf) (precompiled binary) and it's dependencies for **Debian/Ubuntu**.

Tested with :
- Debian 10.x :heavy_check_mark:
- Debian 9.x :heavy_check_mark:
- Ubuntu 20.04.x :heavy_check_mark:
- Ubuntu 18.04.x :heavy_check_mark:

Role Variables
--------------

```yaml
wkhtmltopdf_base_url: https://github.com/wkhtmltopdf/wkhtmltopdf/releases/download
wkhtmltopdf_version: "0.12.5" # the version to install
wkhtmltopdf_dependencies:
  - fontconfig

```

Example playbook
----------------

```yaml
---
- hosts: servers
  gather_facts: yes
  become: yes

  roles:
    - fidanf.wkhtmltopdf

```

License
-------

BSD / MIT
