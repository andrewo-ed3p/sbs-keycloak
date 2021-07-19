# Keycloak Docker image

Keycloak Server Docker image.

Short instruction.

Based on https://github.com/keycloak/keycloak-containers/tree/master/server


## Usage

To boot in standalone mode

    docker run jboss/keycloak



## Expose on localhost

To be able to open Keycloak on localhost map port 8080 locally

    docker run -p 8080:8080 jboss/keycloak



## Creating admin account

By default there is no admin user created so you won't be able to login to the admin console. To create an admin account
you need to use environment variables to pass in an initial username and password. This is done by running:

    docker run -e KEYCLOAK_USER=<USERNAME> -e KEYCLOAK_PASSWORD=<PASSWORD> jboss/keycloak

You can also create an account on an already running container by running:

    docker exec <CONTAINER> /opt/jboss/keycloak/bin/add-user-keycloak.sh -u <USERNAME> -p <PASSWORD>

Then restarting the container:

    docker restart <CONTAINER>

