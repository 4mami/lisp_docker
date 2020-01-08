# Dockerfiles for Common Lisp programming

Dockerfiles for each versions of Common Lisp implementations and utilities. Currently this repository provides for the following products:

- [roswell](https://github.com/roswell/roswell) [\[Docker Hub\]](https://hub.docker.com/r/fukamachi/roswell)
- [sbcl](http://sbcl.org) [\[Docker Hub\]](https://hub.docker.com/r/fukamachi/sbcl)

## Usage

### Building by yourself

```
# Build SBCL 2.0.0 image (Debian)
$ docker build -t sbcl:2.0.0 sbcl/2.0.0
# On Alpine Linux
$ docker build -t sbcl:2.0.0-alpine sbcl/2.0.0/alpine

# Start a REPL
$ docker run -it --rm sbcl:2.0.0
* (lisp-implementation-type)
"SBCL"
* (lisp-implementation-version)
"2.0.0"
```

### Using built images

Built images are automatically published to Docker Hub and can `docker pull`:

```
$ docker pull fukamachi/sbcl:latest
$ docker run -it --rm fukamachi/sbcl:latest
*
```

## Developer notes

These scripts will be called by [GitHub Actions](https://github.com/fukamachi/dockerfiles/actions) automatically, however, sometimes it needs to be run manually.

### Generate Dockerfiles for recent releases

```
$ ./roswell/update.sh
$ ./sbcl/update.sh
```

### Generate GitHub Actions

```
$ ./generate-build-actions.sh
```
