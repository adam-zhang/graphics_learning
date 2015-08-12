#=============================================================================
#     FileName: CMakeLists.txt
#         Desc: 
#       Author: Mingping (Adam) Zhang
#        Email: mingpingzhang@163.com
#     HomePage: 
#      Version: 0.0.1
#   LastChange: 2015-08-12 16:38:47
#      History:
#=============================================================================

project(gultDemo)
cmake_minimum_required(VERSION 2.8)

find_package(OpenGL REQUIRED)
include_directories(${OpenGL_INCLUDE_DIRS})
link_directories(${OpenGL_LIBRARY_DIRS})
add_definitions(${OpneGL_DEFINITIONS})
if(NOT OPENGL_FOUND)
	message(ERROR "OpenGL did not find")
endif(NOT OPENGL_FOUND)

find_package(GLUT REQUIRED)
include_directories(${GLUT_INCLUDE_DIRS})
link_directories(${GLUT_LIBRARY_DIRS})
add_definitions(${GLUT_DEFINITIONS})
if(NOT GLUT_FOUND)
	message(ERROR "GLUT is not found")
endif(NOT GLUT_FOUND)


add_executable(glutDemo appMain.cpp)
target_link_libraries(glutDemo ${OPENGL_LIBRARIES} ${GLUT_LIBRARY})


