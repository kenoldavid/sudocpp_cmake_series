# sudocpp_cmake_series

### Configure and build with Debug mode
$ cmake -S.. -G Ninja -D CMAKE_CXX_COMPILER=g++ **-D CMAKE_BUILD_TYPE:STRING=Debug**  
$ cmake --build . **--config Debug** --target all

### Configure and build with Release mode
$ `cmake -S.. -G Ninja -D CMAKE_CXX_COMPILER=g++ `**-D CMAKE_BUILD_TYPE:STRING=Release**  
$ `cmake --build . `**--config Release**` --target all`  
