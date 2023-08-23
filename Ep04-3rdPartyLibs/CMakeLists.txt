cmake_minimum_required(VERSION 3.15)
project(Packages)

set(OSBitness 32)
if(CMAKE_SIZEOF_VOID_P EQUAL 8)
	set(OSBitness 64)
endif()

set(FullOutputDir "${CMAKE_SOURCE_DIR}/bin/${CMAKE_SYSTEM_NAME}${OSBitness}/${CMAKE_BUILD_TYPE}")

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY "${FullOutputDir}/Static Libs")
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY "${FullOutputDir}")
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "${FullOutputDir}")

#set(CMAKE_PREFIX_PATH "C:/SDL2")
message("-- Adding SDL2 DIR to CMAKE_PREFIX_PATH - $ENV{SDL2DIR}")
set(CMAKE_PREFIX_PATH $ENV{SDL2DIR})

message("-- Ken is generating...${PROJECT_NAME} 
                with build type ${CMAKE_BUILD_TYPE}")

include_directories(.)

# Link SDL
find_package(SDL2 REQUIRED)
include_directories(${SDL2_INCLUDE_DIRS})

message("-- Found SDL2 Include DIR - ${SDL2_INCLUDE_DIRS}")

add_executable(${PROJECT_NAME} main.cpp)

target_link_libraries(${PROJECT_NAME} ${SDL2_LIBRARIES})
