cmake_minimum_required (VERSION 2.8)

project (demo2)

# create hello lib
add_library(hello SHARED src/hello.cpp)
target_include_directories(hello PUBLIC ${PROJECT_SOURCE_DIR}/include/hello)

# create world lib
add_library(world SHARED src/world.cpp)
target_include_directories(world PUBLIC ${PROJECT_SOURCE_DIR}/include/world)
target_link_libraries(world PRIVATE hello)

# create main executable file
add_executable(main src/main.cpp)
target_link_libraries(main PUBLIC world)