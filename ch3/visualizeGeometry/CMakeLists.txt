cmake_minimum_required( VERSION 2.8 )
project( visualizeGeometry )

set(CMAKE_CXX_FLAGS "-std=c++11")

# 添加Eigen头文件
find_package( Eigen3 REQUIRED )
include_directories( ${EIGEN3_INCLUDE_DIR} )

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "/Users/ichn/Projects/robots/slambook2/3rdparty/Pangolin/build" )
set(CMAKE_PREFIX_PATH ${CMAKE_PREFIX_PATH} "/Users/ichn/Projects/robots/slambook2/3rdparty/Pangolin/build")
# 添加Pangolin依赖
find_package( Pangolin REQUIRED )
include_directories( ${Pangolin_INCLUDE_DIRS} )
MESSAGE(STATUS "Pangolin_INCLUDE_DIRS = ${Pangolin_INCLUDE_DIRS}")


add_executable( visualizeGeometry visualizeGeometry.cpp )
target_link_libraries( visualizeGeometry ${Pangolin_LIBRARIES} )
