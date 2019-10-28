# Phive

* [Available version](#available-version)
* [How to use?](#how-to-use)

## Available version

| Phive version | PHP version |
|---------------|-------------|
| v0.12.4       | 7.3         |

## How to use?

This image is mostly useful when you want to securely install PHARs. You can use
it as a base image:

```bash
FROM knplabs/phive as base

RUN phive install \
        --trust-gpg-keys 'E82B2FB314E9906E' \
        "php-cs-fixer:v2.15.3"

######################

FROM php:7.3 as php-cs-fixer

COPY --from=base /home/docker/.phive/phars/php-cs-fixer.phar /usr/local/bin/php-cs-fixer

WORKDIR /workdir

ENTRYPOINT ["/usr/local/bin/php-cs-fixer"]
```
