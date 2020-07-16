# How to compile on linux

1. Go to vmd, then plugins : "cd vmd/plugins"
2. Have Tcl installed in your bin root to be able to use the make
3. Type "make LINUXAMD64" if you are on linux 64bits
4. A folder called "compile" has been created and there is the LINUXAMD64 compiled lib in it
5. It contains all the molfile plugins so just copy the "lib_LINUXAMD64" folder to fpocket/plugins and rename it "LINUXAMD64"
6. Recompile fpocket
7. Done 