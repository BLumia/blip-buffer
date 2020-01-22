function(BLIPBUFFER_ADD_EXAMPLE _input_file_name _which_player)
    # get_filename_component (_bin_name ${_input_file_name} NAME_WE)
    string(REGEX REPLACE "\\.[^.]*$" "" _bin_name ${_input_file_name})
    add_executable (${_bin_name}
        ${_input_file_name}
    )
    target_link_libraries (${_bin_name} ${_which_player})
endfunction()

blipbuffer_add_example (1.waveform.cpp blip-buffer-dumb-player)
blipbuffer_add_example (2.square.cpp blip-buffer-dumb-player)
blipbuffer_add_example (3.clock_rate.cpp blip-buffer-dumb-player)
blipbuffer_add_example (4.continuous.cpp blip-buffer-dumb-player)
blipbuffer_add_example (delta_synth.cpp blip-buffer-dumb-player)
blipbuffer_add_example (sdl_audio.cpp blip-buffer-sdl-player)
blipbuffer_add_example (stereo.cpp blip-buffer-dumb-player)
blipbuffer_add_example (treble_bass.cpp blip-buffer-dumb-player)