# Proxmox trying to acquire lock to stop VM - fix error

```
trying to acquire lock...
TASK ERROR: can't lock file '/var/lock/qemu-server/lock-<VM id>.conf' - got timeout
```

```shell
rm /var/lock/qemu-server/lock-<VM id>.conf
```