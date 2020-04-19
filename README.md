openemr-ansible
=========

This role installs OpenEMR releases to RHEL 8 and CentOS 8 systems. 

Requirements
------------

1. OpenEMR requires a MariaDB / Mysql database to connect to. This role does not setup or configure the database.
2. Ability to download to sourceforge.net (download links can be configured if it needs to be staged elsewhere)

Role Variables
--------------

Database Configuration
```
mysql_host_fqdn: 'db-example.example.com'
mysql_openemr_db_name: 'openemr'
mysql_openemr_user: 'openemr'
mysql_openemr_user_password: 'example-password'
mysql_openemr_user_host: "%"
mysql_openemr_user_priv: "{{ mysql_openemr_db_name }}.*:ALL,GRANT"
```

Initial OpenEMR Application User
```
mysql_openemr_initial_user: 'user-example'
mysql_openemr_initial_user_password: 'example-password'
```

OpenEMR Release
```
download_openemr_link: "https://sourceforge.net/projects/openemr/files/OpenEMR%20Current/5.0.2.1/openemr-5.0.2.tar.gz/download"
```

Dependencies
------------

No other roles are required to install this role.

If developing against this role the molecule test requires the following roles:
- diodonfrost.mariadb


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: openemr
      tasks:
        - name: Testing openemr-ansible role
          import_role:
            name: "openemr-ansible"
          vars:
            autoconfigure: true
    

License
-------

BSD

Author Information
------------------
Jeff Pullen
