# Compilation steps

## Linux 64 bits



## OSX


### Install tcl
If you plan to use the default tcl version considered by VMD, then you need to download tcl 8.5. 

Download & install http://www.tcl.tk/software/tcltk/downloadnow85.html
Unzip the archive 
```bash
cd tcl8.5.19/macosx
CC=clang ./configure
make -f Makefile
sudo make install -f Makefile
```

Then you can define these as environment variables

```bash
export TCLINC=/usr/local/include
export TCLLIB=/usr/local/lib
```

### Install netcdf
If you want to compile the netcdf plugin & have netcdf support you also need this library: 
```bash 
sudo port install netcdf
export NETCDFINC=-I/opt/local/include
export NETCDFLIB=/opt/local/lib/libnetcdf.dylib
export NETCDFLDFLAGS=-Lnetcdf
```

### Compile the molfile plugin (for X86_64 Intel chipset)

adapt the TCLLIB variable to the tcl version you have installed

In this repo: 
```bash
cd plugins 
make MACOSXX86_64 TCLINC=$TCLINC TCLLIB=$TCLLIB/libtcl8.5.dylib
export PLUGINDIR=$PWD/compiled
make distrib
```

# Original Documentation

VMD Plugin README
-----------------
  This directory is the root of the plugin directory for VMD.  
VMD plugins are designed to add new functionality and support for new types
of files or external programs without compiling that functionality into the
main body of VMD's code.  Most plugins take the form of a shared library 
(files named xxx.so or xxx.dll) which can be detected by VMD and loaded at 
run time.  The plugin and the application communicate through a well-defined 
API, which makes the plugin more reusable by avoiding direct coupling to 
VMD's internal data structures.  Similarly, plugins can be upgraded at
any time, independent of VMD itself.

For additional information on compiling the plugins and building VMD,
please read the web-based plugin documentation here:
  http://www.ks.uiuc.edu/Research/vmd/plugins/doxygen/

Plugin directory structure
--------------------------
/_plugin: 
  Directories that end in _plugin are plugin source repositories.  All 
plugins of a given type (i.e., which use the same API) should be placed in the
corresponding directory.  Each plugin directory contains the following 
subdirectories:
 - src: source code for all plugins of that type;
 - msvc: Microsoft Visual Studio project files for each plugin;
 - doc: documentation for each plugin.
The plugin directory also contains a Makefile for compiling all the plugins.
The Makefile currently is for a gcc target only.

/compile:
  Contains compiled binary plugins, both static and dynamic, as well as
related header files, etc. 

/include: 
  This directory contains the VMD plugin API header files, including
vmdplugin.h (the base-level plugin header) as well as headers for other plugin
types.  Alternatively, these files may be linked from the VMD source tree.

/msvc: 
  Contains a Microsoft Visual Studio workspace file for compiling all
the plugins for the Win32 platform.


