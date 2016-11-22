# exakat-docker

[![Docker Stars](https://img.shields.io/docker/stars/mikoim/exakat-docker.svg)](https://hub.docker.com/r/mikoim/exakat-docker/)
[![Docker Pulls](https://img.shields.io/docker/pulls/mikoim/exakat-docker.svg)](https://hub.docker.com/r/mikoim/exakat-docker/)
[![Docker Automated buil](https://img.shields.io/docker/automated/mikoim/exakat-docker.svg)](https://hub.docker.com/r/mikoim/exakat-docker/)

Build a docker container with [exakat](http://www.exakat.io/) and all dependencies installed.

## How do I use it?

### Build your own container

Pros:

* Latest
* Customizable

Cons:

* It takes a lot of time to build container

---

Make sure you have all pre-requisite

* Docker
* Packer
* Git

Then :

```bash
git clone https://github.com/mikoim/exakat-docker.git exakat-docker
cd exakat-docker
packer build packer.json
```

### Use pre-build container

Pros:

* Only need Docker
* Takes less time, than self-building

Cons:

* ~~May be outdated~~ (Now automated weekly builds available :smile:)

---

Make sure you have all pre-requisite

* Docker

```bash
docker pull mikoim/exakat-docker
```

### What we do next?

Example:

```bash
docker run --name exakat -i -t mikoim/exakat-docker /bin/bash

cd /opt/exakat
./exakat.phar doctor
```

## More details

* PHP binary for exakat execution (PHP with curl, tokenizer and sqlite3).
* PHP 7.1-dev (master), 7.0, 5.6, 5.5 for exakat analysis
* Neo4j 2.2.7 and gremlin 2.0 plugin, running on Java 8

This container is sized to handle projects up to 100k LOC of PHP. Larger projects do require more RAM and adaptation in config/config.ini.

The ansible playbook may be used independantly to install exakat only : see role ['exakat'](https://github.com/mikoim/exakat-docker/blob/master/.ansible/exakat.yml).

## Author

This repository is the brain child of [Alexis von Glasow](https://github.com/vonglasow), with the help of contributors.
