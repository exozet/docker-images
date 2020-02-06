# docker images at exozet

At exozet we use gitlab ci, drone or other docker based tools for CI/CD.
Sometimes we need images and don't want to rely on custom builds for projects.
Sometimes we don't know which is the official image or the official image only has latest tags.
To avoid this, we create small Dockerfiles (usually based on alpine) for those images.
For official images with too many updates, we maintain a whitelist.

## Our Images

To avoid depending on lots of good (but not exozet maintained) docker images, we are hosting auto build images on docker hub.
If we want to make a new version available there, you need to do only one step: add a new tag with the version number.
Minutes later the image will be available as exozet/product:version on docker hub.

The following images are available:

* [exozet/php-fpm](https://hub.docker.com/r/exozet/php-fpm) // *[source](https://github.com/exozet/docker-php-fpm)*
* [exozet/helm](https://hub.docker.com/r/exozet/helm) // *[source](https://github.com/exozet/docker-helm)*
* [exozet/curl](https://hub.docker.com/r/exozet/curl) // *[source](https://github.com/exozet/docker-curl)*
* [exozet/kubectl](https://hub.docker.com/r/exozet/kubectl) // *[source](https://github.com/exozet/docker-kubectl)*
* [exozet/goss](https://hub.docker.com/r/exozet/goss) // *[source](https://github.com/exozet/docker-goss)*

## Whitelist

* [alpine](https://hub.docker.com/_/alpine)
* [google/cloud-sdk:alpine](https://hub.docker.com/r/google/cloud-sdk)

## Deprecations

* [byrnedo/alpine-curl](https://hub.docker.com/r/byrnedo/alpine-curl) -> use [exozet/curl](https://hub.docker.com/r/exozet/curl)
* [devth/helm](https://hub.docker.com/r/devth/helm/) -> use [exozet/helm](https://hub.docker.com/r/exozet/helm)
* [aelsabbahy/goss](https://hub.docker.com/r/aelsabbahy/goss) -> use [exozet/goss](https://hub.docker.com/r/exozet/goss)
* [php](https://hub.docker.com/_/php) -> use [exozet/php-fpm](https://hub.docker.com/r/exozet/php-fpm)

## Tools

We use hub.docker.com (and sometimes travis-ci) for building the images. We use quay.io to generate CVE-Reports.

# License

This README.md is copyright by Exozet (http://exozet.com) and licensed under the terms of MIT License.
