cmake_minimum_required(VERSION 3.7)

find_package(SDL REQUIRED)

set (BLIPBUFFER_SDL_PLAYER_HEADERS
    player.h
    Audio_Scope.h
    Sync_Audio.h
)

set (BLIPBUFFER_SDL_PLAYER_CPP_FILES
    player.cpp
    Audio_Scope.cpp
    Sync_Audio.cpp
)

add_library (blip-buffer-sdl-player STATIC
    ${BLIPBUFFER_SDL_PLAYER_HEADERS}
    ${BLIPBUFFER_SDL_PLAYER_CPP_FILES}
)

target_include_directories (blip-buffer-sdl-player 
PUBLIC
    ${SDL_INCLUDE_DIR}
INTERFACE
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/../>
    $<INSTALL_INTERFACE:include>  # <prefix>/include/
)

target_link_libraries (blip-buffer-sdl-player blip-buffer ${SDL_LIBRARY})