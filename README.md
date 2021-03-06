matio-ffi
========

A LuaJIT interface to MATIO

# Installation #

First, make sure MATIO is installed on your system. This package only requires the binary shared libraries (.so, .dylib, .dll).
Please see your package management system to install MATIO. 
You can also download and compile matio from [MATIO web page](http://matio.sourceforge.net)

```sh
# OSX
brew install libmatio

# Ubuntu
sudo apt-get install libmatio2
```


```sh
luarocks install https://raw.githubusercontent.com/soumith/matio-ffi.torch/master/matio-scm-1.rockspec
```

# Usage #
###Load a tensor from matlab array
```lua
local matio = require 'matio'
testTensor = matio.load('test.mat', 'var_a')
```

### Calling MATIO C functions

All MATIO C functions are available in the `matio.ffi.` namespace returned by require. The only difference is the naming, which is not prefixed
by `Mat_` anymore. 

For example, look at matio.load in init.lua
