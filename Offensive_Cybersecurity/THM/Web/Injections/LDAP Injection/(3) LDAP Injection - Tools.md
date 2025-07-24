#LDAP #ActiveDirectory #WebInjection #WEB 
## ldapsearch

- This tool allows a user to query and modify the LDAP directory from the command line, making it a valuable resource
- Part of the OpenLDAP suite
==EX:==
```shell
 ldapsearch -x -H ldap://10.10.101.206:389 -b "dc=ldap,dc=thm" "(ou=People)"
```

