cmake_minimum_required(VERSION 3.13)

include(pico_sdk_import.cmake)
project(BlueSensor C CXX ASM)

set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)
set(DPICO pico_w)

pico_sdk_init()

include_directories(${CMAKE_SOURCE_DIR})

add_executable(BlueSensor
	BlueSensor.S
	)

pico_enable_stdio_usb(BlueSensor 1)
pico_enable_stdio_uart(BlueSensor 0)
pico_add_extra_outputs(BlueSensor)
target_link_libraries(BlueSensor pico_stdlib)
