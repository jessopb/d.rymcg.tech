# Node-RED

[Node-RED](https://nodered.org/) is a programming tool for wiring together
hardware devices, APIs and online services in new and interesting ways.

Run `make config` or copy `.env-dist` to
`.env_${DOCKER_CONTEXT}_default`, and edit variables accordingly.

 * `NODERED_TRAEFIK_HOST` the external domain name to forward from traefik.
 * `NODERED_HTTP_AUTH` - HTTP Basic Authentication Password hashed with
   htpasswd.

## Create username/password

Node-RED does not provide any authentication, so Traefik can limit access via
HTTP Basic Authentication, which requires a username and password for access.
The password must be hashed with the `htpasswd` utility.

The `make config` will ask you to enter the new username and password,
and then automatically edit your `.env_${DOCKER_CONTEXT}_default` file
accordingly.

Paste the generated `Hashed user/password` into your
`.env_${DOCKER_CONTEXT}_default` file for the `NODERED_HTTP_AUTH`
variable.

## Start the container

Start the container with `docker-compose up -d` then login to the app with the
username `admin` and the plain text password generated.

