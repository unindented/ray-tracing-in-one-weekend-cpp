add_executable(rtiowapp app.cpp)

target_compile_features(rtiowapp PRIVATE cxx_std_11)

target_link_libraries(rtiowapp PRIVATE rtiow)
