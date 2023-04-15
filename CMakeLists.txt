cmake_minimum_required( VERSION 3.2 )

project( Lazy_Foo CXX )

find_package(SDL2 REQUIRED)

# find_package(OpenGL REQUIRED)

set ( Lessons 
  01_hello_SDL
  02_getting_an_image_on_the_screen
  03_event_driven_programming
  04_key_presses
  05_optimized_surface_loading_and_soft_stretching
  06_extension_libraries_and_loading_other_image_formats
  07_texture_loading_and_rendering
  08_geometry_rendering
  09_the_viewport
  10_color_keying
  11_clip_rendering_and_sprite_sheets
  12_color_modulation
  13_alpha_blending
  14_animated_sprites_and_vsync
  15_rotation_and_flipping
  16_true_type_fonts
  17_mouse_events
  18_key_states
  19_gamepads_and_joysticks
  20_force_feedback
  21_sound_effects_and_music
  22_timing
  23_advanced_timers
  24_calculating_frame_rate
  25_capping_frame_rate
  26_motion
  27_collision_detection
  28_per-pixel_collision_detection
  29_circular_collision_detection
  30_scrolling
  31_scrolling_backgrounds
  32_text_input_and_clipboard_handling
 # 33_file_reading_and_writing
  35_window_events
  36_multiple_windows
  37_multiple_displays
  38_particle_engines
  39_tiling
  40_texture_manipulation
  41_bitmap_fonts
  42_texture_streaming
  43_render_to_texture
  44_frame_independent_movement
  45_timer_callbacks
  46_multithreading
  47_semaphores
  48_atomic_operations
  49_mutexes_and_conditions
#  50_SDL_and_opengl_2
#  51_SDL_and_modern_opengl
  52_hello_mobile
  53_extensions_and_changing_orientation
  54_touches
  55_multitouch )

foreach( lesson ${Lessons} )
  add_executable( ${lesson} ${lesson}/${lesson}.cpp )
  target_include_directories( ${lesson} PRIVATE ${SDL2_INCLUDE_DIRS} )
  target_link_libraries( ${lesson} PRIVATE ${SDL2_LIBRARIES} SDL2_image SDL2_ttf SDL2_mixer )
endforeach()
