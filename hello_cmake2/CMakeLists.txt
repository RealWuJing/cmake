cmake_minimum_required (VERSION 2.6)

project(hello_cmake)

#//头文件目录
include_directories(${PROJECT_SOURCE_DIR}/include)

#添加静态库目录
LINK_DIRECTORIES(${PROJECT_SOURCE_DIR}/static)

# link_libraries("-static")

#//生成可执行文件
add_executable(hello_cmake main.cpp)

#//链接库到可执行文件，以下三种写法都是可以的
#target_link_libraries(hello_cmake libhello.a)
#target_link_libraries(hello_cmake hello.a)
target_link_libraries(hello_cmake 
    PUBLIC "-static"
    hello
)
