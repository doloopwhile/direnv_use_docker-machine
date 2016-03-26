#!/bin/sh
use_docker-machine() {
  if [ $# -ne 1 ]; then
    echo "usage: use_docker-machine MACHINE" >&2
    return 1
  fi

  if ! which docker-machine > /dev/null 2>&1; then
    echo "'docker-machine' command not found in PATH" >&2
    return 1
  fi

  docker-machine start "$1"
  eval "$(docker-machine env)"
}
