cmake_minimum_required(VERSION 3.25)
project(stb VERSION 0.1)
enable_language(C CXX)

file(GLOB stb_headers "stb/*.h")
add_library(stb INTERFACE)

install(
    TARGETS stb
    EXPORT stb_export
    INCLUDES DESTINATION "include"
)

install(
    EXPORT stb_export
    FILE "stb-config.cmake"
    DESTINATION "cmake"
)

install(
    FILES ${stb_headers}
    DESTINATION "include"
)
