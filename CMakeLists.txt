cmake_minimum_required(VERSION 3.5)

project(tiled_ncurses LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -fno-rtti")

add_library(${PROJECT_NAME} STATIC
    include/tiled_ncurses/tiled_ncurses.hpp
    src/tiled_ncurses.cpp
)

target_include_directories(${PROJECT_NAME}
    PRIVATE ./
    PUBLIC include
)

target_link_libraries(${PROJECT_NAME}
    PRIVATE string_essentials
    PUBLIC ncurses
)
