# openldap-subordinate-AD
Initial configuration of OpenLDAP to glue AD DIS as suffix in OpenLDAP DIS

After successful startup of slapd (service slapd start) add initial objects to the database:

root@hostname:~# ldapadd -x -D cn=ldap_admin,dc=example,dc=org -w password_of_rootdn -f /etc/ldap/ldif/initial_o_units.ldif

Then you can connect to ldap using software like ldapadmin using cn=ldap_admin,dc=example,dc=org and it's password
