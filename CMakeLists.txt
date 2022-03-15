cmake_minimum_required(VERSION 3.22)

# set the project name
project(Tetris)

#Bring the headers, such as Student.h into the project
include_directories(include)
 
#Can manually add the sources using the set command as follows:
#set(SOURCES src/mainapp.cpp src/Student.cpp)
 
#However, the file(GLOB...) allows for wildcard additions:
file(GLOB SOURCES "src/*.cxx")
 
add_executable(tetris ${SOURCES})