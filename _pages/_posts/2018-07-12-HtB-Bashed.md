## HtB - Bashed Walkthrough
<img src="/_pages/2018-07-12_23-17-16.jpg" class="align-left" alt="">


In prepartion for the OSCP I have been utilizing the [Hack the Box](https://www.hackthebox.eu/home) lab environment.

The first machine I completed was Bashed. Bashed has been retired and rooting this machine will not award any points. None the less this is a great machine to begin with. Currently the IP address for Bashed is `10.10.10.68`.

To access the lab environment download your openvpn connection pack and run the command `openvpn connection-pack.ovpn` replacing `connection-pack.ovpn` with the one downloaded.

Once in the lab environment we can now start enumerating the machine. Starting with a simple `nmap` scan.
  `nmap -sC -sV -oA nmap/initial 10.10.10.68`
