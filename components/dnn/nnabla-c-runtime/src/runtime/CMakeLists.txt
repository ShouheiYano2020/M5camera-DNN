cmake_minimum_required(VERSION 2.8)

set(project_root "${CMAKE_CURRENT_SOURCE_DIR}/../..")
include(${project_root}/build-tools/cmake/common.cmake)

project(nnablart_runtime)

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/../../include)

add_library(nnablart_runtime STATIC
  runtime.c
  runtime_internal.c

  function_context.c)


install(FILES ../../include/nnablart/network.h DESTINATION include/nnablart)
install(FILES ../../include/nnablart/runtime.h DESTINATION include/nnablart)
install(TARGETS ${PROJECT_NAME} DESTINATION lib)
