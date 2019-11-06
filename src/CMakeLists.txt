# Note that headers are optional, and do not affect `add_library`, but they
# will not show up in IDEs unless they are listed in `add_library`.

set(HEADER_LIST "${PROJECT_SOURCE_DIR}/include/rtiow/lib.hpp")

add_library(rtiow lib.cpp ${HEADER_LIST})

target_include_directories(rtiow PUBLIC ../include)

target_compile_features(rtiow PUBLIC cxx_std_11)

target_link_libraries(rtiow PRIVATE fmt::fmt)

# IDEs should put headers in a nice place
source_group(TREE "${PROJECT_SOURCE_DIR}/include" PREFIX "Header Files" FILES ${HEADER_LIST})
