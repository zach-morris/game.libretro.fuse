cmake_minimum_required(VERSION 3.1)
project(game.libretro.fuse)

list(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR})

find_package(Kodi REQUIRED)
find_library(FUSE_LIB NAMES fuse_libretro${CMAKE_SHARED_LIBRARY_SUFFIX} PATH_SUFFIXES libretro)

set(FUSE_CUSTOM_BINARY ${FUSE_LIB}
    ${PROJECT_NAME}${CMAKE_SHARED_LIBRARY_SUFFIX})

build_addon(${PROJECT_NAME} FUSE "")

include(CPack)
