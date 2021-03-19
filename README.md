# bracket
WordPress development and production servers with Docker


Wordpress containerization, scaffolding and local development provisioner

MVP
- DRY: No need to copy-paste files per project
- Standardized version controller scaffolding
- CLI clones latest Bedrock
- Docker-compose for local development
- Version controlled Kubernetes stack

TODO
- Multiple environments
- Provision using Dozer
- Sync with remote


Engine CLI
==========

engine create example.com
    clone bedrock to ./site
    run composer install 
    configure .env for Docker-compose
    configure CI Build scripts
    
engine start
    docker-compose up -d

engine down
    docker-compose down


Future
---
engine provision production
    ansible-playbook server.yml -e env=production

engine deploy production
    ./bin/deploy.sh production example.com

engine sync production development
    ./bin/sync.sh 
        wget db.sql
        wget web/app/uploads
        wp import db


Folder Structure
---
example.com/
    bin/
    config/
    site/ ---> bedrock

Configure
---
config/
    development/
        site.yml
        vault.yml
