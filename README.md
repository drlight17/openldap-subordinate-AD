# openldap-subordinate-AD
Initial configuration of OpenLDAP to glue AD DIS as suffix in OpenLDAP DIS

After successful startup of slapd (service slapd start) add initial objects to the database:
ldapadd -x -D cn=ldap_admin,dc=example,dc=org -w secret -f /etc/ldap/ldif/initial_o_units.ldif
