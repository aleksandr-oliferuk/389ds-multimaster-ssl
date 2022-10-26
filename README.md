# 389-ds multi-master cluster with SSL (LDAPS)

Role for deployment [389 Directory Server](https://directory.fedoraproject.org) cluster in multi-master mode with one central server and many peer nodes.

## Requirements

You need [Centos 8 Stream](https://www.centos.org/centos-stream) installed on each server you want to configure with this role and ssh access to it.

## Main files

 - [Main role playbook](roles/389ds/tasks/main.yml)
 - [Hosts file](inventory/hosts)
 - [VARs](defaults/main.yml)

## Generate PKCS12 certificate

Use this command to generate p12-file from your pem-certificate chain & key:

```
openssl pkcs12 -export -inkey server.key -in server.crt -out server.p12 -nodes -name YOURDOMAIN.COM
```
