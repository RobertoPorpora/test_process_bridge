cmake_minimum_required(VERSION 3.10)
project(test_process_bridge)

add_executable(${PROJECT_NAME} child.c)

set_target_properties(${PROJECT_NAME} PROPERTIES
    RUNTIME_OUTPUT_DIRECTORY "${CMAKE_SOURCE_DIR}/bin"
)

add_subdirectory("${CMAKE_SOURCE_DIR}/../../lib/c_process_bridge/" PB_build)
target_link_libraries(${PROJECT_NAME} process_bridge)