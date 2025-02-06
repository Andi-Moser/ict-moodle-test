# Moodle Setup

This setup builds and runs a moodle container with the german locale enabled.

## Instructions

### Start the thing

To start everything simply run `docker compose up`. To detach the console from the process run `docker compose up -d` instead.

### Generate a certificate

Run the `generate-cert.sh` script as follows: `generate-cert.sh xxx.ict-bz.ch`

### Renew the certificates

Run the `renew-certs.sh` script to renew every installed certificate. This should be done via a cronjob every one month.

## Troubleshooting

### MariaDB can't start (Permission denied)

See https://github.com/bitnami/containers/issues/23841#issuecomment-1816394184 or temporary set the `./data/mariadb_data` to `777`.

### Cannot login after fresh installation / default username/password

The default username and password is `user` / `bitnami`.

Those can be set by the `MOODLE_USERNAME` / `MOODLE_PASSWORD` environment variables (either via the host system or the `docker-compose.yml`)