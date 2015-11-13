cmake_minimum_required (VERSION 2.6)
project (ka9q-fec)

set(CMAKE_BINARY_DIR ${CMAKE_SOURCE_DIR}/build)
 
SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -m32") 

set(EXECUTABLE_OUTPUT_PATH ${CMAKE_BINARY_DIR})
set(LIBRARY_OUTPUT_PATH ${CMAKE_BINARY_DIR})
 
set(PROJECT_INCLUDE_DIR
	${PROJECT_SOURCE_DIR}/include
	)
 

include_directories("${PROJECT_INCLUDE_DIR}")
include_directories("${PROJECT_SOURCE_DIR}")

add_subdirectory(src)
