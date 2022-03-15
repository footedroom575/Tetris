cmake_minimum_required(VERSION 3.22)

# set the project name
project(Tetris)

#Bring the headers, such as Student.h into the project
include_directories(include)
 
#Can manually add the sources using the set command as follows:
set(SOURCES src/main.cxx src/home.cxx) 
 
add_executable(tetris ${SOURCES})
