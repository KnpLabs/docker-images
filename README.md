# KNPLabs images

Images:
* [phive](phive/README.md)
* [php-cs-fixer](php-cs-fixer/README.md)

## For maintainers

**Note:** at the time of writing (October 2019), you’ll need to enable Docker’s
[experimental features](https://github.com/docker/docker-ce/blob/master/components/cli/experimental/README.md)
to be able to build the images (the build requires `docker build --squash`).

##### Build a new version

```bash
IMAGE=phive VERSION=v0.12.4 make build
```

You have to provide the `IMAGE` name, which should match a root directory name.
You also have to provide the `VERSION`. Minor version should have a subdirectory
in the image root dir, with a Dockerfile and its build context.

You can use `NO_CACHE=y` to build with no cache.

##### Push a new version

```bash
IMAGE=php-cs-fixer VERSION=v2.15.3 make push
```

You have to provide the `IMAGE` and `VERSION` to push. If the image already
exists on the remote repo, it will fail. You can force push by adding `FORCE=y`.
