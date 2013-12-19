kerberos_server
===============

This role installs the Kerberos server on the target host.

The role deploys the Kerberos server and creates a new realm as specified
in the parameter. It also creates a default admin user which can be used to
manage this Kerberos server. The default admin name can be specified via
"kadmin_user" and password via "kadmin_pass".

Requirements
------------

This role requires Ansible 1.4 or higher, and platform requirements as listed
in the metadata file.

Role Variables
--------------

The variables that can be passed to this role and a brief description about
them are as follows:

    realm_name: EXAMPLE.COM      # The realm name for the kerneros server
    kdc_port: 88                 # The port in which kdc should listen
    master_db_pass: foobar       # Password for the master Kerberos database
    kadmin_pass: foobar          # Password for the Kerberos admin
    kadmin_user: benz            # Username for the Kerberos server

Examples
--------

Following is an example which deploys are Kerberos server with Realm as
BENNO.COM and a admin user "root" and password "foobar"

    - hosts: all
      roles:
      - { role: kerberos_server,
          realm_name: "BENNO.COM",
          kadmin_user: "root",
          kadmin_pass: "foobar" }

Dependencies
------------

None

License
-------

BSD

Author Information
------------------

Benno Joy

