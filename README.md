# Deploying Keycloak in Gitops way

RH-SSO and RHBK manifests to deploy instances of Red Hat Single Sign On and Red Hat Build of Keycloak


# Note:

The secret containing certificate and database credential can be created in Non-Declarative Manner , or instead use [sealed secrets](https://github.com/bitnami-labs/sealed-secrets) in case you want to maintain secrets in declarative manner.
~~~
$ oc create secret generic keycloak-db-secret \
--from-literal=username=xxxxxxx \
--from-literal=password=xxxxxxx
secret/keycloak-db-secret created

$ oc create secret tls rhbk-tls-secret --cert tls.crt --key tls.key
secret/rhbk-tls-secret created 
~~~
