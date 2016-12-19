#!/bin/bash
defvar () {
  HON=$(ps -e | grep -m1 hon-x86 | awk -F ' ' '{print $4}')
  BRIGHT=$(xrandr --verbose | awk '/Brightness/ { print $2 }')
  checkhon
}
checkhon ()  {
    if [ "$BRIGHT" != "1.0" ] && [ "$HON" == "" ]; then
      stb1 && sleep 1 && checkhon2
    else
      sleep 1 && checkhon2
    fi  }
checkhon2 () {
  if [ "$BRIGHT" != "2.0" ] && [ "$HON" != "" ]; then
    stb2 && sleep 1 && defvar
  else
    sleep 1 && defvar
  fi
}

stb1 () {
  xrandr --output $(xrandr -q | grep " connected" | awk '{ print $1 }') \
  --brightness 1
}
stb2 () {
  xrandr --output $(xrandr -q | grep " connected" | awk '{ print $1 }') \
  --brightness 2
}

defvar
