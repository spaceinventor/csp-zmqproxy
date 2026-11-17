
## Dependencies (As named on Ubuntu 24.04)

apt install -y git meson libzmq3-dev pkg-config


## (Configure) and Build

meson setup builddir
ninja -C builddir


## Install

ninja -C builddir install
