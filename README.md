# 🚀 Install

**We recommend to use our Docker images along with our docker-compose example file to start using LEAV-Engine.**

#### Prerequisites

You'll need to have [Docker](https://docs.docker.com/get-docker/) with [Docker compose](https://docs.docker.com/compose/install/) installed on your machine.

#### Install

* Open a terminal, create a folder for leav-engine and get in it.

```bash
mkdir ~/leav-engine && cd ~/leav-engine
```

* Download the docker-compose file:

```bash
curl -O https://raw.githubusercontent.com/leav-solutions/leav-engine/master/docker/docker-compose.prod.yml
```

* Start the services:

```bash
docker-compose -f docker-compose.prod.yml up -d
```

* Once the install is done, you can access LEAV-Engine at `http://core.leav.localhost`. The initial start might take a while. During this time, you might encounter a `Bad gateway` error. Wait a few minutes and try to refresh the page. You can check the docker logs to see what's going on.

_We advise to use Chrome or Firefox as they will figure out that this is a local domain. Otherwise, you will have to add this domain to the `/etc/hosts` file:_

```
127.0.0.1 core.leav.localhost
```

LEAV-Engine is now ready for action, have fun! 🚀
