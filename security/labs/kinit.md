# kinit.md

## Generar credenciales con el comando KINIT y listar las credenciales activas con el comando KLIST

* kinit 

```
[test-user@ip-10-1-2-236 ~]$ kinit
Password for test-user@CLOUDERA:
```

* klist

```
[test-user@ip-10-1-2-236 ~]$ klist
Ticket cache: FILE:/tmp/krb5cc_1001
Default principal: test-user@CLOUDERA

Valid starting       Expires              Service principal
11/30/2017 11:08:44  12/01/2017 11:08:44  krbtgt/CLOUDERA@CLOUDERA
        renew until 12/07/2017 11:08:44
```
