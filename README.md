# ntua_ppp
NTUA's PPP to be tool

# Prerequisite

You need two (C++) libararies to install the software

1. `ggeodesy` which can be found [here](https://bitbucket.org/xanthos/ggeodesy/src/master/); the [readme](https://bitbucket.org/xanthos/ggeodesy/src/master/readme.md) files contains more info.

2. `ggdatetime` which can be found [here](https://bitbucket.org/xanthos/ggdatetime/src/master/); again consult the [readme](https://bitbucket.org/xanthos/ggdatetime/src/master/README.md) file for details.

# Installation

At this point the project is under heavy development, thus users will have to use autotools to install it. After cloning
```
autoreconf -if
./configure
make
````
