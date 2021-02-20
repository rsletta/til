# Change user password in HANA Express

```shell
hdbsql -i 90 -d systemdb -u SYSTEM
```

```shell
alter user XSA_DEV password <new password>;
```