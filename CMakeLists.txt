cmake_minimum_required(VERSION 3.11...3.15)

# Version ranges were added in CMake 3.12
if(${CMAKE_VERSION} VERSION_LESS 3.12)
  cmake_policy(VERSION ${CMAKE_MAJOR_VERSION}.${CMAKE_MINOR_VERSION})
endif()

project(RayTracingInOneWeekend
  VERSION 0.2
  DESCRIPTION "Ray Tracing in One Weekend (C++)"
  LANGUAGES CXX
)

# Only do these if this is the main project, and not if it is included through
# `add_subdirectory`
if(CMAKE_PROJECT_NAME STREQUAL PROJECT_NAME)
  # Ensure `-std=c++xx` instead of `-std=g++xx`
  set(CMAKE_CXX_EXTENSIONS OFF)
  # Support folders in IDEs
  set_property(GLOBAL PROPERTY USE_FOLDERS ON)
  # This needs to be done in the main `CMakeLists.txt` since it calls
  # `enable_testing`
  include(CTest)
endif()

# `FetchContent` was added in CMake 3.11
include(FetchContent)
# `FetchContent_MakeAvailable` was not added until CMake 3.14
if(${CMAKE_VERSION} VERSION_LESS 3.14)
  include(cmake/FetchContent_MakeAvailable.cmake)
endif()

# Formatting library
FetchContent_Declare(
  fmtlib
  GIT_REPOSITORY https://github.com/fmtlib/fmt.git
  GIT_TAG        6.0.0
)
# Adds `fmt::fmt`
FetchContent_MakeAvailable(fmtlib)

add_subdirectory(src)

add_subdirectory(apps)

if(CMAKE_PROJECT_NAME STREQUAL PROJECT_NAME AND BUILD_TESTING)
  add_subdirectory(tests)
endif()
