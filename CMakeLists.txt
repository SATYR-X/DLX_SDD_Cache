cmake_minimum_required(VERSION 3.10)

project(AlgorithmDXZ VERSION 1.0)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# 添加头文件路径
include_directories(${PROJECT_SOURCE_DIR}/include)

# 设置源文件
set(MAIN_SOURCES
    src/main.cpp
    src/DLXZ.cpp
)

# 添加可执行文件
add_executable(main ${MAIN_SOURCES})
# add_executable(test ${TEST_SOURCES})

# 链接本地 libsdd.a 静态库
target_link_libraries(main
    ${PROJECT_SOURCE_DIR}/libs/libsdd.a
    m
)

set(TEST_SOURCES
    test/test.cpp
    src/DLXZ.cpp
)


# 添加调试标志
set(CMAKE_BUILD_TYPE Debug)
set(CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} -g")