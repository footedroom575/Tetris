cmake_minimum_required(VERSION 3.22)

# set the project name
project(Tetris)

# if you want to compile your own glfw3
set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)
add_subdirectory(lib/GLFW/)

# if you want to use native glfw3
# find_package(glfw3 REQUIRED)

# adding opengl as required
find_package(OpenGL REQUIRED)

# adding glad.c library 
add_library(GLAD "lib/GLAD/glad.c")

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

# linking glad glfw3 opengl
target_link_libraries(tetris
    ${OPENGL_LIBRARY} # filled by "find_package(OpenGL REQUIRED)"
    glfw
    GLAD
)

