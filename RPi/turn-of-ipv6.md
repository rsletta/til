# Turn of IPv6 Raspian Strech install
Edit ```/etc/sysctl.conf```. 

```vim 
    net.ipv6.conf.all.disable_ipv6 = 1
```
Save

Modify kernel parameters

```bash
~ $ sudo sysctl -p
```

