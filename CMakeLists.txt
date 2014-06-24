##
## Author(s):
##  - Cedric GESTES      <gestes@aldebaran-robotics.com>
##
## Copyright (C) 2012 Aldebaran Robotics
##
cmake_minimum_required(VERSION 2.6.4)
project(libqi-capi)
find_package(qibuild)

enable_testing()

qi_sanitize_compile_flags(HIDDEN_SYMBOLS)

include_directories("${CMAKE_CURRENT_SOURCE_DIR}")

qi_create_lib("qic" SHARED qic/api.h
                     qic/application.h
                     qic/session.h
                     qic/object.h
                     qic/future.h
                     qic/value.h
                     qic/type.h

                     src/object_p.h
                     src/object.cpp
                     src/future_p.h
                     src/future.cpp
                     src/session.cpp
                     src/application.cpp
                     src/value_p.h
                     src/value.cpp
                     src/type.cpp)

qi_use_lib(qic qimessaging qitype qi)
qi_stage_lib(qic)

add_subdirectory("test")
add_subdirectory("bin")
