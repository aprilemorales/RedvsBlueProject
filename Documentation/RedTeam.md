# Red Team Documentation

### Discover the IP address of the Linux web server
First step would be to do an ifconfig in the terminal to see what the Kali machine IP is.

Command:
`ifconfig`

Result:
IP 192.168.1.90 and Netmask 255.255.255.0
![ifconfig terminal results](/Images/ifconfig-results.png "ifconfig terminal results")

Next was to scan all IPs on the same network in the subnet. Knowing the subnet of netmask of 255.255.255.0 is /24 it can be established in the nmap scan.

Command: 
`nmap -sS -A 192.168.1.1/24`

Result:
IP 192.168.1.105
![nmap terminal results](/Images/nmap-results.png "nmap terminal results")

While there were other machines on the network it could be determined that IP ending with 105 was the machine we were looking for. This is based on the list of directories found and it returns as Apache/2.4.29 server.

### Locate the hidden directory on the web server.
Now that the IP of the server/machine was found it was time to visit it at http://192.168.1.105.