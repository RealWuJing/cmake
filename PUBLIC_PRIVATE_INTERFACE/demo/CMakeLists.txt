cmake_minimum_required (VERSION 2.8)

project (demo)

# create a lib target
add_library(hello src/hello.cpp)
# specify header path for hello lib
target_include_directories(hello PUBLIC ${PROJECT_SOURCE_DIR}/include)

# create main driver
add_executable(main src/main.cpp)
# add link deps
target_link_libraries(main hello)