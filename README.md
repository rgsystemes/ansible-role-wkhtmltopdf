wkhtmltopdf
=========

Installs [wkhtmltopdf](https://github.com/wkhtmltopdf/wkhtmltopdf) (precompiled binary) and it's dependencies for **Debian/Ubuntu**.

Tested with :
- Debian 11.x :heavy_check_mark:
- Ubuntu 20.04.x :heavy_check_mark:

Role Variables
--------------

```yaml
# Wkhtmltopdf installation apt requirements
wkhtmltopdf_dependencies: 
  - fontconfig
# The repository to download from
# Use https://github.com/wkhtmltopdf/wkhtmltopdf/releases/download/ for older releases
wkhtmltopdf_base_url: https://github.com/wkhtmltopdf/packaging/releases/download/
# Wkhtmltopdf version, including release number 
wkhtmltopdf_version: 0.12.6.1-2
# This is a wildcard variable allowing the force a different distribution name than the destination host 
# wkhtmltopdf_os_release: ''
# GitHub tag to set for correct URL for some releases
# wkhtmltopdf_tag: ''
```

Example requirements file
--------------------
```yaml
---
- src: https://github.com/rgsystemes/ansible-role-wkhtmltopdf
  name: rgsystem.wkhtmltopdf
  version: master
  
```

Example playbook
----------------

```yaml
---
- hosts: servers
  gather_facts: yes
  become: yes

  roles:
    - name: rgsystem.wkhtmltopdf
      vars: 
        # Variables aiming for 0.12.5 installed version with patched qt on Debian 11
        wkhtmltopdf_base_url: https://github.com/wkhtmltopdf/wkhtmltopdf/releases/download/
        wkhtmltopdf_version: 0.12.5
        wkhtmltopdf_os_release: buster # No download links are available for bullseye, fallbacks to 'buster'
        wkhtmltopdf_tag: 0.12.5-1
```

License
-------

BSD / MIT
