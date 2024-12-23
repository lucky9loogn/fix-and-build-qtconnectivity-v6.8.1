cmake_minimum_required(VERSION 3.16)
project(build-qtconnectivity)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wno-dev")

# find_package(Qt6 REQUIRED COMPONENTS Core)

# message(STATUS "Qt Version: ${Qt6_VERSION}")

add_subdirectory(qtconnectivity)

if(WIN32)
  add_custom_target(
    Copy-Qt6Bluetooth.dll-to-dist
    COMMAND ${CMAKE_COMMAND} -E make_directory
            ${CMAKE_SOURCE_DIR}/dist/
    COMMAND
      ${CMAKE_COMMAND} -E copy ${CMAKE_CURRENT_BINARY_DIR}/bin/Qt6Bluetooth.dll
      ${CMAKE_SOURCE_DIR}/dist/
    SOURCES ${CMAKE_CURRENT_SOURCE_DIR}/CMakeLists.txt
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})
endif()
