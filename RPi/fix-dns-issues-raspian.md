# Fix DNS issues on fresh Raspian Strech install
Edit ```/etc/dhcpcd.conf```. 

static domain_name_servers=1.1.1.1 1.0.0.1 208.69.38.205 8.8.8.8