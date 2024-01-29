cmake_minimum_required(VERSION 3.15)

project(PitchShifterPlugin)

if (WIN32)
  add_definitions(-DNOMINMAX)
endif (WIN32)

# set(JUCE_SOURCE_DIR "/JUCE") # set juce source dir
# add_subdirectory(${JUCE_SOURCE_DIR} "${CMAKE_BINARY_DIR}/juce")

# use CPM
include(cmake/CPM.cmake)
set(CPM_USE_NAMED_CACHE_DIRECTORIES true)
set(CPM_SOURCE_CACHE ~/.cache/CPM)

# get JUCE
CPMAddPackage("gh:juce-framework/JUCE@7.0.9#master")

add_subdirectory(rubberband)
add_subdirectory(plugin)
