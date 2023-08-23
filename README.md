# sudocpp_cmake_series

#### CMAKE_SIZEOF_VOID_P
$ `cmake --help-variable CMAKE_SIZEOF_VOID_P`

&nbsp;&nbsp;&nbsp;&nbsp;CMAKE_SIZEOF_VOID_P  
&nbsp;&nbsp;&nbsp;&nbsp;--------------------------

&nbsp;&nbsp;&nbsp;&nbsp;Size of a ``void`` pointer.

&nbsp;&nbsp;&nbsp;&nbsp;This is set to the size of a pointer on the target machine, and is determined by a try compile.  
&nbsp;&nbsp;&nbsp;&nbsp;If a 64-bit size is found, then the library search path is modified to look for 64-bit libraries first.

***

### Configure and build with Debug mode
$ cmake -S.. -G Ninja -D CMAKE_CXX_COMPILER=g++ **-D CMAKE_BUILD_TYPE:STRING=Debug**  
$ cmake --build . **--config Debug** --target all

### Configure and build with Release mode
$ `cmake -S.. -G Ninja -D CMAKE_CXX_COMPILER=g++ `**-D CMAKE_BUILD_TYPE:STRING=Release**  
$ `cmake --build . `**--config Release**` --target all`  

***