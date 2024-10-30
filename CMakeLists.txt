cmake_minimum_required(VERSION 3.8)

project("asteroids")

add_subdirectory(deps)

set(assets_dir ${PROJECT_SOURCE_DIR}/assets)
set (CMAKE_RUNTIME_OUTPUT_DIRECTORY "${PROJECT_SOURCE_DIR}/bin")
set (CMAKE_LIBRARY_OUTPUT_DIRECTORY "${PROJECT_SOURCE_DIR}/bin")

add_subdirectory(src)