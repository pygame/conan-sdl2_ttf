cmake_minimum_required(VERSION 2.8.12)
project(test_package)

set(CMAKE_VERBOSE_MAKEFILE TRUE)

include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
conan_basic_setup()

set(FONT_PATH "${CMAKE_CURRENT_LIST_DIR}/OpenSans-Bold.ttf" CACHE STRING "Path of font")

add_executable(${PROJECT_NAME} test_package.c)
target_compile_definitions(${PROJECT_NAME} PRIVATE
  FONT_PATH="${FONT_PATH}")
target_link_libraries(${PROJECT_NAME} ${CONAN_LIBS})
