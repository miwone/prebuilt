FROM serversideup/php:8.4-unit

USER root

RUN usermod -s /bin/bash www-data && \
    docker-php-serversideup-set-id www-data 1000:1000 && \
    docker-php-serversideup-set-file-permissions --owner 1000:1000 --service unit && \
    ##
    echo "alias art='php artisan'" >> /var/www/.profile

RUN install-php-extensions sqlsrv pdo_sqlsrv gd && \
    docker-php-serversideup-dep-install-debian git && \

    # LibreOffice
    apt-get update && apt-get install -y \
    libreoffice \
    libxrender1 \
    libxt6 \
    libxext6 \
    libxinerama1 \
    fonts-dejavu \
    # for github.com/spatie/pdf-to-text
    poppler-utils \
    ##
    && apt-get clean && rm -rf /var/lib/apt/lists/*

USER www-data
