<!-- https://shields.io/ -->
[![license](https://img.shields.io/github/license/peaceiris/hugo-extended-docker.svg)](https://github.com/peaceiris/hugo-extended-docker/blob/master/LICENSE)
[![release](https://img.shields.io/github/release/peaceiris/hugo-extended-docker.svg)](https://github.com/peaceiris/hugo-extended-docker/releases/latest)
[![GitHub release date](https://img.shields.io/github/release-date/peaceiris/hugo-extended-docker.svg)](https://github.com/peaceiris/hugo-extended-docker/releases)
[![GitHub Actions status](https://github.com/peaceiris/hugo-extended-docker/workflows/Docker%20Image%20CI/badge.svg)](https://github.com/peaceiris/hugo-extended-docker/actions)

<img width="400" alt="Docker image of Hugo extended version" src="./images/ogp.svg">



## Docker image of Hugo (Hugo extended and Hugo Modules)

- [peaceiris/hugo - Docker Hub]

[![Docker Hub Build Status](https://img.shields.io/docker/cloud/build/peaceiris/hugo.svg)](https://hub.docker.com/r/peaceiris/hugo)
[![docker image size](https://images.microbadger.com/badges/image/peaceiris/hugo.svg)](https://microbadger.com/images/peaceiris/hugo)

<!-- https://microbadger.com/ -->

[![DockerHub Badge](https://dockeri.co/image/peaceiris/hugo)][peaceiris/hugo - Docker Hub]

[peaceiris/hugo - Docker Hub]: https://hub.docker.com/r/peaceiris/hugo



## Getting started

| Image tag | Base Image | Image size | Notes |
|---|---|---|---|
| `peaceiris/hugo:v0.x.x` | `alpine:3.11` | 66.1 MB | Small image |
| `peaceiris/hugo:v0.x.x-mod` | `golang:1.13-alpine3.11` | 419 MB | Hugo Modules feature is available |

### (1) Docker Compose

Create your `docker-compose.yml` like the following.

```yaml
version: '3'

services:
  hugo:
    container_name: hugo
    image: peaceiris/hugo:v0.x.x
    # image: peaceiris/hugo:v0.x.x-mod  # Hugo Modules
    ports:
      - 1313:1313
    volumes:
      - ${PWD}:/src
    command:
      - server
      - --bind=0.0.0.0
      - --buildDrafts
```

### (2) Usage

```sh
# Run "hugo server"
docker-compose up

# Build site
docker-compose run --rm hugo ""
# Build site with flags
docker-compose run --rm hugo --gc --minify --cleanDestinationDir

# Run a command of Hugo
docker-compose run --rm hugo env
```



## License

- [MIT License - peaceiris/hugo-extended-docker]

[MIT License - peaceiris/hugo-extended-docker]: https://github.com/peaceiris/hugo-extended-docker/blob/master/LICENSE



## Maintainer

- [peaceiris homepage](https://peaceiris.com/)
