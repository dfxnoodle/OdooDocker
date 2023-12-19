About this Repo
======

This is the Git repo of a customized verison of official Docker image for [Odoo](https://registry.hub.docker.com/_/odoo/). See the Hub page for the full readme on how to use the Docker image and for information regarding contributing and issues.

The full readme is generated over in [docker-library/docs](https://github.com/docker-library/docs), specifically in [docker-library/docs/odoo](https://github.com/docker-library/docs/tree/master/odoo).

**Manually download the package file into the directory if necessary**
```
curl -k -o odoo.deb https://{domain}/odoo16/odoo_16.0+e.latest_all.deb
```
**This is an example docker build image command with an image name: odoo-docker-16 and version 0.1**
```
docker build -t odoo-docker-16:0.1 .
```
**Before starting odoo, Start a PostgreSQL server**
```
docker run -d -e POSTGRES_USER=odoo -e POSTGRES_PASSWORD=odoo -e POSTGRES_DB=postgres --name db postgres:15
```
**Then run a odoo docker image**
```
docker run -d -p 8069:8069 --name odoo --link db:db -t odoo-docker-16:0.1
```
Remember to change the name and port to an unused one
