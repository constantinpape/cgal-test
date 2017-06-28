cmake_minimum_required(VERSION 2.8.4)
project(cgal_test)

# set c++ 11
set(CMAKE_CXX_STANDARD 11)

# Find CGAL
#find_package(CGAL REQUIRED COMPONENTS Core)
find_package(CGAL REQUIRED)

# include relevant cgal stuff
include(${CGAL_USE_FILE})
include(CGAL_CreateSingleSourceCGALProgram)

# find eigen3 and add igen include dirs
find_package(Eigen3 REQUIRED)
include_directories(${EIGEN3_INCLUDE_DIR})

# enable eigen3 support 
add_definitions(-DCGAL_EIGEN3_ENABLED)

# add the target file
create_single_source_cgal_program("skel_example.cpp")
