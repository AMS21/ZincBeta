if (PHI_PLATFORM_EMSCRIPTEN)
     # Force js executable suffix for tests so node can run them
     set(CMAKE_EXECUTABLE_SUFFIX ".js")
endif()

# ZincBetaLibTest
add_subdirectory("ZincBetaLibTest")
