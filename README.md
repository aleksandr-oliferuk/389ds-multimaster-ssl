# 389-ds setup playbook

Playbook for setup [389 Directory Server](https://directory.fedoraproject.org/) cluster in [multi-master replication](https://access.redhat.com/documentation/en-us/red_hat_directory_server/11/html/administration_guide/multi-supplier_replication) mode (star topology) with admin-console, memberOf, DNA plugins, SSL (LDAPS) and SAMBA schema.

## Overview

This project handles ansible role for 389 Directory Server setup on CentOS 8 Stream.
Role could create cluster with multi-master replication for one main server and N peers.

## Main files

 - [Main role playbook](roles/389ds/tasks/main.yml)
 - [Hosts file](inventory/hosts)
 - [VARs](defaults/main.yml)

## Pk12 certificate generation

Use this command to generate p12-file from your pem-certificate chain & key:

```
openssl pkcs12 -export -inkey server.key -in server.crt -out server.p12 -nodes -name YOURDOMAIN.COM
```
. . .
