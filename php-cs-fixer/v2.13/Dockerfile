FROM knplabs/phive:v0.12.4 as base

ARG PHP_CS_FIXER_VERSION

RUN phive install \
        --trust-gpg-keys 'E82B2FB314E9906E' \
        "php-cs-fixer:${PHP_CS_FIXER_VERSION}"

######################

FROM php:7.2 as php-cs-fixer

COPY --from=base /home/docker/tools/php-cs-fixer /usr/local/bin/php-cs-fixer

USER 1000
WORKDIR /workdir

ENTRYPOINT ["/usr/local/bin/php-cs-fixer"]
