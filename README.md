# Zerops x Zabbix

[Zabbix](https://www.zabbix.com/) is self-hosted monitoring and visualization software.

## Prerequisites

- Zerops account - [sign up here](https://app.zerops.io/registration)

## Deploy Zabbix to Zerops

Locate "Import project" in the menu top left corner and paste following yaml:

```
project:
  name: recipe-zabbix
services:
  - hostname: pgdb
    type: postgresql@16
    mode: HA
    priority: 10
  
  - hostname: zabbix
    type: ubuntu@22.04
    enableSubdomainAccess: true
    buildFromGit: "https://github.com/zeropsio/recipe-zabbix"
    zeropsSetup: zabbix
    priority: 1
```

## Login to Zabbix 
When deploy is complete, go to `recipe-zabbix` project detail and in the left menu locate `IP Addresses & Public Routing Overview`, where you can find a subdomain link to open Zabbix frontend.
Open it and make your first login into Zabbix as `Admin` with password `zabbix` and enjoy :-)
