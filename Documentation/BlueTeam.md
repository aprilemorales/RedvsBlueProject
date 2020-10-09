# Blue Team Documentation

### Identify the offensive traffic.
Identify the traffic between your machine and the web machine:

KQL Search: 

`http.response.status_code: 201`

- When did the interaction occur?
    - July 18th 2020 @ 19:13:17.000
- What responses did the victim send back?
    - 201 response which is a successful PUT request meaning a file was created.
- What data is concerning from the Blue Team perspective?
    - Metricbeat results:
        - This came from a Kali machine which is a known pentesting OS. (agent.name)
        - The PUT request (adding shell.php)
        - Cadaver to access WebDav (weird program/traffic not a typical user)
    - Filebeat results: 
        - Apache access
        - 201 confirmed/file created on server
        - Username ryan (someone did this under ryan’s account - compromised account)
        - Source IP 192.168.1.90
