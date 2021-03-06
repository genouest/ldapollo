[![Docker Repository on Quay](https://quay.io/repository/genouest/ldapollo/status "Docker Repository on Quay")](https://quay.io/repository/genouest/ldapollo)

# ldapollo

A Docker image allowing to synchronize users and groups from an ldap server into an [Apollo](https://github.com/GMOD/apollo) instance.

This is especially useful when Apollo authentication is performed using the REMOTE_USER method, and an ldap module on an upstream HTTP proxy.

## Configuration

Here the available config keys, with default values:

```
REPEAT_TIMER=3600                           # Delay between each synchronization (in seconds)
APOLLO_URL="http://0.0.0.0:8080"            # Url to the Apollo server
APOLLO_ADMIN="admin"                        # Apollo admin user name
APOLLO_PASSWORD="password"                  # Apollo admin user password
LDAP_URL="ldap://ldap"                      # Connection url for the LDAP server
LDAP_USER_DN="ou=People,dc=default,dc=org"  # DN for users in the LDAP server
LDAP_GROUP_DN="ou=Groups,dc=default,dc=org" # DN for groups in the LDAP server
CREATE_USERS=1                              # Set this to 0 if you don't want all ldap users to be created in Apollo
FAKE_EMAIL=""                               # If you want users to be registered with a fake email rather than the mail in ldap, write the suffix to use (e.g.: "@example.org")
LDAP_USER_FILTER="(mail=*)"                 # LDAP filter string for retrieving user list
LDAP_GROUP_FILTER="(cn=*)"                  # LDAP filter string for retrieving group list
DEFAULT_GROUP=""                            # Optionnaly, an additional default group assigned to all users
```
