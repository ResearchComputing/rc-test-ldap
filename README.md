# RC LDAP Test Service
This Dockerfile provides a test 389 service, configured to match the production RC LDAP. It is initialized with no user data.

## Usage Instructions
To build this container, run:
```
docker build --tag="dev/rcldap" .
```
After the container has been built, it can be run with the following command:
```
docker run --rm -d -p 10389:389 --name="ldap-server" dev/rcldap
```
