cmake_minimum_required(VERSION 3.15)
project(test_grpc_project)

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_subdirectory(./deps/grpc deps/grpc_build EXCLUDE_FROM_ALL)

add_executable(test_grpc main.cpp)

target_link_libraries(test_grpc PRIVATE grpc++)

target_include_directories(test_grpc PRIVATE ./deps/grpc/include)