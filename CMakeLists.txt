cmake_minimum_required(VERSION 2.8)

project(openssl)

include_directories(${CMAKE_CURRENT_SOURCE_DIR})
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)

add_subdirectory(crypto)
add_subdirectory(ssl)

set(OPENSSL_INCLUDE_DIR ${CMAKE_CURRENT_SOURCE_DIR}/include PARENT_SCOPE)

set(OPENSSL_LIBRARIES crypto ssleay32)
