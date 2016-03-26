# use docker-machine
Loads directory specific docker-machine machine.

## Install
```bash
git clone git@github.com:doloopwhile/direnv_use_docker-machine.git ~/direnv_use_docker-machine
echo '. ~/direnv_use_docker-machine/direnv_use_docker-machine.sh' >> ~/.direnvrc
```

## Usage
Create a docker-machine machine for your project
```bash
docker-machine create -d virtualbox my-machine
```

Loads the docker-machine machine with `use docker-machine`.
```
cd my-project
direnv edit . # .env is opened by $EDITOR

use docker-machine my-machine
```

The docker-machine machine will be started (if needed) and environment variables will be set on the directory.

```
$ cd my-project
direnv: loading ~/.direnvrc
direnv: loading .envrc
direnv: using docker-machine my-machine
Starting "my-machine"...
Machine "my-machine" is already running.
direnv: export +DOCKER_CERT_PATH +DOCKER_HOST +DOCKER_MACHINE_NAME +DOCKER_TLS_VERIFY
$ docker ps  # Only containers in my-machine will be listed.
```
