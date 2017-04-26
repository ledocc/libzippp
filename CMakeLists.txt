cmake_minimum_required(VERSION 3.7.2)


# define project
project(libzippp VERSION 2.1)


# search dependencies
list(APPEND CMAKE_MODULE_PATH "${PROJECT_SOURCE_DIR}/cmake")

find_package(ZLIB REQUIRED)
if(ZLIB_VERSION_STRING VERSION_LESS "1.1.2")
  message(FATAL_ERROR "zlib version too old, please install at least zlib v1.1.2")
endif()

find_package(LIBZIP REQUIRED)
if(LIBZIP_VERSION_STRING VERSION_LESS "1.2.0")
  message(FATAL_ERROR "libzip version too old, please install at least libzip v1.2.0")
endif()


# define LIBZIPPP_EXPORTS MACRO used to export function/class
add_definitions(-DLIBZIPPP_EXPORTS)


add_subdirectory(src)
add_subdirectory(tests)
