##
## Author(s):
##  - Laurent LEC        <llec@aldebaran-robotics.com>
##
## Copyright (C) 2009, 2010, 2012 Aldebaran Robotics
##
cmake_minimum_required(VERSION 2.6.4)
project(libqi-capi-bin)
find_package(qibuild)

add_subdirectory("qiclient-c")
add_subdirectory("qiservice-c")
