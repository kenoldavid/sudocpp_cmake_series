cmake_minimum_required(VERSION 3.15)
project(Testing)

set(OSBitness 32)
if(CMAKE_SIZEOF_VOID_P EQUAL 8)
	set(OSBitness 64)
endif()

set(FullOutputDir "${CMAKE_SOURCE_DIR}/bin/${CMAKE_SYSTEM_NAME}${OSBitness}/${CMAKE_BUILD_TYPE}")

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY "${FullOutputDir}/Static Libs")

set(CMAKE_LIBRARY_OUTPUT_DIRECTORY "${FullOutputDir}")

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "${FullOutputDir}")

message("-- Ken is generating...${PROJECT_NAME} 
                with build type ${CMAKE_BUILD_TYPE}")

include_directories(.)

# builds a STATIC library by default
#add_library(console console.cpp)

add_library(console SHARED console.cpp)

add_executable(${PROJECT_NAME} main.cpp)

target_link_libraries(${PROJECT_NAME} console)
