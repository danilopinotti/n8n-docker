# N8N with PostgreSQL, Worker and auto SSL

Starts n8n with PostgreSQL as database, and the Worker as a separate container. In addition, this environment auto configures the SSL.

This project is made on top of [official n8n docker-compose file](https://github.com/n8n-io/n8n/tree/master/docker/compose/withPostgresAndWorker)

## Setup

To setup this project in production, first you need to copy the `.env.example` file as `.env`.
```shell
cp .env.example .env
```

Then, you need to open the new `.env` file and edit the following entries.
```
N8N_HOST=n8n.example.com

POSTGRES_PASSWORD=<MY_STRONG_PASSWORD>
POSTGRES_NON_ROOT_PASSWORD=<MY_STRONG_PASSWORD>
```

Feel free to edit the other entries as you need.

## Start

After setup, to start n8n you need to start docker-compose by executing the following command in the current folder.

```shell
docker-compose up -d
```

To stop execution:
```shell
docker-compose stop
```

## Production

To use in production, you only need to set the `STAGE` entry as `production` in the `.env` file and then restart the environment.

In the `.env` file:
```
STAGE=production
```

Commands to run after editing:
```shell
docker-compose stop
docker-compose up -d
```

**Important**: Only set as production after n8n works properly. Otherwise you may be blocked to obtain the SSL certificate at LetsEncrypt.

## License

The MIT License (MIT). Please see [License File](LICENSE) for more information.