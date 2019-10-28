# php-cs-fixer

## Available versions

| `php-cs-fixer` version | PHP version |
|------------------------|-------------|
| v2.13.x                | 7.2         |
| v2.14.x                | 7.3         |
| v2.15.x                | 7.3         |

## How to use?

```bash
docker run --rm -it \
    -v $(pwd):/workdir \
    knplabs/php-cs-fixer:v2.15.3 \
    fix --dry-run --diff --verbose
```
