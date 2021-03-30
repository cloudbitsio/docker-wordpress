<!-- <p align="center">
  <a href="https://github.com/cloudbitsio/bracket"><img width="240" src="bracket.svg" /></a>
</p> -->
<p align="center">Wordpress on Docker. Plus local development environment with Docker-compose.</p>
<p align="center">
  <a href="#nginx-configurations">About</a> |
  <a href="#configuration">Configuration</a>
</p>

---

# Wordpress in a Docker container

The purpose of this project is to provide a working Docker container for Wordpress, with an accompanying Docker-compose for local development.

Licensed under [MIT](./LICENSE).

Features
- DRY: Standardized version-controlled scaffolding for Wordpress projects
- Docker-compose for local development
- Uses [Lightbulb](https://github.com/cloudbitsio/lightbulb-alpine) as the Docker starting point.
- Utlizes the awesome [Bedrock](https://github.com/roots/bedrock) from Roots.io

## Configuration

Clone this repository into your project folder. The contents of this repository are meant to sit on the root directory of your project.

1. Create a new project directory:
```bash
mkdir website.com && cd website.com
```

2. Clone Bracket:
```bash
git clone --depth=1 git@github.com:cloudbitsio/bracket.git . && rm -rf .git
```

3. Create a new Bedrock project into the `site` folder.
```bash
composer create-project roots/bedrock site
```

4. Run Ansible playbook for configuring Docker engine
```bash
ansible-playbook development.yml
```