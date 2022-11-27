# n8n with PostgreSQL and Worker and auto SSL

Starts n8n with PostgreSQL as database, and the Worker as a separate container. In addition, this environment auto configures the SSL.

This project is made on top of [official n8n docker-compose file](https://github.com/n8n-io/n8n/tree/master/docker/compose/withPostgresAndWorker)

## Start

To start n8n simply start docker-compose by executing the following
command in the current folder.

**IMPORTANT:** But before you do that, you need to duplicate the [`.env.example`](.env.example) file as `.env`, and then, change the default users and passwords in this `.env` file!

```
docker-compose up -d
```

To stop it execute:

```
docker-compose stop
```

## Configuration

The default name of the database, user and password for PostgreSQL can be changed in the [`.env`](.env) file in the current directory.