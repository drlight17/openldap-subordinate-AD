# openldap-subordinate-AD
Initial configuration of OpenLDAP to glue AD DIS as suffix in OpenLDAP DIS
Using Ubuntu 18.04 TLS
1) Install OpenLDAP: # apt-get install slapd ldap-utils -y
2) Enable OpenLDAP on startup: # systemctl enable slapd
3) Copy files from this repo with rewrite
4) Start OpenLDAP: # systemctl start slapd
5) After successful startup of slapd (service slapd start) add initial objects to the database do:

root@hostname:~# ldapadd -x -D cn=ldap_admin,dc=example,dc=org -w password_of_rootdn -f /etc/ldap/ldif/initial_o_units.ldif

Then you can connect to ldap using software like ldapadmin using cn=ldap_admin,dc=example,dc=org and it's password

You could generate hashed password with command:

slappasswd -s password -h {SSHA}
