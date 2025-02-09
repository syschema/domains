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

### Requirements
- Docker and Docker Compose installed
- CPU: 2 cores, RAM: 4GB, Disk: 10GB

### Installation

- Load initial configuration:
```shell
mkdir -p /opt/syschema && cd /opt/syschema
curl -O https://raw.githubusercontent.com/syschema/domains/main/.env 
curl -O https://raw.githubusercontent.com/syschema/domains/main/nginx.conf 
curl -O https://raw.githubusercontent.com/syschema/domains/main/docker-compose.yml 
````
- Change the .env file sample with your server settings 

- Start service on 8080 port:
```shell
docker-compose up -d
```

- Open the service in your browser: [http://localhost:8080](http://localhost:8080)  

### Remote Agent Installation

- Start agent (one in corporate intranet and one in public cloud) to collect data:
```shell
docker run --rm -d --name syschema-agent -e COMMANDS_URL='<URL from Settings Screen>' syschema/agent 
```




 