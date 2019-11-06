# Testing library
FetchContent_Declare(
  catch2
  GIT_REPOSITORY https://github.com/catchorg/Catch2.git
  GIT_TAG        v2.11.1
)
# Adds `Catch2::Catch2`
FetchContent_MakeAvailable(catch2)

add_executable(rtiowtest testlib.cpp)

target_compile_features(rtiowtest PRIVATE cxx_std_11)

target_link_libraries(rtiowtest PRIVATE rtiow Catch2::Catch2)

add_test(NAME tests COMMAND rtiowtest)
