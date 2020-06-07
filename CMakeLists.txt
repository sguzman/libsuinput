cmake_minimum_required(VERSION 3.16)
project(libsuinput C)

set(CMAKE_C_STANDARD 11)
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wall -Wextra")

set(CMAKE_C_FLAGS_DEBUG "${CMAKE_C_FLAGS_DEBUG} -g")
set(CMAKE_C_FLAGS_RELEASE "${CMAKE_C_FLAGS_RELEASE} -O3")

add_library(libsuinput SHARED src/libudev.h src/suinput.c src/suinput.h)

add_executable(keyboard examples/keyboard.c)
add_executable(mouse examples/mouse.c)
add_executable(mouse-and-keyboard examples/mouse-and-keyboard.c)

target_link_libraries(keyboard suinput)
target_link_libraries(mouse suinput)
target_link_libraries(mouse-and-keyboard suinput)
