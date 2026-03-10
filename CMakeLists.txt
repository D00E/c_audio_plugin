cmake_minimum_required(VERSION 3.10.0)
project(c_audio_plugin VERSION 0.1.0 LANGUAGES C)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

add_executable(c_audio_plugin main.c)

find_package(SDL3 REQUIRED)

target_link_libraries(c_audio_plugin PRIVATE SDL3::SDL3)

if(TARGET SDL3::SDL3main)
	target_link_libraries(c_audio_plugin PRIVATE SDL3::SDL3main)
endif()

include(CTest)
enable_testing()

