# openldap-subordinate-AD
Initial configuration of OpenLDAP to glue AD DIT as suffix in OpenLDAP DIT
Using Ubuntu 18.04 TLS
1) Install OpenLDAP: # apt-get install slapd ldap-utils -y
2) Enable OpenLDAP on startup: # systemctl enable slapd
3) Copy files from this repo with rewrite
4) Start OpenLDAP: # systemctl start slapd
5) Add initial objects to the database: ldapadd -x -D cn=ldap_admin,dc=example,dc=org -w password_of_rootdn -f /etc/ldap/ldif/initial_o_units.ldif
6) Connect to ldap using software like ldapadmin using cn=ldap_admin,dc=example,dc=org and it's password

You could generate hashed password with command:

slappasswd -s password -h {SSHA}

You could also generate dynamic configuration based on the slapd.conf file, make sure you have created slapd.d directory with write for openldap user rights:

slaptest -f /etc/ldap/slapd.conf -F /etc/ldap/slapd.d

After config generated check /etc/defaults/slapd for proper config file or directory setting

See changed core schema in etc/ldap/schema - sn attr is now uncertain!

See changed misc schema in etc/ldap/schema - nismailalias has description attr now!
