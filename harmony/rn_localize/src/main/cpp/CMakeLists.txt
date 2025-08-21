cmake_minimum_required(VERSION 3.13)
set(CMAKE_VERBOSE_MAKEFILE on)

set(rnoh_localize_generated_dir "${CMAKE_CURRENT_SOURCE_DIR}/generated")
file(GLOB_RECURSE rnoh_localize_generated_SRC "${rnoh_localize_generated_dir}/**/*.cpp")
file(GLOB rnoh_localize_SRC CONFIGURE_DEPENDS *.cpp)
add_library(rnoh_localize SHARED ${rnoh_localize_SRC} ${rnoh_localize_generated_SRC})
target_include_directories(rnoh_localize PUBLIC ${CMAKE_CURRENT_SOURCE_DIR} ${rnoh_localize_generated_dir})
target_link_libraries(rnoh_localize PUBLIC rnoh)