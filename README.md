travis-docker [![Build Status](https://travis-ci.org/moul/travis-docker.svg?branch=master)](https://travis-ci.org/moul/travis-docker)
=============

Running Docker in a Travis CI build.

`./run` script will run commands in a user-land linux with `docker` and `docker-compose` and pass back the exit code

Inspired by [lukecyca/travis-docker-example](https://github.com/lukecyca/travis-docker-example)

**.travis.yml** examples
------------------------

Run any command inside the pseudo-linux

    install:
    - curl -sLo - https://github.com/moul/travis-docker/raw/master/install.sh | sh -xe
    script:
    - ./run docker run busybox ls -la
    - ./run docker run busybox ls -la /non-existing-dir
    - ./run 'docker-compose up -d blog && docker ps && date'
    - ./run 'apt-get install git && git clone && docker -f ...'

License
=======

MIT
