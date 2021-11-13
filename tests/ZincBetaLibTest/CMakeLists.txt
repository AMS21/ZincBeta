cmake_minimum_required(VERSION 3.10.2)

# Project
project("ZincBetaLibTest" CXX)

# Files
file(GLOB ZINCBETALIB_TEST_SOURCES "src/dummy.cpp" )
file(GLOB ZINCBETALIB_TEST_HEADERS)

source_group(TREE ${CMAKE_CURRENT_SOURCE_DIR} FILES ${ZINCBETALIB_TEST_SOURCES} ${ZINCBETALIB_TEST_HEADERS})

add_executable(${PROJECT_NAME} ${ZINCBETALIB_TEST_SOURCES} ${ZINCBETALIB_TEST_HEADERS})

target_link_libraries(${PROJECT_NAME} PRIVATE ZincBetaLib Catch2::Catch2WithMain Phi::ProjectOptions)

target_include_directories(${PROJECT_NAME} PRIVATE "include")

set_target_properties(${PROJECT_NAME} PROPERTIES FOLDER "Tests")

phi_add_test(TARGET ${PROJECT_NAME})
