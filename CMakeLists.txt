cmake_minimum_required(VERSION 3.16)
project(fix-and-build-qtconnectivity)

add_subdirectory(qtconnectivity)

# # 获取编译生成的Qt6Bluetooth.dll的路径
# set(OUTPUT_DLL_PATH ${CMAKE_CURRENT_BINARY_DIR}/bin/Qt6Bluetooth.dll)

# # 获取编译使用的Qt版本
# string(REGEX MATCH "Qt_([0-9]+_[0-9]+_[0-9]+)" OUTPUT_DLL_VERSION ${CMAKE_CURRENT_BINARY_DIR})
# string(REPLACE "Qt_" "" OUTPUT_DLL_VERSION ${OUTPUT_DLL_VERSION})
# string(REPLACE "_" "." OUTPUT_DLL_VERSION ${OUTPUT_DLL_VERSION})
# set(OUTPUT_DLL_VERSION "v${OUTPUT_DLL_VERSION}")

# # 复制Qt6Bluetooth.dll到dist目录下
# if(WIN32)
#   add_custom_target(
#     Copy-Qt6Bluetooth.dll-to-dist
#     COMMAND ${CMAKE_COMMAND} -E make_directory ${CMAKE_SOURCE_DIR}/dist/${OUTPUT_DLL_VERSION}
#     COMMAND ${CMAKE_COMMAND} -E copy
#             ${OUTPUT_DLL_PATH} ${CMAKE_SOURCE_DIR}/dist/${OUTPUT_DLL_VERSION}
#     SOURCES ${CMAKE_CURRENT_SOURCE_DIR}/CMakeLists.txt
#     WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})
# endif()
