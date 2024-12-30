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

- Load the docker-compose file and the environment file:
    ```shell
    curl -O https://raw.githubusercontent.com/syschema/domains/main/docker-compose.yml
    curl -O https://raw.githubusercontent.com/syschema/domains/main/.env 
    ```
- Edit the `.env` file to set mail server settings and other configurations.

- Start the service:
    ```shell
    docker-compose up -d
    ``` 
