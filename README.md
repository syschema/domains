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


```shell
docker run --rm -d \
  --name syschema-domains \
  --network host \
  -p 8080:8080 \
  -e DB_CONNECTION_URL=mongodb://localhost:27017/syschema \
  -e MAIL_HOST=mail.vmailhost.com \
  syschema/domains
```

- Load the docker-compose file and the environment file:
    ```shell
    mkdir syschema-domains && cd syschema-domains
    curl -O https://raw.githubusercontent.com/syschema/domains/main/docker-compose.yml
    curl -O https://raw.githubusercontent.com/syschema/domains/main/.env 
    ```
- Edit the `.env` file to set mail server settings and other configurations.

- Start the service:
    ```shell
    docker-compose up -d
    ``` 
