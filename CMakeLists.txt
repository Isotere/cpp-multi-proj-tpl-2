cmake_minimum_required(VERSION 3.31)

set(_PATCH_VERSION "1" CACHE INTERNAL "Patch version")
set(PROJECT_VERSION 0.1.${_PATCH_VERSION})

project(project_name VERSION 0.0.${_PATCH_VERSION})

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

set(CMAKE_C_COMPILER /opt/homebrew/opt/llvm/bin/clang)
set(CMAKE_CXX_COMPILER /opt/homebrew/opt/llvm/bin/clang++)
set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED True)

set(CMAKE_CXX_EXTENSIONS OFF)

# Let's nicely support folders in IDEs
set_property(GLOBAL PROPERTY USE_FOLDERS ON)

set(CMAKE_CXX_FLAGS ${CompilerFlags} -stdlib=libc++)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "${PROJECT_SOURCE_DIR}/bin")

# FetchContent added in CMake 3.11, downloads during the configure step
include(FetchContent)

add_subdirectory(src/hello_world)

