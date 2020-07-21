# How to compile on Linux

## Prerequisits

* C compiler (GNU C compiler)
* make

## Steps to compile

* `cd vmd/plugins`
* `make LINUXAMD64` if you are on linux 64bits
* A folder called "compile" has been created and there is the LINUXAMD64 compiled lib in it
* It contains all the molfile plugins so just copy the "lib_LINUXAMD64" folder to your project/plugins and rename it "LINUXAMD64"

Ready, you can use all shared libraries in your own C/C++ code

# How to compile on Mac OSX

## Prerequisits

* C compiler (clang)
* make

## Steps to compile

* `cd vmd/plugins`
* `make MACOSXX86_64"` if you are on OSX 10.15 Catalina, You can compile 32 bits for previous versions of OSX using `make MACOSXX86`
* A folder called "compile" has been created and there is the MACOSXX86_64 compiled lib in it
* It contains all the molfile plugins so just copy the "lib_MACOSXX86_64" folder to your project/plugins and rename it "MACOSXX86_64"

Ready, you can use all shared libraries in your own C/C++ code

