#!/bin/bash

# Set TinyPilot to jiggle the mouse every 300 seconds.

# Author: Michael Lynch
# https://tinypilotkvm.com
# License: MIT License

set -e
set -u

# Change the value below to any you want
readonly TIME_BETWEEN_JIGGLES="300s"
i=0

while true
do
  echo "$(date --iso-8601=seconds):" "Moving mouse cursor"
  if (( $i % 2 )); then
    echo -ne "\0\x03\x16\x58\x4c\0\0" > /dev/hidg1
  else
    echo -ne "\0\xbc\x1b\xdd\x2a\0\0" > /dev/hidg1
  fi
  i=$((i+1))
  sleep "${TIME_BETWEEN_JIGGLES}"
done
