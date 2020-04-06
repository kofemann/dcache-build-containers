# Containers to build dCache packages

An easy way to build any package on any os

## Usage

```
$ git clone https://github.com/dCache/dcache.git
$ cd dcache
$ mkdir -p .m2/repository
$ DOCKER_OPTIONS="-u `id -u`:`id -g` -t --rm -h dcache-build-host --ulimit nofile=8192:8192 -m 2G -v `pwd`:/build -v `pwd`/.m2:/.m2"
$
$ docker run ${DOCKER_OPTIONS} dcache/maven-java11-tar-build
$ docker run ${DOCKER_OPTIONS} dcache/maven-java11-rpm-build
$ docker run ${DOCKER_OPTIONS} dcache/maven-java11-deb-build
```

## To build new containers

```
$ docker build -t dcache/maven-java11-rpm-build -f Dockerfile.rpm blackhole
```

## License

This work is published under [public domain](https://creativecommons.org/licenses/publicdomain/) license.
