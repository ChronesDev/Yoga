# Copyright (c) Facebook, Inc. and its affiliates.
#
# This source code is licensed under the MIT license found in the
# LICENSE file in the root directory of this source tree.

cmake_minimum_required(VERSION 3.4.1)

set(CMAKE_VERBOSE_MAKEFILE on)

add_compile_options(
    -fno-omit-frame-pointer
    -fexceptions
    -fvisibility=hidden
    -ffunction-sections
    -fdata-sections
    -Wall
    -std=c++11)

file(GLOB_RECURSE yoga_impl yoga/yoga/*.cpp)
add_library(yoga STATIC ${yoga_impl})

target_include_directories(yoga PUBLIC yoga/)
set_target_properties(yoga PROPERTIES CXX_STANDARD 11)
