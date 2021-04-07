# RC LDAP Test Service
This Dockerfile provides a test 389 service, configured to match the production RC LDAP. It is initialized with no user data. Possible DOMAINS: curc, cu, csu.

## Usage Instructions
To build this container for csu ldap, run:
```
docker build --tag="dev/rcldap" --build-arg DOMAIN=csu .
```
After the container has been built, it can be run with the following command:
```
docker run --rm -d -p 10389:389 --name="ldap-server" dev/rcldap
```

Command to add adam.ldif to ldap:
```
ldapadd -D "cn=Directory Manager" -xw ${DOMAIN}_password -f /tmp/adam.ldif
```
