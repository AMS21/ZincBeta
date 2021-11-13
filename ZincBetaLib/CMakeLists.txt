cmake_minimum_required(VERSION 3.10.2)

project(ZincBetaLib LANGUAGES CXX)

file(
  GLOB
  ZINCBETALIB_SOURCES
  "src/dummy.cpp")

file(
  GLOB
  ZINCBETALIB_HEADERS)

add_library(${PROJECT_NAME} STATIC ${ZINCBETALIB_SOURCES} ${ZINCBETALIB_HEADERS})

target_include_directories(${PROJECT_NAME} PUBLIC "include")
target_link_libraries(
  ${PROJECT_NAME}
  PUBLIC Phi::Core
  PRIVATE Phi::ProjectOptions)
target_compile_definitions(${PROJECT_NAME} PUBLIC "$<$<CONFIG:RELWITHDBGINFO>:PHI_DEBUG>")
phi_enable_static_analyzers(${PROJECT_NAME})
