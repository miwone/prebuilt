FROM serversideup/php:8.3-cli-alpine AS basebuilder

USER root
ENV PATH="/composer/vendor/bin:$PATH"
RUN install-php-extensions pdo_mysql fileinfo sqlite3 pdo_sqlite sodium && \
    composer global require phpacker/phpacker && \
    phpacker download "miwone/php-bin"