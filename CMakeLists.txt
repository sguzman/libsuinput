cmake_minimum_required(VERSION 3.16)
project(libsuinput C)

set(CMAKE_C_STANDARD 11)

add_library(libsuinput SHARED src/libudev.h src/suinput.c src/suinput.h)

add_executable(keyboard examples/keyboard.c)
add_executable(mouse examples/mouse.c)
