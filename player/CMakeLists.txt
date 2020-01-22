cmake_minimum_required(VERSION 3.7)

set (BLIPBUFFER_DUMB_PLAYER_HEADERS
    player.h
    Wave_Writer.h
)

set (BLIPBUFFER_DUMB_PLAYER_CPP_FILES
    player.cpp
    Wave_Writer.cpp
)

add_library (blip-buffer-dumb-player STATIC
    ${BLIPBUFFER_DUMB_PLAYER_HEADERS}
    ${BLIPBUFFER_DUMB_PLAYER_CPP_FILES}
)

target_include_directories (blip-buffer-dumb-player INTERFACE
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/../>
    $<INSTALL_INTERFACE:include>  # <prefix>/include/
)

target_link_libraries (blip-buffer-dumb-player blip-buffer)