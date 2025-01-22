# Domain List Management

Domain List Management is a service designed for tracking and inventorying domains, 
subdomains, and hostnames within an organization. 
The service enables manual addition of domains and automatically fetches additional information such as:

- WHOIS data (Name Servers, Expire Date, etc.)
- Host information (IP, DNS-zones, open ports, HTTP info, SSL validity, etc.)

It also supports exporting data to popular documentation platforms and formats, including:

- CSV file
- Google Sheets
- Embeddable link (to be used in Confluence, Notion, etc.)


## Installation as Hosted Service

- Load the .env file sample and set mongodb connection URL and mail server settings:
```shell
curl -O https://raw.githubusercontent.com/syschema/domains/main/.env 
````
- Start Domains service on 8080 port:
```shell
docker run --rm -d --name syschema-domains --network host --env-file .env syschema/domains 
```

- Start Components service on 8080 port:
```shell
docker run --rm -d --name syschema-components --network host --env-file .env -e PORT=8081 syschema/components
```
- Open the service in your browser: [http://localhost:8080](http://localhost:8080)  



- Start agents (one in corporate intranet and one in public cloud) to collect data:
```shell
docker run --rm -d --name syschema-agent -e COMMANDS_URL='<URL from Settings Screen>' syschema/agent 
```




 