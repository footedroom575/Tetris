cmake_minimum_required(VERSION 3.22)

# set the project name
project(Tetris)

find_package(OpenGL REQUIRED)
find_package(glfw3 REQUIRED)
add_library(GLAD "src/glad.c")

#Bring the headers, such as Student.h into the project
set(MY_HEADER_FILES
    include/home.hxx
)

set(MY_SOURCE_FILES
    src/main.cxx 
    src/home.cxx
)


add_executable(tetris
	${MY_HEADER_FILES}
	${MY_SOURCE_FILES}
)


target_link_libraries(tetris
    ${OPENGL_LIBRARY} # filled by "find_package(OpenGL REQUIRED)"
    glfw
    GLAD
)

