cmake_minimum_required(VERSION 3.7)

project(blip-buffer)

set (BLIPBUFFER_HEADERS
    Blip_Buffer.h
)

set (BLIPBUFFER_CPP_FILES
    Blip_Buffer.cpp
)

add_library (blip-buffer STATIC
    ${BLIPBUFFER_HEADERS}
    ${BLIPBUFFER_CPP_FILES}
)

target_include_directories(blip-buffer INTERFACE
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/>
    $<INSTALL_INTERFACE:include>  # <prefix>/include/
)

add_subdirectory (player)
add_subdirectory (sdl_player)
add_subdirectory (demo)