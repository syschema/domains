# Domain List Management

Domain List Management is a service designed for tracking and inventorying domains, 
subdomains, and hostnames within an organization. 
The service enables manual addition of domains and automatically fetches additional information such as:

- WHOIS data (Name Servers, Expire Date, etc.)
- Host information (IP, zones, open ports, SSL validity, etc.)

It also supports exporting data to popular documentation platforms and formats, including:

- Confluence
- Google Sheets
- Notion
- CSV


## Installation as Hosted Service

```shell
wget https://github.com/syschema/domains/docker-compose.yml
docker-compose up -d
```
