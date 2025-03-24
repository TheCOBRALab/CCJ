# Ian Wark July 6 2017

cmake_minimum_required(VERSION 3.1)
project(CCJ)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -g -O3")

# Set option to build Sparse_CCJ (default ON)
option(BUILD_SPARSE_CCJ "Build Sparse_CCJ module" ON)

# Set option to build Original_CCJ (default ON)
option(BUILD_ORIGINAL_CCJ "Build Original_CCJ module" ON)

# set SIMFOLD_HOME to simfold folder so CCJ binary can find it
set(SIMFOLD_HOME ${CMAKE_SOURCE_DIR}/simfold)
add_subdirectory(simfold)

if(BUILD_SPARSE_CCJ)
    add_subdirectory(Sparse_CCJ) # (obsolete)
endif()

if(BUILD_ORIGINAL_CCJ)
    add_subdirectory(Original_CCJ)
endif()
