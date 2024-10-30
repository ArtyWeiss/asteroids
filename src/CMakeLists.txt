add_executable (game 
  main.cpp
)

set_property(TARGET game PROPERTY CXX_STANDARD 20)
target_include_directories(game PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}")

target_link_libraries(game PRIVATE SDL3::SDL3)

if (WIN32)
    add_custom_command(
        TARGET game POST_BUILD
        COMMAND "${CMAKE_COMMAND}" -E copy $<TARGET_FILE:SDL3::SDL3-shared>
        $<TARGET_FILE_DIR:game>
        VERBATIM
    )
endif()