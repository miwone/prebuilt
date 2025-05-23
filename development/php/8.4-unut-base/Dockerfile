FROM serversideup/php:8.4-unit

USER root

RUN usermod -s /bin/bash www-data && \
    docker-php-serversideup-set-id www-data 1000:1000 && \
    docker-php-serversideup-set-file-permissions --owner 1000:1000 --service unit

RUN docker-php-serversideup-dep-install-debian git && \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

USER www-data

