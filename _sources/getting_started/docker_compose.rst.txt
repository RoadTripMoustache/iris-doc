Start with docker compose
=========================

To start with docker compose, you can use the following template to help you. It contains the API and the frontend part.

.. code-block::

    name: iris
    services:
      iris-api:
        container_name: iris-api
        restart: always
        image: "roadtripmoustache/iris-api:latest"
        ports:
          - "8081:8080"
          - "8082:2121"
        environment:
          CONFIG_FILE_PATH: "/tmp/config.yaml"
        volumes:
          - ./iris_config.yaml:/tmp/config.yaml:ro
          - ./svc-account.json:/tmp/svc_account.json:ro
        labels:
          name: iris-api
        networks:
          - iris

      iris-front:
        container_name: iris-front
        restart: always
        image: "roadtripmoustache/iris-front:latest"
        volumes:
          - ./firebase-config.json:/app/server/files/firebase-config.json:ro
          - ./config.json:/app/server/files/config.json:ro
        ports:
          - "8083:3000"
        labels:
          name: iris-front
        networks:
          - iris

    networks:
      iris:

Update some configurations like the exposed ports, where your config files are, rename the network,
change `the images versions <https://hub.docker.com/repositories/roadtripmoustache>`__... and you're ready to go !

.. important::

    **Don't forget to setup the MongoDB instance !**

    There's no MongoDB instance in this docker compose yaml template, but it's mandatory to make it work correctly.

Then use the following command to start the services.

.. code-block::

    docker compose up
