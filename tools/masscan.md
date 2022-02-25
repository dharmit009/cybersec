# Masscan 

**What is Masscan?**

**Masscan** is a multithreaded port scanner which is extremely fast when
compared to **nmap**. That is because it was designed to scan entire
organization open ports at once if you need to do so. It uses
asynchronize timing.

**How to use Masscan?**

* To massively scan the network for open ports: 

`masscan 10.0.0.0/8 -p80`

This will scan port 80 for the entire IP range from 10.0.0.0 to 10.0.0.8

**How to scan the entire internet?** [SUPER DANGEROUS]

`masscan 0.0.0.0/0 -p <any port number if specific> --rate 1000000`
