# KNPLabs images

Images:
* [phive](phive/README.md)
* [php-cs-fixer](php-cs-fixer/README.md)

## For maintainers

##### Build a new version

```bash
IMAGE=phive VERSION=v0.12.1 make build
```

You have to provide the `IMAGE` name, which should match a root directory name. 
You also have to provide the `VERSION`. Minor version should have a subdirectory
in the image root dir, with a Dockerfile and its build context.

You can use `NO_CACHE=y` to build with no cache.

##### Push a new version

```bash
IMAGE=php-cs-fixer VERSION=v2.14.2 make push
```

You have to provide the `IMAGE` and `VERSION` to push. If the image already
exists on the remote repo, it will fail. You can force push by adding `FORCE=y`.
